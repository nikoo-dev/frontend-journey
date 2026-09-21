# Lecture — Git & GitHub Fundamentals (2026-09-19)

## Installing & configuring Git

Covered installing Git on Windows (via Git Bash, choosing VS Code as the
default editor instead of Vim to avoid getting stuck mid-commit, and leaving
line-ending settings at their recommended defaults) and on macOS (via Homebrew
or Apple's bundled Git through `xcode-select --install`).

Verified the install with `git --version`, and set up global config:

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --global init.defaultBranch main
git config --list
```

Key point: `--global` settings apply once per machine, across all repos — and
the email should match the one used on GitHub, since every commit is attributed
to it.

## Why version control at all?

Before Git, the "manual" approach was duplicating files with names like
`final_v1`, `final_v2` — messy and error-prone. Git instead tracks full
history of changes over time, so nothing is ever really lost, and mistakes can
be undone.

## Git vs GitHub

- **Git** — a local tool. Runs on your machine, works offline, and takes
  full snapshots of your project's state.
- **GitHub** — a cloud platform. Hosts your repo remotely, enables
  collaboration (pull requests, code review), and acts as a backup of your
  local work.

## The three zones

Git moves changes through three stages:

1. **Working Directory** — your actual project folder, where files are
   created/edited/deleted.
2. **Staging Area (Index)** — a "packing box" — `git add` puts only the
   changes you're ready to commit here.
3. **Repository (.git)** — the permanent, versioned history — `git commit`
   seals the staged changes into a snapshot.

```bash
git add index.html
git restore --staged index.html   # undo a mistaken add
git commit -m "feat: complete navigation bar"
```

Staging lets you commit selectively — e.g. change 5 files but only commit 2,
keeping the rest for later.

## File states

A file moves through four states, visible via `git status`:

1. **Untracked** — brand new, Git sees it but isn't tracking history yet
2. **Staged** — added via `git add`, ready for the next commit
3. **Unmodified** — committed and matching the last snapshot exactly
4. **Modified** — edited since the last commit, not yet re-staged

```bash
git status                     # Untracked files: about.html
git add about.html
git status                     # Changes to be committed: new file: about.html
git commit -m "feat: add about page"
git status                     # nothing to commit, working tree clean
# edit the file...
git status                     # Changes not staged for commit: modified: about.html
```

## Pushing to GitHub

```bash
git branch -M main
git remote add origin git@github.com:username/repo.git
git push -u origin main
```

`-u` links the local branch to the remote one so future pushes can just be
`git push`.
