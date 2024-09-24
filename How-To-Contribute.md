# How To Contribute

## Create Email & Github

1. Use Privatemx (or preferred service) to create an email. [Tor Link](http://privao7wfgfbpf46lytcgla7fn7dcjpomp2djzm3lk3yy3i7zocvn5id.onion) | [Clearnet Link](https://privatemx.org)

2. Sign up for Github and enable 2fa. There is not a Tor .onion for Github at this time.

3. Store all relevant credentials in password manager.

4. Ideally you will never need to use the email address again, but make sure all data is stored in case you need it!

5. You can now interact via Github in your web browser, or continue to the next section to interact via SSH in command line.


## GitHub over Tor-tunneled SSH

1. Make sure you have the necessary dependencies, for example if you are a Debian based Linux user run the following command.
    ```
    sudo apt install gpg netcat-openbsd tor git ssh
    ```

2. Create an ssh key, and see more info about generating new keys here. [Tor Link](http://w5j6stm77zs6652pgsij4awcjeel3eco7kvipheu6mtr623eyyehj4yd.onion/wiki/SSH#Key_Generation) | [Clearnet Link](https://www.kicksecure.com/wiki/SSH#Key_Generation)
    ```
    ssh-keygen -o -a 75 -t ed25519 -C "githubemail@example.com"
    ```

3. When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

4. Rename files. (TODO: Backups)
    ```
    mv ~/.ssh/id_rsa ~/.ssh/sovrepo_rsa
    mv ~/.ssh/id_rsa.pub ~/.ssh/sovrepo_rsa.pub
    ```

5. Create PGP key. (TODO: Backups)
    ```
    gpg --full-generate-key
    # Key type is 1
    # Key size is 4096
    # Set expiry you want
    # Enter name you want
    # Enter email you used for your github account
    # Type secure passphrase and record it in your password manager
    ```

6.  Obtain signing key by running the command below, it will come after the `0x` on the line that starts with `pub`. Keep it for use in step 7 below.
    ```
    gpg --list-keys
    ```

7.  Edit these commands as needed, then run them to configure Git. Check ~/.gitconfig file at any time to see the git configuration settings.
    ```
    git config --global user.name "Github User"
    git config --global user.email githubemail@example.com
    git config --global commit.gpgsign true
    git config --global pull.rebase true
    git config --global user.signingkey XXXPGPKEYHEREXXX
    ```

8. At the prompt, type a secure passphrase, and be sure to store it in your password manager.

9. Add the key to your GitHub account. [Clearnet Link](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)

10. Edit your SSH configuration file.
    ```
    nano ~/.ssh/config
    ```

11. Add this to your `~/.ssh/config` and press Ctrl + X then Y to save. This will forward all SSH commands to github.com through your Tor proxy.
    ```
    Host github.com
    IdentityFile ~/.ssh/sovrepo_rsa
    ProxyCommand nc -X 5 -x localhost:9050 %h %p
    ```

12. Try cloning a repository and if everything looks good try a few other commands. Make sure to always use the SSH variant of GitHub repositories.
    ```
    git clone git@github.com:thesovereignrepo/The-Sovereign-Repository.git
    cd ~/The-Sovereign-Repository
    git status
    git checkout develop
    ls -la
    ```

13. Want to learn more about using Git in command line? Here is a great book. [Clearnet Link](https://git-scm.com/book/en/v2)

<br/>

# Qubes

Qubes users see here. TODO

<br/>
