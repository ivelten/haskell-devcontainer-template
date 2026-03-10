# haskell-dev-base

A dev container template for Haskell development.

## What's included

| Component | Version |
| ----------- | --------- |
| GHC | 9.6.7 |
| Cabal | 3.10.3.0 |
| Haskell Language Server (HLS) | 2.12.0.0 |

**Shell:** Zsh (default)

**System tools:** `build-essential`, `curl`, `git`, `pkg-config`, `libffi-dev`, `libgmp-dev`, `libssl-dev`, `zlib1g-dev`, `direnv`, `socat`, `procps`

**VS Code extensions installed automatically:**

- [Haskell](https://marketplace.visualstudio.com/items?itemName=haskell.haskell) — HLS integration
- [Haskell Syntax Highlighting](https://marketplace.visualstudio.com/items?itemName=justusadam.language-haskell)
- [GHCi](https://marketplace.visualstudio.com/items?itemName=eriksik2.vscode-ghci)
- [direnv](https://marketplace.visualstudio.com/items?itemName=mkhl.direnv)
- [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)
- [EditorConfig](https://marketplace.visualstudio.com/items?itemName=editorconfig.editorconfig)
- [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
- [markdownlint](https://marketplace.visualstudio.com/items?itemName=davidanson.vscode-markdownlint)

## Prerequisites

- [Docker](https://www.docker.com/products/docker-desktop)
- [VS Code](https://code.visualstudio.com/) with the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Using this template

1. Click **Use this template** on GitHub to create a new repository from this template.
2. Clone your new repository and open it in VS Code.
3. When prompted, click **Reopen in Container** (or run the command `Dev Containers: Reopen in Container`).
4. The container will build and run the post-creation setup automatically. This may take several minutes on first build.

## Project structure

```text
.
├── .devcontainer/
│   ├── devcontainer.json   # Dev container configuration
│   ├── docker-compose.yml  # App services
│   ├── Dockerfile          # Haskell toolchain setup
│   └── post-create.sh      # Post-creation setup script
├── .editorconfig           # Consistent editor formatting rules
└── .gitignore              # Haskell, Cabal, and VS Code ignores
```

## Customising the template

**Changing GHC or HLS versions:** Update the version variables in `.devcontainer/Dockerfile` and update the versions mentioned in `.devcontainer/post-create.sh` welcome message accordingly.

**Changing Cabal version:** Update `BOOTSTRAP_HASKELL_CABAL_VERSION` in `.devcontainer/Dockerfile`.

**Adding Cabal packages as dependencies:** Create a `cabal.project` and `.cabal` package file at the root of the repository after cloning the template.

**Using direnv for per-project environment variables:** Add a `.envrc` file to the project root. direnv is pre-installed and hooked into both Bash and Zsh.
