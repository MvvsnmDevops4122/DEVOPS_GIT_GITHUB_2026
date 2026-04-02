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

## **Q1: What is the difference between `git add .` and `git add *`?**

| Command      | Behavior |
|--------------|----------|
| `git add .`  | Adds all files — new, modified, including hidden files and files inside subfolders.
| `git add *`  | Adds only visible (non-hidden) files from the current folder. Skips hidden files and files inside subfolders.

**Tip:**  
`git add .` is the most commonly used as it handles everything.

---

## **Q2: How to remove untracked files from the working directory?**

```bash
git clean -f
````

* Removes **untracked** files
* Does **not** remove tracked files

---

## **Q3: Is it possible to move files from staging area back to working directory?**

Yes:

```bash
git reset <file>
# or
git restore --staged <file>
```

This removes the file from staging but keeps the changes.

---

## **Q4: Due to a bad commit, the application is not working. How to revert it?**

```bash
git revert <commit_id>
```

* Creates a **new commit** that reverses the changes
* Safe for remote repos (does NOT rewrite history)

---

## **Q5: How to delete updated code in the remote repository?**

### Step 1: Reset local branch to previous commit

```bash
git reset --hard <commit_id>
```

### Step 2: Force-push the corrected branch

```bash
git push --force
```

⚠️ **Warning:** This rewrites history. Use carefully.

---

## **Q6: Difference between `git reset` and `git revert`?**

| Command      | Description                                                                          |
| ------------ | ------------------------------------------------------------------------------------ |
| `git reset`  | Moves all staged files back to working area                                          |
| `git revert` | creates a new commit to undo the changes made by a specific commit                   |

---

## **Q7: What is a `.gitignore` file?**

.gitignore file tell Git which files and folders to ignore(not track)

**Example:**

```
*.log
node_modules/
.env
target/
```

Used to skip logs, temp files, secrets, build files, etc.

---

# 🎯 Bonus: Real-Time Git Tips

---

### **1. View status of tracked and staged files**

```bash
git status
```

---

### **2. See commit history**

```bash
git log
```

---

### **3. Undo last local commit (but keep changes)**

```bash
git reset --soft HEAD~1
```

---

### **4. Remove a file from staging**

```bash
git restore --staged <file>
```

---

# 🔥 Real-Time Use Case

### **Scenario:**

You committed a file to GitHub by mistake.

### **Solution:**

```bash
git reset --soft HEAD~1
git restore --staged <file>
git commit -m "Fixed accidental commit"
git push -f
```

### SUMMARY - RESET, REVERT

## **1. Git Reset (Unstage Files)**

```bash
git reset                            # Unstage all files/Moves all staged files back to working area
git reset filename                   # Unstage one file/Moves only the specified file
git reset .                          # Unstage everything including hidden files/To unstage all the files including hidden ones
```

---

## **2. Git Clean (Remove Untracked Files)**

* Removing files from the working directory

```bash
git clean -n                         # Dry run – shows which files will be deleted
git clean -f                         # Forcefully deletes all untracked files
git clean -f filename                # Forcefully deletes particular untracked file.
```

---

## **3. Git Revert (Undo a Commit With a New Commit)**

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

## **4. Git Ignore**

.gitignore                          # .gitignore file tell Git which files and folders to ignore(not track)

---


---
