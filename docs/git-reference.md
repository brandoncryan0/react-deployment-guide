# Git Quick Reference

This page summarizes the Git commands used throughout this guide.

Use it when you need to remember a command without reading through the full deployment procedure.

## Repository Status

```bash
git status
```

Shows the current state of the repository.

Use it to check:

- modified files
- staged files
- untracked files
- current branch

---

## Initialize a Repository

```bash
git init
```

Creates a new local Git repository in the current folder.

Run this once when starting Git tracking for a project.

---

## Stage Changes

Stage all changed files:

```bash
git add .
```

Stage one specific file:

```bash
git add src/App.jsx
```

Staging selects which changes will be included in the next commit.

---

## Create a Commit

```bash
git commit -m "Describe the change"
```

Creates a snapshot of the staged files.

Example:

```bash
git commit -m "Fix mobile navigation"
```

Use short, specific commit messages.

---

## View Commit History

```bash
git log
```

Shows previous commits.

A shorter version is:

```bash
git log --oneline
```

Example output:

```text
6a32f1c Fix mobile navigation
31ab820 Add contact page
11d9ef2 Initial commit
```

Press `q` to exit the full log view if necessary.

---

## View the Latest Commit

```bash
git log -1
```

Shows only the most recent commit.

This is useful when checking whether your latest changes were committed.

---

## View Branches

```bash
git branch
```

Shows local branches.

The active branch is marked with an asterisk:

```text
* main
```

---

## Rename the Current Branch

```bash
git branch -M main
```

Renames the current branch to:

```text
main
```

This is commonly done before the first push to GitHub.

---

## Add a GitHub Remote

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

Connects the local repository to a GitHub repository.

Replace the example URL with the actual repository URL.

---

## View Remote Repositories

```bash
git remote -v
```

Shows the remote addresses configured for the repository.

Example:

```text
origin  https://github.com/USERNAME/REPOSITORY.git (fetch)
origin  https://github.com/USERNAME/REPOSITORY.git (push)
```

---

## Change a Remote URL

```bash
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
```

Use this when the existing `origin` points to the wrong repository.

---

## First Push to GitHub

```bash
git push -u origin main
```

Pushes the local `main` branch to GitHub and connects the local and remote branches.

After the first push, you can usually use:

```bash
git push
```

---

## Push New Commits

```bash
git push
```

Sends committed changes to the connected GitHub repository.

If Vercel is connected to the repository, this can trigger a new deployment.

---

## Download Remote Changes

```bash
git pull
```

Downloads changes from the remote repository and integrates them into the current branch.

Use this when the remote repository contains changes that are not yet on your computer.

---

## Typical Update Workflow

For most website updates:

```bash
git status
git add .
git commit -m "Describe the update"
git push
```

The workflow is:

```text
Edit Files
    ↓
git status
    ↓
git add
    ↓
git commit
    ↓
git push
    ↓
GitHub
    ↓
Vercel
```

## Common Problems

### `remote origin already exists`

Check the existing remote:

```bash
git remote -v
```

If the URL is wrong:

```bash
git remote set-url origin <repository-url>
```

### Nothing to commit

If Git reports:

```text
nothing to commit, working tree clean
```

there are no uncommitted changes.

### Push rejected

If a push is rejected, first check:

```bash
git status
git branch
git remote -v
```

Then confirm that:

- you are on the expected branch
- the remote URL is correct
- you are authenticated with GitHub

## Command Summary

| Command                           | Purpose                         |
| --------------------------------- | ------------------------------- |
| `git init`                        | Create a local repository       |
| `git status`                      | Check repository status         |
| `git add .`                       | Stage all changes               |
| `git commit -m "message"`         | Create a commit                 |
| `git log`                         | View commit history             |
| `git log --oneline`               | View compact commit history     |
| `git branch`                      | View branches                   |
| `git branch -M main`              | Rename current branch to `main` |
| `git remote add origin <url>`     | Connect GitHub repository       |
| `git remote -v`                   | View remotes                    |
| `git remote set-url origin <url>` | Change remote URL               |
| `git push -u origin main`         | First push                      |
| `git push`                        | Push later commits              |
| `git pull`                        | Download remote changes         |

## End of Guide

You now have the complete workflow for moving a React and Vite project from local development to a deployed website using GitHub and Vercel.

When you need a specific procedure again, use the navigation to return to the relevant section.
