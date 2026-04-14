# **Git Branching & Merging **
---

## **1. Git Branching: Work Without Disturbing the Main Code**

Branching in Git allows you to create a separate path from the main project so you can work independently without affecting the original code.

---

## **2. Why Use Branching?**

* Develop new features without touching or breaking the main code.
* Fix bugs safely before applying changes to the main branch.
* Enable team collaboration — multiple developers can work at the same time.
* Allow thorough testing before moving changes live.
* Keep the main branch stable for production use.
* Maintain a clear history of contributions — you can easily see who changed what and when.
* This makes tracking, reviewing, and managing the project simple.

---

## **3. Git Branching Flow: From Main to Production**

This flow helps manage code safely from development to deployment.

1. **main/master is the main production code**
2. **Create development branch from main**
3. **Developers create feature branches from development**
4. **After completion and testing, feature branches are merged into development**
5. **QA team tests the development code (in QA or UAT environment)**
6. **Once QA is approved, changes are moved to UAT (User Acceptance Testing)**
7. **After UAT success, merge development into main and deploy to production**

---

## **Handling Hotfixes in Git Branching**

Hotfix branches are crucial when an urgent issue needs fixing in production without disrupting ongoing development.

### **Hotfix Workflow**

1. **Create a hotfix branch from main/master**
   Examples: `hotfix/payment-error`, `hotfix/payment-bug`

2. **Apply and test the fix in the hotfix branch**

3. **Merge the hotfix into main/master and deploy**

4. **Merge the hotfix back into development**

---

### **Why Merge Hotfix to Development After Merging to Main?**

* You need the same fix in development.
* If not merged, the issue will appear again in future releases.
* Development and main must always stay in sync.

**Example:**
Fix added in main through hotfix must also exist in development → otherwise future releases will overwrite it.

---

# **1. Git Branch Commands**

In Git, the `git branch` command helps us do many things like:

* List all branches
* Create branch
* Delete a branch
* Rename a branch
* Switch from one branch to another

```
git init, status, push, add, commit, revert, reset, ....
       ↓
git branch  →  List ✔️   Create ✔️   Delete ✔️   Rename ✔️
```

### **Common Git Branch Commands**

```bash
git branch                           # List local branches
git branch <name>                    # Create branch
git checkout <name>                  # Switch from one branch to another
git switch <name>                    # Alternative command
git branch -d <name>                 # Delete branch
git branch -D <name>                 # Force delete branch
git checkout -b <name>               # Create + switch
git switch -c <name>                 # Create + switch
git branch -m old new                # Rename branch
git push <alias> branch1 branch2     # Push specific branches
git push <alias> --all               # Push all branches
git branch -r                        # List remote branches
git branch -a                        # List all (local + remote)
git pull <alias> branch              # Get updated remote branch code
git push origin --delete branch      # Delete remote branch
git push origin --delete branch && git branch -d branch   # Delete remote + local branch
```

---

# **2. Git Merging Strategy & Merge Conflicts**

---

## **1. Create a New Branch from Master**

Example file list:

```
Demo.java  Order.java  Prasanth.java  abc.py  def.sh  kkdevops.txt
```

Demo.java:

```
Adding new feature = 2
```

Create branch:

```
git branch development
git switch development
```

Note:
All files from master are copied into development.
You can now safely work without touching main code.

---

## **3. Make Changes and Commit in Development**

Edit:

```
Adding new feature = 3
```

Check status:

```
git status
git diff
```

Stage and commit:

```
git add Demo.java
git commit -m "Updated feature 2 to 3 in Demo.java"
```

---

## **Switch to Master and Merge**

```
git switch master
git merge development
```

---

## **4. What Happens If You Don't Commit Before Switching Branches?**

If you edited a file but didn't commit it:

```
git switch master
```

Git will **auto-carry** the uncommitted changes into master — very dangerous.

### **Avoid Auto-Carry**

Before switching:

```
git commit
OR
git stash
```

---

# **5. What is a Merge Conflict?**

A merge conflict happens when Git is unable to automatically merge changes from two branches.

👉 This occurs when:

Same file is modified in both branches
Same line is changed differently
One branch deletes a file, another modifies it.

### 🧑‍💻 Step 1: Create a Repository

```
mkdir merge-conflict-demo
cd merge-conflict-demo
git init

```
Create a file:
```
vi Demo.java
```
Add:
```
public class Demo {
    public static void main(String[] args) {
        int value = 5;
        System.out.println("Value = " + value);
    }
}
```
Save and commit:
```
git add .
git commit -m "Initial commit"
```
# Step 2: Create a Feature Branch

```
git checkout -b feature
```
Modify file:

```
int value = 10;
```
Commit:
```
git commit -am "Feature branch change value to 10"
```

# Step 3: Switch to Main Branch

```
git checkout master

```
Modify same line:
```
int value = 5;
```
Change to:
```
int value = 20;
```
Commit:
```
git commit -am "Main branch change value to 20"
```
# Step 4: Merge → Conflict Happens

```
git merge feature
```
👉 You will see:
```
CONFLICT (content): Merge conflict in Demo.java
```
# Step 5: Open the File

```
vi Demo.java
```
You will see:
```
<<<<<<< HEAD
int value = 20;
=======
int value = 10;
>>>>>>> feature
```
# Step 6: Fix Manually
Choose one OR combine:
```
int value = 20;
```
Option 2 (choose feature)
```
int value = 10;
```
Option 3 (combine)
```
int value = 20; // from main
// OR use logic if needed
```
Remove all markers (<<<<, ====, >>>>)

# Step 7: Mark as Resolved

```
git add Demo.java
git commit -m "Resolved merge conflict in Demo.java"
```
# Step 8: Verify
```
git log --oneline --graph
```
# **6. How to Push a New Branch to GitHub – Full Steps**

### **Step 1: Check Local Branches**

```
git branch
```

### **Step 2: Check Remote Branches**

```
git branch -r
```

### **Step 3: Push Local Branch**

```
git push origin branch-name
git push --all    # Push all branches
```

### **Step 4: Confirm Remote Branches**

```
git branch -r
```

### **Step 5: View All Branches**

```
git branch -a
```

---

#  Get Remote Branch to Local – Git Commands

## 🔹 Step 1: Fetch Latest Branches from Remote

```bash
git fetch origin
```

👉 This will download all remote branches (but not switch to them)

---

## 🔹 Step 2: Check Available Remote Branches

```bash
git branch -r
```

👉 Example output:

```
origin/main
origin/feature
origin/dev
```

---

## 🔹 Step 3: Create Local Branch from Remote

```bash
git checkout -b feature origin/feature
```

👉 Explanation:

* `feature` → your local branch name
* `origin/feature` → remote branch

---

## 🔹 Alternative (Recommended – New Git)

```bash
git switch -c feature origin/feature
```

---

## 🔹 Step 4: Verify

```bash
git branch
```

👉 You should see:

```
* feature
  main
```

---
# ✅ Summary

* `git fetch origin` → get remote branches
* `git branch -r` → see them
* `git checkout -b branch origin/branch` → use it locally

---
### Git Cherry-Pick
🔹 Definition : git cherry-pick is used to apply a specific commit from one branch into another branch.

👉 Instead of merging the entire branch, you pick only the required commit.

🔹 Syntax
```
git cherry-pick <commit-id>
```
---
### Git Pull vs Git Fetch

# Git Fetch
📌 Definition: git fetch downloads the latest changes from the remote repository but does NOT apply them to your current branch.

🔧 Commands
```
git fetch origin test
git merge origin/test
```

🧠 Explanation
git fetch origin test → Downloads changes from remote branch test
git merge origin/test → Applies those changes to your current branch

👉 So:

Fetch → Download only
Merge → Apply changes

✅ Advantages

Safe operation

No automatic changes to your code
You can review changes before merging

# Git Pull
📌 Definition: git pull is a shortcut that performs fetch + merge in one command.

🔧 Command
```
git pull origin test
```
🧠 Explanation
Fetches latest changes from test branch
Automatically merges into your current branch

👉 So:

Pull = Fetch + Merge
