# Git and GitHub Notes

## 1. What is Git?

Git is a **distributed version control system** that tracks changes in source code and helps teams collaborate on projects.

- Created by Linus Torvalds
- CLI-based, fast, and efficient
- Works offline

## 2. What is GitHub?

GitHub is a **cloud-based hosting service** for Git repositories. It adds collaboration features like pull requests, issues, and CI/CD.

## 3. Install and Configure Git

Install Git from: [git website](https://git-scm.com)

Initial setup:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
````

Check config:

```bash
git config --list
```

## 4. Basic Commands

```bash
git init            # Initialize a new repo
git status          # Show file status
git add <file>      # Stage file
git commit -m "msg" # Commit staged changes
git log             # View commit history
```

Stage all files:

```bash
git add .
```

## 5. Working with GitHub

### Create a Repository

1. Create a new repo on GitHub (don't initialize with README)
2. In terminal:

```bash
git remote add origin https://github.com/user/repo.git
git branch -M main
git push -u origin main
```

## 6. .gitignore

Use `.gitignore` to exclude files/folders from being tracked.

Example:

```
node_modules/
.env
.DS_Store
```

## 7. Cloning Repositories

```bash
git clone https://github.com/user/repo.git
```

## 8. Branching

```bash
git branch         # List branches
git branch dev     # Create branch
git switch dev     # Switch branch (or: git checkout dev)
git merge dev      # Merge dev into current branch
```

Delete a branch:

```bash
git branch -d dev
```

## 9. Handling Merge Conflicts

When two branches modify the same line:

```bash
<<<<<<< HEAD
your version
=======
incoming version
>>>>>>> dev
```

Resolve manually, then:

```bash
git add .
git commit
```

## 10. Undoing Changes

Discard unstaged changes:

```bash
git restore <file>
```

Unstage a file:

```bash
git reset <file>
```

Reset entire repo:

```bash
git reset --hard HEAD
```

Revert a commit (safe):

```bash
git revert <commit-hash>
```

## 11. Stashing Changes

Temporarily save work:

```bash
git stash
git stash list
git stash apply
git stash pop
```

## 12. Working with Remotes

```bash
git remote -v                # Show remotes
git remote add origin <url>  # Add remote
git push origin main         # Push to remote
git pull origin main         # Pull latest
```

## 13. Pull Requests (PRs)

1. Push branch to GitHub
2. Click "Compare & Pull Request"
3. Add title, description, reviewers
4. Merge after approval

## 14. Fork vs Clone

- **Fork**: Your own copy of someone else’s repo (for contributing)

- **Clone**: Local copy of any repo (for development)

## 15. Tags and Releases

```bash
git tag v1.0
git tag -a v1.1 -m "Version 1.1"
git push origin --tags
```

Use tags on GitHub to create releases.

## 16. Rebase (Advanced)

```bash
git rebase main         # Rebase current branch onto main
git rebase -i HEAD~3    # Interactive rebase last 3 commits
```

Squash commits by choosing `s` for all except the first.

## 17. Authentication Methods

### HTTPS with Token:

```bash
git remote set-url origin https://<token>@github.com/user/repo.git
```

### SSH:

1. Generate key:

```bash
ssh-keygen -t ed25519 -C "you@example.com"
```

2. Add public key to GitHub → Settings → SSH & GPG

3. Test:

```bash
ssh -T git@github.com
```

## 18. Git Tools

- **GitHub Desktop** – GUI for GitHub workflows
- **Sourcetree**, **GitKraken** – Git GUI clients
- **GitLens (VS Code)** – Git insights in editor

## 19. Git Hooks (Optional)

Automate actions on Git events:

Example: `.git/hooks/pre-commit`

```bash
#!/bin/sh
npm run lint
```

Make it executable:

```bash
chmod +x .git/hooks/pre-commit
```

## 20. Best Practices

- Commit often with meaningful messages
- Use `.gitignore` to avoid committing unwanted files
- Use branches for features/fixes
- Don’t commit secrets (use `.env`)
- Resolve merge conflicts carefully
- Keep pull requests small and focused
- Never force push to `main` unless you know what you’re doing

## Commit Message Format

Use present tense, short, descriptive messages:

```bash
git commit -m "Add contact form validation"
```

Prefix (optional): `feat`, `fix`, `docs`, `refactor`, `test`, etc.

## Summary Cheatsheet

| Command                | Description             |
| ---------------------- | ----------------------- |
| `git init`             | Start new repository    |
| `git clone <url>`      | Clone a repo            |
| `git status`           | Show status             |
| `git add .`            | Stage all changes       |
| `git commit -m ""`     | Commit changes          |
| `git push origin main` | Push to GitHub          |
| `git pull origin main` | Pull latest from GitHub |
| `git branch <name>`    | Create new branch       |
| `git switch <branch>`  | Switch branch           |
| `git merge <branch>`   | Merge into current      |
| `git log`              | Show commit history     |
| `git stash`            | Save uncommitted work   |
| `git tag v1.0`         | Create version tag      |
