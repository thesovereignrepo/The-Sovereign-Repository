# Some Dev Enviro Stuff

Most importantly, don’t do anything other than code editor and git in a development VM. Browsing has probably the highest risk. Therefore best if avoided in a development VM. Some code is safe to test in a development VM if you verofy it only runs locally.

<br/>

# Install VSCode

The following assumes you have a debian template.

You can either download the .deb in a disposable VM and then transfer it to the template, or you can install the snap backend in the template and then download the snap package in the application VM.

Once installed go to the application VM settings, click the Applications tab, and add VSCode to your menu.

Install VSCode - [Clearnet Link](https://forum.qubes-os.org/t/installing-visual-studio-code-unity-securely/11219)

<details>

<summary>**>> Click here to expand additional resources**</summary>

### Why Use Codium?

Codium contains build files to generate free release binaries of Microsoft's VS Code. When we speak of "free" or "FOSS" software, we're talking about freedom, not price.

Microsoft's releases of Visual Studio Code are licensed under this not-FOSS license and contain telemetry/tracking. According to this comment from a Visual Studio Code maintainer:

    "When we [Microsoft] build Visual Studio Code, we do exactly this. We clone the vscode repository, we lay down a customized product.json that has Microsoft specific functionality (telemetry, gallery, logo, etc.), and then produce a build that we release under our license.

    When you clone and build from the vscode repo, none of these endpoints are configured in the default product.json. Therefore, you generate a "clean" build, without the Microsoft customizations, which is by default licensed under the MIT license."

This repo exists so that you don't have to download+build from source. The build scripts in this repo clone Microsoft's vscode repo, run the build commands, and upload the resulting binaries to GitHub releases. These binaries are licensed under the MIT license. Telemetry is disabled.

If you want to build from source yourself, head over to Microsoft's vscode repo and follow their instructions. This repo exists to make it easier to get the latest version of MIT-licensed VS Code.

</details>

<br/>

# Quick Local SSH Shortcuts

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

# GitHub over Tor-tunneled SSH

For users of QubesOS Whonix Virtual Machines, learn to interact with the repo via command line.

**NOTE:** Do not use this VM for any other purpose besides interacting with this repo.

1. Create a new Qube and choose the following attributes.
    ```
    Name:      tsr-editing
    Color:     red
    Type:      standaloneVM
    Template:  whonix-workstation-17
    Network:   sys-whonix
    ```

2. Launch the `tsr-editing` Qube, open Terminal, and make sure you have the necessary dependencies. 
    ```
    sudo apt install gpg netcat-openbsd tor git ssh
    ```

2. Create an ssh key, and see more info about generating new keys here. [Tor Link](http://w5j6stm77zs6652pgsij4awcjeel3eco7kvipheu6mtr623eyyehj4yd.onion/wiki/SSH#Key_Generation) | [Clearnet Link](https://www.kicksecure.com/wiki/SSH#Key_Generation)
    ```
    ssh-keygen -o -a 75 -t ed25519
    ```

3. When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

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

7.  Edit these commands as needed, then run them to configure Git. Check ~/.gitconfig file at any time to see the git configuration settings.
    ```
    git config --global user.name "Github Username"
    git config --global user.email githubemail@example.com
    git config --global commit.gpgsign true
    git config --global pull.rebase true
    git config --global user.signingkey XXXPGPKEYHEREXXX
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

TODO: only use this VM for editing, cloning, etc

TODO: mention codium

<br/>

# Git Configuration

COMING SOON ADD GPG KEY to config file

git config --global user.signingkey XXXXXXXXXXX

To sign all commits by default in any local repository on your computer, run:
git config --global commit.gpgsign true

<br/>

Make sure:

    ```
    git config pull.rebase true
    ```

<br/>

# Bash Git Prompt

See: https://github.com/magicmonty/bash-git-prompt

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
