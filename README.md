# Workspace Development Kit(WDE)
The WDE is designed to be a minimal set of tools that can cater to any and all development needs. It's used for creating environments to undertake development work.

WDE leverages DevPods, Docker and Devcontainers to create reproductable development environments.

## Install
```bash
git clone git@github.com:BrandonC98/wde.git
```

### Windows
1. Install the chocolatey  package manager. https://chocolatey.org/
2. Install tools `choco install -y .\packages.config`
3. Install devcontainer cli `npm install -g @devcontainers/cli`

### MacOS
1. Install tools from the brewfile `brew bundle`

### Credentials
Add SSH keys with access to any needed git repositories to the SSH agent.

### Setting up a provider

Providers are used to define where/how a workspace will run and setting options. Their is offical support for many different providers. Most cloud services are supported like AWS or Azure.


Docker can be setup as a provider using this command. This will run the workspace on a local docker container
```bash
devpod provider add docker
```
#### Resouces on provider
- https://devpod.sh/docs/managing-providers/add-provider

## Quick Start

Create a repository
```bash
gh repo create example-repo --clone --private
```

Get a devcontainer template with the default values.
```bash
cd example-repo
devcontainer templates apply -w . -t ghcr.io/brandonc98/devcontainer-templates/neovim
```
Spin up the devcontainer. Optionally add the `--dotfiles` flag to add dotfiles
```bash
devpod up . --ide none
```

Access the devcontainer
```bash
ssh example-repo.devpod
```

