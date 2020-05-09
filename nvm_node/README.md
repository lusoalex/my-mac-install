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
# Enable nvm completion & lazy loading settings for zsh-nvm plugin 
export NVM_COMPLETION=true
export NVM_LAZY_LOAD=true

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

## Optional bonus - Newman

_Newman is a command line Collection Runner for Postman. It allows you to run and test a Postman Collection directly from the command line._

I oftenly use [Newman](https://learning.postman.com/docs/postman/collection-runs/command-line-integration-with-newman/) for my postman Non Regression Test collections.  
It is a npm component, so I used to install it by default on my setup...  

```BASH
# Install newman globaly
npm install -g newman
 ```