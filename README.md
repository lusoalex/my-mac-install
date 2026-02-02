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

**Tip:** If you are working with developers using Windows, according to this [documentation](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration) then you should run this:

```bash
git config --global core.autocrlf input
````

And request developers using Windows to set this:
```bash
git config --global core.autocrlf true
````

*This will unify end of lines in LF mode, please read the official [documentation](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)  for more details.*


## Generate ssh key

ssh-keygen -t rsa -b 4096 -C "email@somewhere.com"

Here I prefer use a specific file such as id_rsa_git, _**that imply to manage a ssh config:**_

```bash
# first create the key
ssh-keygen -t ed25519 -C "your_email@exemple.com" -f ~/.ssh/id_ed_git

cd ~/.ssh
touch config
```
with

```YAML
# Use specific ssh key for github.com: ssh-keygen -t ed25519 -C "your_email@exemple.com" -f ~/.ssh/id_ed_git
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed_git
  AddKeysToAgent yes
  UseKeychain yes
```

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@exemple.com"
```

Now add you key in your github account...

## Sign commits

Follow this [link](https://help.github.com/en/github/authenticating-to-github/signing-commits)
