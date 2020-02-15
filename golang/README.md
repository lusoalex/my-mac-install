# Install golang

## Install go

Install newer version of go

```bash
brew install go
```

### Go paths

Add paths in your .bashrc or .zshrc. Personally I add this in my ~/.profile which is sourced by zshrc

```bash
# Go development
export GOPATH="${HOME}/.go"
export GOROOT="$(brew --prefix golang)/libexec"
export PATH="$PATH:${GOPATH}/bin:${GOROOT}/bin"
```
