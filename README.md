# 🛠 Personal Shell Scripts

This directory contains modular, clean, and conflict-free personal shell scripts, aliases, functions, and tools.

## Structure

| File/Dir         | Purpose                                      |
|------------------|----------------------------------------------|
| `aliases`        | Universal aliases (ls, cd, etc.) — no python, pip, git here |
| `common`         | Common reusable settings (shared utilities) |
| `functions`      | Personal functions (video, audio, debug, system) |
| `git-functions`  | Git-specific functions (push, open, hooks)   |
| `git-hooks`      | Git hooks templates (copied by `git_set_hooks`) |
| `vnv`            | VNV manager (env creation, activation, safety wrappers) |

## Usage

In your `~/.zshrc`:

```bash
# Load common shell settings
source ~/scripts/common

# Load universal aliases
source ~/scripts/aliases

# Load personal functions
source ~/scripts/functions

# Load git-specific functions
source ~/scripts/git-functions

# Load model commands
source ~/scripts/llm

# Load VNV manager (must be last to override python, pip, etc.)
source ~/scripts/vnv
```

## Philosophy
- 🛡 Safe and predictable: Functions always override aliases.
- 🗃 Modular: Git, vnv, general tools — separated into clear files.
- 🧹 Clean environment: No company-specific or sensitive info inside this folder.
- 🎨 Portable: Can be reused or shared freely.
