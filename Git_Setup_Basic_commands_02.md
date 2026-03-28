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

# 💡 Git Interview Q&A

---

## Q1: Can you remove a Git remote alias?
👉 Yes

```

git remote remove jio

```

---

## Q2: How to skip git add for modified files?

```

git commit -a -m "Updated code"

```

🔹 Works only for tracked files

---

## Q3: Where are Git credentials stored?

- Windows → Credential Manager  
- macOS → Keychain Access  

---

## Q4: How to view files changed in a specific commit?

```

git show --pretty="" --name-only <commit_id>

```

### Example:

```

git show --pretty="" --name-only 93bc198a48166ce5ff14ad2e3df9908c85caf150

```

---

#  Why DevOps Engineers Need Git?

- Manage scripts, YAML, Terraform files  
- Enable team collaboration  
- Track changes and rollback easily  
- Integrate with CI/CD tools like:
  - Jenkins  
  - GitHub Actions  

---

---

If you want next:
👉 I can convert this into **real-time hands-on lab (step-by-step commands)**
👉 or **Git branching + merging practice (very important for interviews)** 🚀
