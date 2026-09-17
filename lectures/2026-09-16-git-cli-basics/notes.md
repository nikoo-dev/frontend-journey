# Lecture — CLI Basics & Intro to Version Control (2026-09-16)

Covered the command line as a developer's working environment, as groundwork
before Git.

**GUI vs CLI:** GUI (Finder/File Explorer) relies on visual elements and mouse
clicks — simple for everyday use but slow for repetitive tasks. CLI uses direct
text commands — faster, more controllable, and the standard interface for
developer tools (Git, npm, build tools) and remote servers.

**Navigation:**
- `pwd` — print current directory
- `ls -la` — list all files in the current directory
- `cd my-app` — move into a folder
- `cd ..` — move up one level

**File operations:**
- `mkdir` — create a new folder
- `touch index.html style.css app.js` — create empty files instantly
- `clear` — clear the terminal screen
- `rm` / `rmdir` — delete files and folders

**Practice:** created a project folder and scaffolded frontend files from the terminal:

```bash
mkdir portfolio
cd portfolio
touch index.html style.css app.js
```

This session set up the terminal fluency needed before diving into Git for version control.
