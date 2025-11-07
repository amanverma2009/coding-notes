# ![ ](../assets/GitHub_light.svg#only-light) ![ ](../assets/GitHub_dark.svg#only-dark) GitHub

## What is GitHub

GitHub is a cloud-based platform for **version control** and **collaboration** built around **Git**. It allows developers to store, track, and manage code changes, work together on projects, and maintain repositories.

## Key Concepts

### 1. **Repository (Repo)**

A repository is a folder where your project files and their version history are stored.
It can be:

- **Public** → visible to everyone.
- **Private** → visible only to you and collaborators.

### 2. **Commit**

A snapshot of your code at a specific time.
Each commit has:

- A **commit message** describing the change.
- A unique **hash ID** for reference.

### 3. **Branch**

Branches allow you to work on different features without affecting the main code.

- **main/master** → stable production version.
- **feature branches** → for new features or bug fixes.

### 4. **Pull Request (PR)**

A request to merge changes from one branch (like `feature`) into another (like `main`).
Used in team projects for:

- Code review
- Discussion
- Testing before merging

### 5. **Merge**

Combining changes from different branches. Usually happens after a pull request is approved.

### 6. **Fork**

A copy of another user’s repository on your own account.
Used to:

- Contribute to open-source projects
- Experiment with code without affecting the original repo

### 7. **Clone**

Download a repository from GitHub to your local machine using:

```bash
git clone <repo-url>
```

### 8. **Remote**

A version of your project hosted on GitHub. The local and remote repositories sync through commands like:

```bash
git push      # Upload changes
git pull      # Download updates
git fetch     # Get changes without merging
```

## Common GitHub Features

### 1. **Issues**

Used to track bugs, enhancements, or tasks.
Each issue can have:

- Labels
- Assignees
- Comments

### 2. **Projects**

Visual boards to organize work (like Kanban or Scrum boards).

### 3. **Actions (CI/CD)**

Automate workflows such as:

- Testing code
- Building projects
- Deploying applications

Example YAML file:

```yaml
name: Node.js CI
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - run: npm install
      - run: npm test
```

### 4. **Discussions**

For community Q&A and brainstorming ideas.

### 5. **Wiki**

A built-in documentation system for repositories.

### 6. **Releases**

Used to package and version software with changelogs and assets.

## GitHub Commands (Basic)

```bash
git init                 # Initialize new Git repo
git clone <url>          # Clone remote repo
git add .                # Stage all changes
git commit -m "message"  # Commit changes
git push origin main     # Push changes to GitHub
git pull origin main     # Pull latest changes
git branch               # List branches
git checkout -b feature  # Create and switch to a new branch
git merge feature         # Merge feature branch into current
```

## GitHub Collaboration Workflow

1. **Fork** the main repository
2. **Clone** it locally
3. **Create** a new branch
4. **Make changes** and commit
5. **Push** branch to GitHub
6. **Create Pull Request**
7. **Wait for review and merge**

## GitHub Profile Features

- **Pinned Repositories:** Highlight top projects.
- **README Profile:** Personal introduction using markdown.
- **Contributions Graph:** Shows daily coding activity.
- **Stars:** Show appreciation for other repos.
- **Followers/Following:** Build a developer network.

## Markdown Example for Profile README

```markdown
# Hi there 👋, I'm [Your Name]

💻 Web Developer | 🚀 Open Source Enthusiast

### 🧠 Skills

- HTML, CSS, JavaScript, React
- Node.js, Python

### 🌱 Currently Learning

Next.js, TypeScript, and API integration

### 📫 Connect with me

[LinkedIn](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)
```

## Benefits of Using GitHub

- Backup and sync code online
- Version control with Git
- Team collaboration tools
- Open-source community support
- Automation and deployment (CI/CD)
- Integration with IDEs and services

## GitHub Desktop

A GUI version of Git that simplifies Git operations (commit, push, pull, etc.) without terminal commands.

## Summary Table

| Concept      | Purpose                     |
| ------------ | --------------------------- |
| Repository   | Store code and history      |
| Branch       | Work on new features safely |
| Commit       | Save project snapshot       |
| Pull Request | Propose and review changes  |
| Fork         | Copy repo for personal use  |
| Clone        | Download repo locally       |
| Issue        | Track bugs and tasks        |
| Actions      | Automate workflows          |
