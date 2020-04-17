# My Mac developments installation guide

## Start with a good shell
https://www.freecodecamp.org/news/how-to-configure-your-macos-terminal-with-zsh-like-a-pro-c0ab3f3c1156/

## Enable zsh plugins

In your .zshrc file, edit your plugins according to your needs:

```
plugins=(
  git
  docker
)
```

## Create some alias

zsh provide a lot of alias, have a look to their [Cheatsheet](https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet).  

I used to put a few more alias and other stuff on a dedicated file, useful when you switch between shell.  
_Even if I did not switch since I am on zsh..._

```bash
touch ~/.profile
echo "# Add alias" >> ~/.profile
#Put this one in comment since I use `la` alias from zsh...
echo "#alias lla=\"ls -la\"" >> ~/.profile
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
