# ![ ](../assets/git-logo.svg) Git

## What is Git?

Git is a **distributed version control system (VCS)** used to track changes in source code during software development. It allows multiple developers to collaborate efficiently by managing versions of code and merging updates seamlessly.

## Key Features of Git

- **Distributed System:** Every developer has a local copy of the repository.
- **Version Tracking:** Tracks every change made to files.
- **Branching & Merging:** Enables developers to create independent branches for new features and merge them later.
- **Collaboration:** Facilitates teamwork through remote repositories like GitHub, GitLab, or Bitbucket.
- **Data Integrity:** Uses SHA-1 hashing to ensure code integrity.
- **Lightweight & Fast:** Most operations are done locally, ensuring speed.

## Basic Git Terminology

| Term | Description |
| | -- |
| **Repository (Repo)** | A project folder tracked by Git containing all files and their history. |
| **Commit** | A snapshot of changes made to the code. |
| **Branch** | A separate line of development for new features or experiments. |
| **Merge** | Combining changes from one branch into another. |
| **Clone** | Copying a remote repository to your local system. |
| **Pull** | Fetching and merging changes from a remote repo. |
| **Push** | Uploading local commits to a remote repo. |
| **Staging Area** | Temporary area where changes are prepared before committing. |
| **Remote** | A version of the repository hosted online. |

## Git Workflow

1. **Clone or Initialize Repository**

   ```bash
   git clone <repo-url>
   # or
   git init
   ```

2. **Make Changes**
   Edit or create files.
3. **Check Status**

   ```bash
   git status
   ```

4. **Add to Staging Area**

   ```bash
   git add <filename>
   # or all files
   git add .
   ```

5. **Commit Changes**

   ```bash
   git commit -m "Describe your changes"
   ```

6. **Push to Remote**

   ```bash
   git push origin main
   ```

7. **Pull Latest Updates**

   ```bash
   git pull origin main
   ```

## Branching in Git

### Create a Branch

```bash
git branch feature-xyz
```

### Switch to Branch

```bash
git checkout feature-xyz
```

### Merge Branch

```bash
git checkout main
git merge feature-xyz
```

### Delete Branch

```bash
git branch -d feature-xyz
```

## Viewing History

- **Commit Log**

  ```bash
  git log
  ```

- **Short Log**

  ```bash
  git log --oneline
  ```

- **Show Changes**

  ```bash
  git diff
  ```

## Undoing Changes

- **Unstage a File**

  ```bash
  git reset <file>
  ```

- **Undo Last Commit (Keep Changes)**

  ```bash
  git reset --soft HEAD~1
  ```

- **Discard Local Changes**

  ```bash
  git checkout -- <file>
  ```

## Working with Remote Repositories

### Add Remote

```bash
git remote add origin <repo-url>
```

### View Remotes

```bash
git remote -v
```

### Push Changes

```bash
git push origin main
```

### Fetch Remote Changes

```bash
git fetch origin
```

## Common Git Commands Summary

| Command | Description |
| - | |
| `git init` | Initialize a new Git repository |
| `git clone <url>` | Clone a remote repository |
| `git status` | Check status of working directory |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save changes |
| `git push` | Upload commits to remote |
| `git pull` | Download and merge remote changes |
| `git branch` | List branches |
| `git checkout <branch>` | Switch branches |
| `git merge <branch>` | Merge branch into current |
| `git log` | View commit history |

## .gitignore

A special file used to tell Git which files/folders to **ignore** (not track).
Example:

```text
node_modules/
.env
*.log
```

## Git Configurations

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --list
```

## Git Stash

Temporarily saves uncommitted changes.

```bash
git stash
git stash list
git stash pop
```

## Git Rebase

Reapply commits on top of another base branch (used to clean commit history).

```bash
git rebase main
```

## Git Tag

Mark specific commits as versions.

```bash
git tag v1.0
git push origin v1.0
```
