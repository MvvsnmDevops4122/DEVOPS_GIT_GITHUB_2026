#  Step-by-Step Git Setup

## Step 0: Install Git Bash

Download and install Git from: 
```
 https://git-scm.com/
```
## Step 1: Check Git Version

```
git --version

# or

git -v

```

## Step 2: Create a Project Folder

```
cd ~/OneDrive/Desktop
mkdir jio
cd jio
```

## Step 3: Initialize Git Repository

```
git init

```

## Step 4: View Hidden Files

```

ls -la

```

## Step 5: Explore the .git Directory

```

cd .git
ls -lrth
cd ..

```

---

#  Basic Git Commands

## 1. Install Git

```

yum install git -y          # Install Git
git --version               # Check Git version
git init                    # Initialize Git repo in a directory

```

---

## 2. Git Add (Tracking Files)

```

git add filename            # To track the file (working directory to staging area)
git add *                   # Adds only visible (non-hidden) files from the current folder. Skips hidden files and files inside subfolders.
git add .                   # Adds all files — new, modified, including hidden files and files inside subfolders.
git rm --cached filename    # Untrack a file

```

---

## 3. Git Status

```

git status                  # Check tracked and untracked files

```

---

## 4. Git Config (Username & Email)

* Before making any commits, you should configure your Git username and email.

```
git config --global user.name "MvvsnmDevops4122"           # Set your Git user name
git config --global user.email "satyaandhu2389@gmail.com"  # Set your Git user email
git config --global --list                                 # View global Git settings
git config --list                                          # View all Git settings (local + global + system)

```

---

## 5. Git Commit (Saving Work)

```

git commit -m "message" filename     # Commit a specific file
git commit -m "message" .            # Commit all staged files
git commit -am "Updated"             # Commit modified files without git add

```
a - automatically

Working directory -----------> local repository

(When modified the existing file to commit the changes without add git add)

git commit -am does NOT work for new or untracked files.It only stages and commits files that are already tracked by Git.

---

## 6. Git Log (Commit History)

```

git log                              # To see commit details/ commit history
git log -1                           # Latest commit
git log -2                           # Latest 2 commits
git log --oneline                    # Used to get short commit ID's and commit message
git log --pretty=oneline             # Used to get full commit ID's and commit message
git log --follow --oneline --all     # History of a single file

```

---

## 7. Git Show (Commit Details)

```

git show commit-id                   # To see the full details of the commit.
git show commit-id --name-only       # To see commit details along with file names
git show --pretty="" --name-only     # Same output (only file names)

```

---

##  8. Connect Local Repo to Remote Repository (GitHub)

* Before pushing your changes, always make sure your local branch is updated with the latest code from the remote repository.

```

git remote add origin(alish name) <repo_url>     # Connect local repo to GitHub
git remote -v                                    # Verify remote connection/Used to check github repository connect or not
git pull --rebase origin branch                  # gets latest code from github and applies your new commits on top of it.
git push origin branch-name                      # Push the code from local repo to remote repository
git remote rename origin <alias>                 # Rename the alias name
git push <alias> --all                           # Push all branches/push all branches from local repo to remote repo
git remote remove <repo_url>                     # Remove the connection
git clone <repo_url>                             # Clones a repository from a remote URL to your local machine

```

---
## **10. Git Reset (Unstage Files)**

```bash
git reset                            # Unstage all files/Moves all staged files back to working area
git reset filename                   # Unstage one file/Moves only the specified file
git reset .                          # Unstage everything including hidden files/To unstage all the files including hidden ones
```

---

## **11. Git Clean (Remove Untracked Files)**

* Removing files from the working directory

```bash
git clean -n                         # Dry run – shows which files will be deleted
git clean -f                         # Forcefully deletes all untracked files
git clean -f filename                # Forcefully deletes particular untracked file.
```

---

## **12. Git Revert (Undo a Commit With a New Commit)**

```bash
git revert <commit-id>        #creates a new commit to undo the changes made by a specific commit.
```

📌 Examples:

* **Revert new file commit:** Delete the file
* **Revert updated file commit:** Undo the change inside the file

                         revert
EX: New file (commit)  ------------> delete the file

                            revert
  Updated File (commit) -----------> Delete only data inside the file
  
---
### Git Revert (Undo Pushed Changes)

📌 Command
```bash
git revert HEAD
git push origin main

```
📖 Description
git revert HEAD → Undo last commit
Creates a new commit to reverse changes
git push origin main → Update remote repo

---

## **4. Git Ignore**

.gitignore                          # .gitignore file tell Git which files and folders to ignore(not track)

---

# 🔹 Git Reset – Short Notes

## 📌 `git reset --soft HEAD~1`

* Removes last commit
* Keeps changes in **staging area**
* No data loss

👉 Use when:

* You want to fix commit message
* You want to recommit

---

## 📌 `git reset --hard HEAD~1`

* Removes last commit
* Deletes changes from:

  * Staging
  * Working directory
* **Data lost permanently ❗**

👉 Use when:

* You want to discard changes completely

---

## 🔹 Quick Difference

| Command  | Commit | Staging | Working |
| -------- | ------ | ------- | ------- |
| `--soft` | ❌      | ✅       | ✅       |
| `--hard` | ❌      | ❌       | ❌       |

---

## 🔹 Key Point

👉 `HEAD~1` = go back 1 commit

---

# 🌿 **13. Git Branch (Create / Delete / Rename / Switch)**

```bash
git branch                           # List local branches
git branch <name>                    # Create branch
git checkout <name>                  # Switch from one branch to another branch
git switch <name>                    # Alternative command
git branch -d <name>                 # Delete branch
git branch -D <name>                 # To delete a branch forcefully
git checkout -b <name>               # Create + switch/Used to create and switch branch at a time
git switch -c <name>                 # Create + switch
git branch -m old new                # Rename branch
git push <alias> branch1 branch2     # Push specific branches
git push <alias> --all               # Push all branches
git branch -r                        # List remote branches
git branch -a                        # To see all the branches(local and remote)
git pull <alias> branch              # To get updated code from remote branch
git push origin --delete branch      # Delete Remote Branches from  CLI
git push origin --delete branch && git branch -d branch   # Delete remote repo branch and local repo branch (same)

```

---

# 🔀 **14. Git Merge**

```bash
git merge branch-name                # Merge a branch into current branch
git diff branch-name                 # Compare branches
```

---

# 🏷️ **15. Git Tag**

A tag marks a specific commit, usually after a stable or production release.

### Tag Commands

```bash
git tag                               # List tags
git tag <tag-name>                    # Create lightweight tag
git tag -a v1.0 -m "Message"          # Create annotated tag
git push <alias> <tag-name>           # Push single tag
git push <alias> --tags               # Push all tags
git show <tag-name>                   # View tag details
git tag -d <tag-name>                 # Delete tag locally
git push <alias> --delete <tag-name>  # Delete remote tag
git tag -a v0.9.0 <commit> -m "old release"   # Tag previous commit
```

---

# 💾 **16. Git Stash (Temporary Save Work)**

### Example Scenario

Working on *dev*, urgent fix in *master* → use stash.

### Commands

```bash
git stash                             # Stash changes
git stash save "message"              # Save with message
git stash list                        # View stashes
git stash apply stash@{id}            # Apply stash
git stash pop                         # Apply + delete stash
git stash drop                        # Delete latest stash
git stash drop stash@{id}             # Delete specific stash
git stash clear                       # Delete all stashes
```

---

### Q1: Local repo size increasing?

→ Delete unused stashes:

```bash
git stash drop
git stash drop stash@{5}
git stash clear
```

---

### Q2: Difference Between Branch & Tag

| Branch                     | Tag                      |
| -------------------------- | ------------------------ |
| Mutable                    | Immutable                |
| Created during development | Created after production |
| Contains ongoing work      | Marks a specific version |
| Can be deleted             | Stays as version label   |

---

# 🔄 **17. Git Restore**

```bash
git restore filename     # Undo changes in working directory
```

---

# 🧭 **18. Git Best Practices**

* Don’t commit incomplete code
* Test before commit
* Use meaningful commit messages
* Avoid merge conflicts
* Always raise Pull Requests (avoid blind merges)
* Delete unused branches
* Clean old stashes

---

# 📥 **19. Git Clone**

```bash
git clone <url>
```

### Steps:

1. Create a folder
2. Go inside
3. Run `git clone <url>`
4. Create a staging branch and start working

Default alias: **origin**

Rename:

```bash
git remote rename origin <alias>
git remote -v
```

---

