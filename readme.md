## Essential Git Commands

- **`git init`**: Initializes a new Git repository in your current directory. This is the first command you'll run for a new project.
- **`git clone <repository_url>`**: Creates a local copy of a remote repository. This is how you get a project that's hosted online (like on GitHub, GitLab, or Bitbucket) onto your computer.
- **`git add <file(s)>`**: Adds changes in your working directory to the staging area. You can use `git add .` to stage all modified and new files, or specify individual files or patterns (e.g., `git add *.txt`).
- **`git commit -m "<commit message>"`**: Records the changes in the staging area to your local repository. The commit message should be concise but descriptive, explaining what changes you've made.
- **`git status`**: Shows the state of your working directory and staging area. It tells you which files have been modified, staged, or are untracked.
- **`git log`**: Displays the commit history of your repository. You can see who made changes, when, and their commit messages. Use flags like `--oneline` for a more compact view or `--graph` to visualize branching.
- **`git branch`**: Lists your local branches. Adding the `-a` flag shows all branches (local and remote).
- **`git checkout <branch_name>`**: Switches to an existing branch. This moves your working directory to the state of the chosen branch.
- **`git checkout -b <new_branch_name>`**: Creates a new branch and immediately switches to it.
- **`git merge <branch_name>`**: Integrates the changes from the specified branch into your currently active branch. You'll often merge feature branches back into your main branch.
- **`git pull <remote_name> <branch_name>`**: Fetches changes from a remote repository and merges them into your current local branch. It's a combination of `git fetch` and `git merge`.
- **`git push <remote_name> <branch_name>`**: Sends your local commits to a remote repository. This allows others to see your changes.
- **`git remote add <remote_name> <repository_url>`**: Creates a new connection to a remote repository. `origin` is a common name for the main remote repository.
- **`.gitignore`**: A file that specifies intentionally untracked files that Git should ignore. This is useful for things like build artifacts, temporary files, or sensitive information.

## Intermediate Git Commands

- **`git diff`**: Shows the differences between various states of your repository.
  - `git diff`: Shows changes in your working directory that are not yet staged.
  - `git diff --staged` (or `git diff --cached`): Shows changes that are staged but not yet committed.
  - `git diff <branch_name>`: Shows the differences between your current branch and another branch.
  - `git diff <commit_hash1> <commit_hash2>`: Shows the differences between two specific commits.
- **`git reset`**: A powerful command used to undo changes. It has different modes:
  - `git reset --soft <commit_hash>`: Moves the HEAD pointer back to the specified commit, but leaves the staging area and working directory unchanged. Your changes are still there and staged.
  - `git reset --mixed <commit_hash>` (default): Moves the HEAD pointer back and unstages the changes. Your changes in the working directory remain.
  - `git reset --hard <commit_hash>`: Moves the HEAD pointer back, unstages changes, and **discards** changes in your working directory. Use this with caution as you can lose work!
- **`git revert <commit_hash>`**: Creates a new commit that undoes the changes introduced by the specified commit. This is a safer way to undo changes in a shared repository as it preserves the history.
- **`git stash`**: Temporarily saves changes you've made in your working directory so you can switch branches or perform other operations without committing incomplete work.
  - `git stash`: Saves your unstaged and staged changes.
  - `git stash save "<description>"`: Saves your changes with a descriptive message.
  - `git stash list`: Shows a list of your stashed changes.
  - `git stash apply`: Reapplies the most recent stashed changes.
  - `git stash apply stash@{<index>}`: Applies a specific stash from the list.
  - `git stash pop`: Applies the most recent stash and removes it from the stash list.
  - `git stash drop stash@{<index>}`: Removes a specific stash from the list.
- **`git branch -d <branch_name>`**: Deletes a local branch. Git will prevent you from deleting a branch that hasn't been merged unless you use `-D` (force delete).
- **`git push origin --delete <branch_name>`**: Deletes a branch on the remote repository (`origin`).
- **`git rebase <branch_name>`**: Integrates changes from one branch into another by replaying the commits of the current branch on top of the target branch. This can create a cleaner, linear history but can be more complex than merging, especially in shared repositories. **Avoid rebasing public branches that others have based their work on.**
- **`git tag`**: Creates markers (tags) at specific points in your repository history, often used to mark releases.
  - `git tag <tag_name>`: Creates a lightweight tag at the current commit.
  - `git tag -a <tag_name> -m "<message>"`: Creates an annotated tag with a message.
  - `git push origin --tags`: Pushes your tags to the remote repository.


## Additional Git Concepts
* **Interactive Rebase:** This powerful tool allows you to manipulate your commit history, such as changing commit messages, deleting or reordering commits, and combining multiple commits.
* **Cherry Picking:** Learn how to select specific commits from one branch and apply them to another, useful when a commit was made on the wrong branch.
* **Reflog:** Discover Git's "diary" that logs every movement of the HEAD pointer, which is invaluable for recovering lost commits or branches.
* **Submodules:** The video explains how to include external libraries or third-party code in your project as separate, nested repositories.
* **Filtering Commit History:** The tutorial covers how to search and filter through your commit history by date, message, author, or file.