# Devcontainer

## Creating a devcontainer
There are multiple ways to create a devcontainer file.
- Use a template
- Write your own

### Use a template
Find a template you would like to use then apply the template.

```bash
devcontainer templates apply -w <PATH_TO_WORKSPACE> -t <TEMPLATE_URL>
```

You can change the defaults values in a template by adding the `--template-args`/`-a` flag and providing a json list of the fields and the new values.
```bash
devcontainer templates apply -w ./project4 -t ghcr.io/BrandonC98/devcontainer-templates/neovim -a '{\"neovimConfig\": \"https://github.com/LazyVim/starter\"}'
```

#### Template Repositories
- https://github.com/BrandonC98/devcontainer-templates
- https://github.com/devcontainers/templates
- https://containers.dev/templates

#### Useful Template Resources
- https://github.com/devcontainers/template-starter
- https://containers.dev/implementors/templates/

### Write your own
Devcontainer can be written in json to define the container.

Example `.devcontainer.json` file.
```json
{
  "image": "mcr.microsoft.com/devcontainers/typescript-node",

  "customizations": {
    "vscode": {
      "extensions": ["streetsidesoftware.code-spell-checker"]
    }
  },
  "forwardPorts": [3000]
}
```

#### Useful resources for writing devcontainer files
- https://containers.dev/implementors/json_reference/

## Devcontainer Debugging Commands

build and run the container
```bash
devcontainer up --workspace-folder .
```

exec into the container
```bash
devcontainer exec --workspace-folder . /bin/bash
```