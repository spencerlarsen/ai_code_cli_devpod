# AI Coding Agents DevPod Template

Run AI coding agents safely inside Docker containers using DevPod.

AI coding agents are powerful. Running them unconstrained on your computer is risky. This template runs them within Docker containers to mitigate the risk of data loss or corruption from hallucinations.

[DevPod](https://devpod.sh/) is an open source alternative to GitHub Codespaces. It lets you spin up development containers from a `.devcontainer` configuration with a single command.

## Prerequisites

(Skip if you've done this before)

1. [Install Docker](https://docs.docker.com/engine/install/)
2. [Install DevPod CLI](https://devpod.sh/docs/getting-started/install#install-devpod-cli)
3. Add Docker to DevPod as the default provider:
```bash
devpod provider add docker
devpod provider use docker
```

## Quick Start

1. Clone this repository and `cd` into it
2. Run `devpod up . --ide vscode`

That's it! Claude Code, Codex CLI, and Gemini CLI are automatically installed and ready to use.

## What's Included

### AI Coding Agents
- **Claude Code** - Anthropic's AI coding assistant (auto-installed)
- **OpenAI Codex CLI** - OpenAI's AI coding agent (auto-installed)
- **Gemini CLI** - Google's Gemini CLI (auto-installed)
- **Gemini Code Assist** - Google's AI coding assistant with real-time code completion and chat (auto-installed)
- **GitHub Copilot** - GitHub's AI pair programmer pre-configured with all permissions enabled for sandboxed development (requires active subscription)
- **GitHub Copilot CLI** - Terminal-based AI assistant for shell commands and code explanations (auto-installed, requires authentication)

### Development Tools
- **Python** + **uv** - Python with fast package management
- **Rust** - Full Rust toolchain with rust-analyzer
- **Node.js** - JavaScript runtime
- **Git** + **GitHub CLI** - Version control

## Using the AI Coding Agents

Once the container opens in VS Code:

### Claude Code

```bash
# Start with all permissions (recommended for containers)
claude --dangerously-skip-permissions

# Or start with normal permissions
claude
```

### OpenAI Codex CLI

```bash
# Start in yolo mode - no approvals or sandbox (recommended for containers)
codex --yolo

# Or start with normal permissions
codex
```

### Gemini CLI

```bash
# Start in yolo mode - no approvals or sandbox (recommended for containers)
gemini --yolo

# Or start with normal permissions
gemini
```

### GitHub Copilot CLI

```bash
# Start in permissive mode - no approvals or sandbox (recommended for containers)
copilot --allow-all

# Or start with normal permissions
copilot
```

## Customization

Edit `.devcontainer/devcontainer.json` to customize your environment:

- Change the base image (Debian, Fedora, etc.)
- Add/remove language features (Julia, Go, etc.)
- Add VS Code extensions
- Modify the setup script in `.devcontainer/setup.sh`

See [devcontainer features](https://containers.dev/features) for available options.

## How It Works

The `.devcontainer/` folder contains:
- `devcontainer.json` - Container configuration with VS Code extensions
- `setup.sh` - Post-creation script that installs Claude Code, Codex CLI, Gemini CLI, and uv

VS Code extensions included by default:
- Claude Code
- Codex
- Gemini CLI Companion
- Gemini Code Assist
- GitHub Copilot (with Chat)

The `.claude/settings.json` file pre-configures Claude Code to bypass permission prompts (safe within containers). 
GitHub Copilot is pre-configured with all permissions enabled for all file types, providing seamless AI assistance in the sandboxed environment. 
The GitHub Copilot CLI is also installed for terminal-based AI interactions, offering command suggestions and explanations directly from your shell. 
Gemini Code Assist provides additional AI-powered code completion and documentation features.

## See Also

* [Claude Code DevPod template for Python only](https://github.com/jusevitch/claude_code_python)
* [Claude Code DevPod template for Rust only](https://github.com/jusevitch/claude_code_rust)

## Resources

- [DevPod Documentation](https://devpod.sh/docs)
- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [OpenAI Codex CLI Documentation](https://developers.openai.com/codex/cli/)
- [Devcontainer Features](https://containers.dev/features)
- [Microsoft Devcontainer Images](https://hub.docker.com/r/microsoft/devcontainers)
