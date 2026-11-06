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

## Bulk commits

`bgitpush` generates one concise commit subject per changed repository using Codex,
then commits and pushes in parallel. `bgitpush 'message'` uses the supplied message
without calling Codex. The third column shows the subject and commit count.

Automatic messages use `gpt-6.1-sol` with low reasoning and a self-contained staged
snapshot: summary, diff, and complete changed text files. Binary changes and deleted
files are identified without binary contents. Inputs over 128 KiB fall back to a bounded summary of filenames, change types
and line counts. Generation failures leave changes staged. Generation errors include the location of their retained log.
