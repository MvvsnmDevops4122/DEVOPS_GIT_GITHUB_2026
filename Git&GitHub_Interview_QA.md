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
