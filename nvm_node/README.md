# Install nvm (Node Version Manager)

I am using nvm to manage node version and switch according the projects...

## Install nvm

[Nvm](https://github.com/nvm-sh/nvm) is not supporting brew and suggest for zsh user to install it through [zsh-nvm](https://github.com/lukechilds/zsh-nvm) which basically consist in

```bash
# Install plugin into .zsh custom plugin folder
git clone https://github.com/lukechilds/zsh-nvm ~/.oh-my-zsh/custom/plugins/zsh-nvm
```

Then in your ~/.zshrc, add `zsh-nvm` plugin as below:

```bash
# Export nvm completion settings for zsh-nvm plugin 
# Need to pull git@github.com:lusoalex/zsh-nvm.git for now instead...
export NVM_COMPLETION=true

plugins=(
  git
  docker
  kubectl
  zsh-nvm
)
```

Finally source your zsh settings, it will automatically install nvm.

```BASH
# Install plugin into .zsh custom plugin folder
source ~/.zshrc
```

Resulting in:
``` log
Installing nvm...
Clonage dans '/Users/xxxx/.nvm'...
remote: Enumerating objects: 13, done.
remote: Counting objects: 100% (13/13), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 7716 (delta 4), reused 10 (delta 4), pack-reused 7703
Réception d'objets: 100% (7716/7716), 2.61 Mio | 3.33 Mio/s, fait.
Résolution des deltas: 100% (4878/4878), fait.
```

```BASH
# Check your installation
nvm --version
```

## Install node

```BASH
# Install node
nvm install node
```

```BASH
# Check your installation
node --version
nvm --version
```