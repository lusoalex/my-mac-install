# My Mac developments installation guide

## Start with a good shell
https://www.freecodecamp.org/news/how-to-configure-your-macos-terminal-with-zsh-like-a-pro-c0ab3f3c1156/

## Create some alias

I used to put my alias and other stuff on a dedicated file, useful when you switch between shell. _Even if I did not switch since I am on zsh..._

```bash
touch ~/.profile
echo "# Add alias" >> ~/.profile
echo "alias lla=\"ls -la\"" >> ~/.profile
echo "alias gst=\"git status\"" >> ~/.profile
```

In your favorite shell, add this: `source ~/.profile` then refresh
```bash
source ~/.zshrc
```


## Install newer git version

```bash
brew install git
git --version
```

## Generate ssh key

ssh-keygen -t rsa -b 4096 -C "email@somewhere.com"

Here I prefer use a specific file such as id_rsa_git, _**that imply to manage a ssh config:**_

```bash
cd ~/.ssh
touch config
```
with

```YAML
#Use specific ssh key for github.com
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_git
```

## Sign commits

Follow this [link](https://help.github.com/en/github/authenticating-to-github/signing-commits)