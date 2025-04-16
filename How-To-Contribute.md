# How To Contribute

## Table of Contents
* [1. Create Email](#create-email)
* [2. Create Github](#create-github-account)
* [3. Github SSH](#github-over-tortunneled-ssh)
* [4. Github Qubes](#qubes-github-ssh)


## Create Email

1. Use Privatemx (or preferred service) to create an email. [Tor Link](http://privao7wfgfbpf46lytcgla7fn7dcjpomp2djzm3lk3yy3i7zocvn5id.onion) | [Clearnet Link](https://privatemx.org)

2. Make sure to use the Tor browser!

3. Store the email credentials in your password manager.

## Create Github Account

1. Using the Tor Browser, sign up for Github using the email you just created.

2. Go to security settings, enable 2FA, and enable private email.

3. Store all Github credendtials in your password manager.

4. You should never need to use the email address again, but make sure all data is stored in case you need it!

5. You can now interact via Github in your web browser, or continue to the next section to interact via SSH in command line.

6. Need to report something? Use Github to open and Issue and make your voice heard! [Clearnet Link](https://github.com/thesovereignrepo/The-Sovereign-Repository/issues)

<br/>

## GitHub over Tor-tunneled SSH

For users of Debian based Linux (Tails, Ubuntu, PopOS), learn to interact with the repo via command line.

**NOTE:** This example process retains any current git configuration and will not interfere with it, while adding another one for The Sovereign Repository.

1. Make sure you have the necessary dependencies, for example if you are a Debian based Linux user run the following command.
    ```
    sudo apt install gpg netcat-openbsd tor git ssh
    ```

2. Create a SSH sovrepo directory for keys:
    ```	
   mkdir ~/.ssh/sovrepo
   chmod 700 ~/.ssh/sovrepo
   ```

3. Create an ssh key, and see more info about generating new keys here. [Tor Link](http://w5j6stm77zs6652pgsij4awcjeel3eco7kvipheu6mtr623eyyehj4yd.onion/wiki/SSH#Key_Generation) | [Clearnet Link](https://www.kicksecure.com/wiki/SSH#Key_Generation)
	```
	ssh-keygen -o -a 75 -t ed25519
	```

4. When you're prompted to "Enter a file in which to save the key," press `Enter`. This accepts the default file location of `~/.ssh`.

5. Move files and rename them.
    ```
	mv ~/.ssh/id_ed25519 ~/.ssh/sovrepo/sovrepo_rsa
	mv ~/.ssh/id_ed25519.pub ~/.ssh/sovrepo/sovrepo_rsa.pub
	```

6. Create PGP key.
    ```
    gpg --full-generate-key
    # Key type is 1
    # Key size is 4096
    # Set expiry you want
    # Enter name you want
    # Enter email you used for your github account
    # Type secure passphrase and record it in your password manager
    ```

7. Copy the alphanumeric value that comes after `0x`. It will be used for the `user.signingkey` value in step 9 below.
    ```
    gpg --list-keys | grep "pub"
    ```

8. Create a project directory for sovrepo
    ```
    mkdir ~/projects/sovrepo/
    cd ~/projects/sovrepo/
    ```

9. Edit to create a project specific .gitconfig
    ```
    nano ~/projects/sovrepo/.gitconfig
    ```

    Add this and press Ctrl + X then Y to save.
    ```
    [user]
            name = "Github Username"
            email = githubemail@example.com
            signingkey = PASTE-KEY-FROM-STEP-7  
    [commit]                                                                                                                                                                                           
            gpgsign = true 
    [pull]                                                                                                                                                                                             
            rebase = true
    ```

10. Copy your SSH and GPG public keys.
    ```
    cat ~/.ssh/sovrepo/sovrepo_rsa.pub
    gpg --export --armor githubemail@example.com
    ```

11. Add your SSH and GPG public keys to your GitHub account. [Clearnet Link](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)


12. Edit your SSH configuration file. 
    ```
    nano ~/.ssh/config
    ```

13. Add this to your ~/.ssh/config and press Ctrl + X then Y to save. This will add a section for github.com default (for your other github projects) and an alias section for sovrepo that will forward SSH commands to sovrepo through your Tor proxy.
    ```
    #
    # Default GitHub
    #
    Host github.com
      HostName github.com
      User git
      IdentityFile ~/.ssh/id_rsa
    
    #
    # sovrepo
    # example: git clone git@sovrepo:thesovereignrepo/The-Sovereign-Repository.git
    #
    Host sovrepo
      HostName github.com
      IdentityFile ~/.ssh/sovrepo/sovrepo_rsa
      ProxyCommand nc -X 5 -x localhost:9050 %h %p
    ```  

14. Make sure to always use the SSH alias (@sovrepo) variant for sovrepo GitHub repositories when you go to clone. Try cloning a repository and if everything looks good try a few other commands. 
    ```
    git clone git@sovrepo:thesovereignrepo/The-Sovereign-Repository.git
    cd ~/The-Sovereign-Repository
    git status
    git checkout develop
    ls -la
    ```

15. Want to learn more about using Git in command line? Here is a great book. [Clearnet Link](https://git-scm.com/book/en/v2)

<br/>

## Qubes Github SSH

Qubes users see this [Qubes Dev Environment](https://github.com/thesovereignrepo/The-Sovereign-Repository/blob/master/01-Desktop/04-Hardcore/04-Qubes-Dev-Environment.md#github-over-tor-tunneled-ssh) guide.

<br/>

## Backup Keys

TODO: GPG and SSH backup info

<br/>
