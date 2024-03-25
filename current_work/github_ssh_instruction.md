# Why would you need to read this instruction?

If you want to establish your connection to remote server (here github.com) without pasting your difficult password or access token. You prefer to work from terminal or your preferred IDE.

# Setup

We will need git and ssh for further work. You can check whether you have it or now.

'''shell
$ git --version
$ ssh-keygen --help
'''

If you are missing something you can install it on

<details>

<summary>Linux</summary>

For Ubuntu/Debian

'''shell
# keygen
$ sudo apt-get install openssh-client
'''

'''shell
# git
$ sudo apt-get install git
'''

</details>

<details>

<summary>MacOS</summary>

SSH is installed in MacOS by default, git is too provided with xcode

If you want to install git anyway, you can do it with brew:

'''shell
$ brew install git
'''

</details>

# Creating SSH-key

Github already has a [detailed instruction](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) on how to create crate and add SSH key to your account
