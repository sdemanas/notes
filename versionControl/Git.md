# Git

- [Core Concepts](#core-concepts)
- [Cheat Sheet](#git-cheat-sheet)
- [Git Configuration](#git-configuration)
- [Starting a Project](#starting-a-project)
- [Day-to-Day Work](#day-to-day-work)
- [Storing Your Work](#storing-your-work)
- [Git Branching Model](#git-branching-model)
- [Inspect History](#inspect-history)
- [Tagging Commits](#tagging-commits)
- [Reverting Changes](#reverting-changes)
- [Synchronizing Repositories](#synchronizing-repositories)
- [Git Installation](#git-installation)
- [Ignoring Files](#ignoring-files)
- [Commit Messages](#commit-messages)
- [Additional Resource](#learning)

---

## Core Concepts

What is Git ?
- Branching
  - Commit
  - Merging
  - Push
  - Pull
  - Sync

---
## Git Cheat Sheet

### Git Configuration

| Command | Description |
|----------|-------------|
| `git config --global user.name "Your Name"` | Set the name that will be attached to your commits and tags. |
| `git config --global user.email "you@example.com"` | Set the e-mail address that will be attached to your commits and tags. |
| `git config --global color.ui auto` | Enable some colorization of Git output. |

### Starting a Project

| Command | Description |
|----------|-------------|
| `git init [project name]` | Create a new local repository in the current directory. If `[project name]` is provided, Git will create a new directory named `[project name]` and initialize a repository inside it. |
| `git clone <project url>` | Download a project with the entire history from the remote repository. |
| `git rm [file]` | Remove file from working directory and staging area. |

### Day-to-Day Work

| Command | Description |
|----------|-------------|
| `git status` | Displays the status of your working directory. Shows new, staged, and modified files, along with branch name and pending commits. |
| `git add [file]` | Add a file to the staging area. Use `.` to add all changed files in the current directory tree. |
| `git diff [file]` | Show changes between working directory and staging area. |
| `git diff --staged [file]` | Show changes between the staging area and the repository. |
| `git checkout -- [file]` | Discard changes in working directory. This operation is unrecoverable. |
| `git reset -<path>--.` | Revert some paths (or the whole index) to their state in `HEAD`. |
| `git commit` | Create a new commit from staged changes. The commit must have a message. |

### Storing Your Work

| Command | Description |
|----------|-------------|
| `git stash` | Put current changes in your working directory into stash for later use. |
| `git stash pop` | Apply stored stash content into working directory, and clear the stash. |
| `git stash drop` | Delete a specific stash from all previous stashes. |

### Git Branching Model

| Command | Description |
|----------|-------------|
| `git branch [-a]` | List all local branches. With `-a`: show all branches (including remote). |
| `git branch [branch_name]` | Create new branch, referencing the current `HEAD`. |
| `git rebase [branch_name]` | Apply commits of the current working branch on top of `[branch_name]` for a linear history. |
| `git checkout [-b] [branch_name]` | Switch working directory to the specified branch. With `-b`: create the branch if it doesn’t exist. |
| `git merge [branch_name]` | Merge the specified branch into your current branch. |
| `git branch -d [branch_name]` | Remove a branch if already merged into another branch. Use `-D` to force deletion. |

### Inspect History

| Command | Description |
|----------|-------------|
| `git log [-n count]` | List commit history of current branch. `-n count` limits to last *n* commits. |
| `git log --oneline --graph --decorate` | Show a condensed history with reference labels and a visual graph. |
| `git log ref-..` | List commits present on the current branch but not merged into `ref`. |
| `git log ..ref` | List commits present on `ref` but not merged into the current branch. |
| `git reflog` | List operations (checkouts, commits, etc.) made on the local repository. |

### Tagging Commits

| Command | Description |
|----------|-------------|
| `git tag` | List all tags. |
| `git tag [name] [commit sha]` | Create a tag reference named `[name]` for the current or specific commit. |
| `git tag -a [name] [commit sha]` | Create an annotated tag object named `[name]` for a commit. |
| `git tag -d [name]` | Remove a tag from the local repository. |

### Reverting Changes

| Command | Description |
|----------|-------------|
| `git reset [--hard] [target reference]` | Switch current branch to the target reference. With `--hard`, discard all uncommitted changes. |
| `git revert [commit sha]` | Create a new commit that reverts the changes introduced by the specified commit. |

### Synchronizing Repositories

| Command | Description |
|----------|-------------|
| `git fetch [remote]` | Fetch changes from remote without updating tracking branches. |
| `git fetch --prune [remote]` | Delete remote refs that were removed from the remote repository. |
| `git pull [remote]` | Fetch changes and merge current branch with its upstream. |
| `git push [--tags] [remote]` | Push local changes to the remote. Use `--tags` to include tags. |
| `git push -u [remote] [branch]` | Push local branch to remote and set it as upstream. |

### Git Installation

| Platform | Instructions |
|-----------|---------------|
| GNU/Linux | Git is available in standard repositories. Example (Debian/Ubuntu):<br>`sudo apt-get install git` |
| From Source | Download and install from [git-scm.com/downloads](https://git-scm.com/downloads). |
| Learning Resource | *Pro Git* by Scott Chacon and Ben Straub, available free at [git-scm.com/book](https://git-scm.com/book). |

### Ignoring Files

| Example `.gitignore` Content | Explanation |
|-------------------------------|-------------|
| ```bash<br>/logs-*<br>!logs/.gitkeep<br>/tmp<br>*.swp<br>``` | To ignore files, create a `.gitignore` file listing patterns. File ignoring works recursively. This example ignores:<br>• All files in `/logs` (except `.gitkeep`)<br>• Entire `/tmp` directory<br>• All files matching `*.swp` |


---
- Git
  - Branching
  - Commit
  - CheckOut
  - Merging
  - Push
  - Pull
  - Sync
---

## Commit Messages

### Conventional Message Types

| Type       | Purpose                                                       | Format Example                        | Example Message                                           |
|------------|---------------------------------------------------------------|----------------------------------------|-----------------------------------------------------------|
| `feat`     | Introduce a new feature                                       | `feat(scope): message`                | `feat(auth): add OAuth2 login`                           |
| `fix`      | Fix a bug                                                     | `fix(scope): message`                 | `fix(api): correct null user check`                      |
| `docs`     | Documentation changes only                                    | `docs(scope): message`                | `docs(readme): update install instructions`              |
| `style`    | Code style changes (no logic impact)                          | `style(scope): message`               | `style(ui): reformat button spacing`                     |
| `refactor` | Code changes (not a fix or feature)                           | `refactor(scope): message`            | `refactor(db): simplify query builder logic`             |
| `perf`     | Improve performance                                           | `perf(scope): message`                | `perf(cache): optimize query results caching`            |
| `test`     | Add or fix tests                                              | `test(scope): message`                | `test(user): add unit tests for registration flow`       |
| `chore`    | Misc. tasks (e.g., build tools, configs, version bumps)       | `chore(scope): message`               | `chore(deps): update Moq to v4.16.1`                     |
| `build`    | Changes to build system or dependencies                       | `build(scope): message`               | `build(gradle): update compileSdkVersion`                |
| `ci`       | CI/CD configuration changes                                   | `ci(scope): message`                  | `ci(github): add PR labeler workflow`                    |



### Breaking Changes

| Usage             | Format                     | Example                                                                 |
|------------------|----------------------------|-------------------------------------------------------------------------|
| In subject        | `type(scope)!: message`    | `feat(api)!: change response structure`                                |
| In footer         | `BREAKING CHANGE:`         | `BREAKING CHANGE: removed legacy login method. Use /auth/login instead.`|



### Issue References in Footer

| Purpose             | Format              | Example               |
|---------------------|---------------------|------------------------|
| Close an issue      | `Closes: #123`      | `Closes: #456`         |
| Fix a bug/issue     | `Fixes: #123`       | `Fixes: #789`          |
| Reference issue     | `Refs: #123`        | `Refs: #101112`        |


---

# Learning

Would highly recommend visiting this website and practising your git skills in a gamified manner:
[Learn Git Branching](https://learngitbranching.js.org/)

