# 💾 16. Git Stash (Temporary Save Work)

## 🔹 Definition

A **Git stash** is used to temporarily save uncommitted changes so you can switch branches without committing.

👉 Useful when:

* You are working on one branch and need to switch urgently
* Work is incomplete but you don’t want to commit

---

## 🔹 Example Scenario

* Working on `dev` branch
* Suddenly need to fix issue in `main` branch

👉 Use stash → switch branch → fix → come back → apply stash

---

## 🔹 Stash Commands

### 📌 Stash current changes

```bash
git stash
```

---

### 📌 Stash with message

```bash
git stash save "work in progress"
```

---

### 📌 List all stashes

```bash
git stash list
```

---

### 📌 Apply stash

```bash
git stash apply stash@{0}
```

---

### 📌 Pop stash (apply + delete)

```bash
git stash pop
```

---

### 📌 Delete latest stash

```bash
git stash drop
```

---

### 📌 Delete specific stash

```bash
git stash drop stash@{1}
```

---

### 📌 Delete all stashes

```bash
git stash clear
```

---

# 🧪 Practical: Git Stash (Real-Time Scenario)

## 🎯 Scenario

👉 You are working on `dev` branch
👉 Suddenly urgent bug in `main`
👉 You don’t want to commit incomplete work

---

## 🔹 Step 1: Create Repository

```bash
git init stash-demo
cd stash-demo
```

---

## 🔹 Step 2: Initial Commit

```bash
echo "Version 1" > app.txt
git add .
git commit -m "Initial commit"
```

---

## 🔹 Step 3: Create dev Branch

```bash
git checkout -b dev
```

---

## 🔹 Step 4: Do Work (Not Committed)

```bash
echo "Work in progress" >> app.txt
git status
```

---

## 🔹 Step 5: Stash Changes

```bash
git stash save "dev work"
git status
```

👉 Working directory becomes clean

---

## 🔹 Step 6: Switch to Main

```bash
git checkout master
```

---

## 🔹 Step 7: Do Urgent Fix

```bash
echo "Hotfix applied" >> app.txt
git commit -am "Hotfix in main"
```

---

## 🔹 Step 8: Return to dev

```bash
git checkout dev
```

---

## 🔹 Step 9: Apply Stash

```bash
git stash pop
```

👉 Previous work restored

---

## 🔹 Step 10: Verify

```bash
git status
```

---

## 🔹 Memory Issue (Important)

### ❓ Q: Local repo size increasing?

👉 Because of unused stashes

### ✅ Solution

```bash
git stash drop
git stash drop stash@{5}
git stash clear
```

---
