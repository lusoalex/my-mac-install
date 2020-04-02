# Docker and Kubernetes Installation

Just follow this [link](https://docs.docker.com/docker-for-mac/).

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
