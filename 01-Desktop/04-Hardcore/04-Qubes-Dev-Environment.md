# Qubes Development Environment

Rule number 1, don’t do anything other than code editor and git in a development VM. Web browsing has probably the highest risk so use Disposable VMs for that. Some code is safe to test in a development VM if you verify it only runs locally.

Another example use case for development VM is using it only to make SSH connections.

Follow this section to setup your secure development enviroment quickly.

<br/>

## Table of Contents
* [1. Install VSCodium](#install-vscodium)
* [2. GitHub Over Tor](#github-over-tor-tunneled-ssh)
* [3. Bash Git Prompt](#bash-git-prompt)
* [4. SSH Shortcuts](#ssh-shortcuts)


## Install VSCodium

This will be a Template that you can customize if you prefer multiple seperated development environments with VSCodium editor. This can be useful for a variety of security, privacy, and testing scenarios.

1. Create Template VM named `whonix-17-dev`.

2. Open terminal for `whonix-17-dev` and use curl to obtain PGP key belonging to Paulcarroty.

```
sudo curl -o /usr/share/keyrings/vscodium-archive-keyring.asc https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/raw/master/pub.gpg
```

3. Add entry to sources list.

```
echo 'deb [ arch=amd64 signed-by=/usr/share/keyrings/vscodium-archive-keyring.asc ] https://paulcarroty.gitlab.io/vscodium-deb-rpm-repo/debs vscodium main' \
    | sudo tee /etc/apt/sources.list.d/vscodium.list
```

4. Run update and install VS Codium and other dependencies.

```
sudo apt update && sudo apt install codium gpg netcat-openbsd git ssh
```

5. Shut down `whonix-17-dev` Template VM.

6. Create new App VM called `whonix-dev1` based on `whonix-17-dev` Template VM, go to `Settings` > `Applications` and add VS Codium.

7. Install any other applications or packages in the `whonix-17-dev` Template VM and **not** in the `whonix-dev1` App VM. Anything installed in an App VM will be lost if it is not installed in the Template VM.

7. Your new development environment is now ready to be customized and put to use. Repeat step 6 and create as many new App VMs as you like.

<details>

<summary>**>> Click here to expand additional resources**</summary>

### Why Use Codium?

Codium contains build files to generate free release binaries of Microsoft's VS Code. When we speak of "free" or "FOSS" software, we're talking about freedom, not price.

Microsoft's releases of Visual Studio Code are licensed under this not-FOSS license and contain telemetry/tracking. According to this comment from a Visual Studio Code maintainer:

    "When we [Microsoft] build Visual Studio Code, we do exactly this. We clone the vscode repository, we lay down a customized product.json that has Microsoft specific functionality (telemetry, gallery, logo, etc.), and then produce a build that we release under our license.

    When you clone and build from the vscode repo, none of these endpoints are configured in the default product.json. Therefore, you generate a "clean" build, without the Microsoft customizations, which is by default licensed under the MIT license."

This repo exists so that you don't have to download+build from source. The build scripts in this repo clone Microsoft's vscode repo, run the build commands, and upload the resulting binaries to GitHub releases. These binaries are licensed under the MIT license. Telemetry is disabled.

If you want to build from source yourself, head over to Microsoft's vscode repo and follow their instructions. This repo exists to make it easier to get the latest version of MIT-licensed VS Code.

Gitlab Repo - [Clearnet Link](https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo)

Github Repo - [Clearnet Link](https://github.com/VSCodium/vscodium/blob/master/docs/index.md)

Discussion - [Clearnet Link](https://forum.qubes-os.org/t/installing-visual-studio-code-unity-securely/11219)

</details>

<br/>

## GitHub over Tor-tunneled SSH

Now that you have the ability to create multiple development environments using the Codium guide above, try interacting with a repo via command line, in this example we will interact with The Sovereign Repo. This can be adapted for Gitlab or Gitea users as well.

**NOTE:** For security, do not use this VM for any other purpose besides interacting with a repo.

1. Open the Terminal in your new `whonix-dev1` App VM.

2. Create an ssh key, and see more info about generating new keys here. [Tor Link](http://w5j6stm77zs6652pgsij4awcjeel3eco7kvipheu6mtr623eyyehj4yd.onion/wiki/SSH#Key_Generation) | [Clearnet Link](https://www.kicksecure.com/wiki/SSH#Key_Generation)
    ```
    ssh-keygen -o -a 75 -t ed25519
    ```

3. When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location of `~/.ssh`.

4. Rename files.
    ```
    mv ~/.ssh/id_ed25519 ~/.ssh/sovrepo_rsa
    mv ~/.ssh/id_ed25519.pub ~/.ssh/sovrepo_rsa.pub
    ```

5. Create PGP key.
    ```
    gpg --full-generate-key
    # Key type is 1
    # Key size is 4096
    # Set expiry you want
    # Enter name you want
    # Enter email you used for your github account
    # Type secure passphrase and record it in your password manager
    ```

6.  Copy the alphanumeric value that comes after `0x`. It will be used for the `user.signingkey` value in step 7 below.
    ```
    gpg --list-keys | grep "pub"
    ```

7.  Edit these commands as needed, then run them to configure Git. Check `~/.gitconfig` file at any time to see the git configuration settings. The `--global` flag is used in this case as we want to ensure each development VM is seperate. If you want to see an example without that flag see [this guide](https://github.com/thesovereignrepo/The-Sovereign-Repository/blob/master/How-To-Contribute.md#github-over-tor-tunneled-ssh).
    ```
    git config --global user.name "Github Username"
    git config --global user.email githubemail@example.com
    git config --global commit.gpgsign true
    git config --global pull.rebase true
    git config --global user.signingkey PASTE-KEY-FROM-STEP-6
    ```

8. Copy your SSH and GPG public keys.
    ```
    cat ~/.ssh/sovrepo_rsa.pub
    gpg --export --armor githubemail@example.com
    ```

8. Add your SSH and GPG public keys to your GitHub account. [Clearnet Link](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)

9. Edit your SSH configuration file.
    ```
    nano ~/.ssh/config
    ```

10. Add this to your `~/.ssh/config` and press Ctrl + X then Y to save. This will forward all SSH commands to github.com through your Tor proxy.
    ```
    Host github.com
    IdentityFile ~/.ssh/sovrepo_rsa
    ProxyCommand nc -X 5 -x localhost:9050 %h %p
    ```

11. Make sure to always use the SSH variant of GitHub repositories when you go to clone. Try cloning a repository and if everything looks good try a few other commands. 
    ```
    git clone git@github.com:thesovereignrepo/The-Sovereign-Repository.git
    cd ~/The-Sovereign-Repository
    git status
    git checkout develop
    ls -la
    ```

12. Want to learn more about using Git in command line? Here is a great book. [Clearnet Link](https://git-scm.com/book/en/v2)

<br/>

13. (Optional) Many prefer this configutaion option.

    ```
    git config pull.rebase true
    ```


## Bash Git Prompt

Could be used in any development VM such as `whonix-dev1` mentioned above. Bash Git Prompt could make your command line experience a little more enjoyable.

1. Follow instructions to git clone and edit ~/.bashrc

2. Make sure `~/bash-git-prompt` is renamed to `~/.bash-git-prompt`

Add the following to ~/.bashrc:
    ```
    if [ -f "$HOME/.bash-git-prompt/gitprompt.sh" ]; then
        GIT_PROMPT_ONLY_IN_REPO=1
        source /usr/share/bash-completion/completions/git
        source $HOME/.bash-git-prompt/gitprompt.sh
    fi
    ```

3. Change directory to any git repo and test:

`source ~/.bashrc`

4. For final touches run:

`nano .gitconfig`

5. Add:
```
[alias]
    aa = add --all
    bv = branch -vv
    ba = branch -ra
    bd = branch -d
    bup = remote update origin --prune
    ca = commit --amend
    cb = checkout -b
    cm = commit -a --amend -C HEAD
    ci = commit -a -v
    co = checkout
    di = diff
    ll = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --numstat
    ld = log --pretty=format:"%C(yellow)%h\\ %C(green)%ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short --graph
    ls = log --pretty=format:"%C(green)%h\\ %C(yellow)[%ad]%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=relative
    last = log -1 HEAD
    mm = merge --no-ff
    st = status --short --branch
    tg = tag -a
    pu = push --tags
    un = reset --hard HEAD
    uh = reset --hard HEAD^
    up = pull --rebase origin master
[color]
    diff = auto
    status = auto
    branch = auto
[push]
        default = simple
[core]
        editor = vim
[user]
	name = XXX
	email = XXX
	signingkey = XXXXXXXXXXXXXXXX
[commit]
	gpgsign = true
```

Github Repo - [Clearnet Link](https://github.com/magicmonty/bash-git-prompt)

<br/>

## SSH Shortcuts

For example the IP could be 192.168.0.3 and instead of memorizing that IP, you want to just use `rpi4`.

1. Run command
    ```
    sudo nano ~/.ssh/config
    ```

2. Example config file
    ```
    Host rpi4
    Hostname = 192.168.0.3
    User = username
    ```

3. Example SSH command entered into the terminal
    ```
    ssh rpi4
    ```

<br/>

## Continue Your Training

Continue to the [Mobile Section](https://github.com/thesovereignrepo/The-Sovereign-Repository/tree/master/02-Mobile) of guides to advance your training further. A new journey with mobile devices is waiting.
