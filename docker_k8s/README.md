# Docker and Kubernetes Installation

## Docker

There is multiple ways to install docker commands.

### Option 1: Docker Desktop (individual/education/small business)

Just follow this [link](https://docs.docker.com/docker-for-mac/).

### Option 2: Rancher Desktop

Rancher Desktop is an alternative to Docker Desktop with no licence risk as employee of a company.  
Just follow this [link](https://rancherdesktop.io/)

### Option 3: Colima

 - [Install colima](https://github.com/abiosoft/colima)
 - [Install docker](https://github.com/abiosoft/colima#docker)
 - [Install kubectl CLI](https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/#install-with-homebrew-on-macos) _(I did chose brew, but there are other options)_

Optionally, you may install [kubectx + kubens](https://github.com/ahmetb/kubectx#homebrew-macos-and-linux)

## ZSH tips

If you are using zsh, you can add **_docker_** and **_kubectl_** plugin as below:

```bash
plugins=(
  git
  docker
  kubectl
)
```
_**TIP:** Here are the available [aliases](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/kubectl#aliases) provided by the plugin_

Edit your .profile to add:

```bash
export KUBECTX_CURRENT_FGCOLOR=$(tput setaf 6) # blue text
export KUBECTX_CURRENT_BGCOLOR=$(tput setab 7) # white background
```

## Kubernetes CLI Interface: K9S

Optionaly you can install a CLI interface for k9s, see this [link](https://k9scli.io/).  
Useful for cusom skins: _On mac (m1), the config directory is `$HOME/Library/Application\ Support/k9s`._  

