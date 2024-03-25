# Why would you need to read this instruction?

If you want to establish your connection to remote server (here [github](github.com)) without pasting your difficult password or access token. You prefer to work from terminal or your preferred IDE.

# Setup

We will need git and ssh for further work. You can check whether you have it or now.

```shell
git --version
ssh-keygen --help
```

If you are missing something you can install it on

<details>

<summary>Linux</summary>

For Ubuntu/Debian

```shell
# keygen
$ sudo apt-get install openssh-client
```

```shell
# git
$ sudo apt-get install git
```

</details>

<details>

<summary>MacOS</summary>

SSH is installed in MacOS by default, git is too provided with xcode

If you want to install git anyway, you can do it with brew:

```shell
brew install git
```

</details>

# Creating SSH-key

Github already has a [detailed instruction](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) on how to create crate and add SSH key to your account.

If you want more straightforward instruction you can do next steps:

- Use ssh-keygen to create a key and then use .pub it to authorize on github.com

```shell
# Create a key
$ ssh-keygen -t ed25519 -f ~/.ssh/github_ed25519

# You can do not add password for this key, it's not that safe put quite standard.
# In case you added password you will need to remmeber it and paste every time you will use that SSH key

# Show public key in console:
$ cat ~/.ssh/github_ed25519.pub

# Copy whole public key including login@device-name
# Be careull .pub key is public and you can share it but never share private key (without .pub) or other people can authorize on server

```

</details>

<details>

<summary>Image</summary>

[keygen example](pics/keygen.png)

</details>

- go to [github](github.com)

- go to your profile in the upper right corner -> Settings -> SSH and GPG keys -> New SSH key

- add title and paste your key (the one that was displayed in console) and press Add SSH key

</details>

<details>

<summary>Image</summary>

[Add SSH to github](pics/SSH_githb.png)

</details>

- Create SSH Config file on your PC so you could use your new key to authorize on [github](github.com)

```shell
$ cat ~/.ssh/config
Host github.com
    IdentityFile ~/.ssh/github_ed25519
```

You can also just create file or edit config file with your preferred way

In order to check yourself open terminal and do:

<details>

<summary>check SSH authorization</summary>

```shell
$ ssh git@github.com
# You should get something like this
PTY allocation request failed on channel 0
Hi TimuJ! You've successfully authenticated, but GitHub does not provide shell access.
Connection to github.com closed.
```

If you didn't authenticated to github with this command you did something wrong

</details>

# Clone our lab repo

```shell
# Go to folder where you want to store our lab repository it can be anything you want
$ cd <your folder>

# Clone repository from github.com
$ git clone git@github.com:WizardZZH/AiXM-private.git

# Now process of folder downloading should start and you successfully synchronized remote directory on your PC
# Add to git config your login and email so github
$ git config --local user.name "<login from github.com>"
$ git config --local user.email "<email from github.com>"

# Add syncronization from public repository so you can get updates 
$ git remote add upstream git@github.com:WizardZZH/AiXM-private.git

```
