# 🏷️ 15. Git Tag

## 🔹 Definition

A Git tag is used to mark a specific commit, usually for stable versions or production releases.

👉 Tags are commonly used for:

* Versioning (v1.0, v2.0)
* Release tracking
* Rollback points

---

## 🔹 Types of Tags

### 1. Lightweight Tag

* Simple pointer to a commit
* No additional metadata

```bash
git tag v1.0
```

---

### 2. Annotated Tag

* Stores metadata (author, date, message)
* Recommended for production releases

```bash
git tag -a v1.0 -m "Initial release"
```

---

## 🔹 Tag Commands

### 📌 List all tags

```bash
git tag
```

---

### 📌 Create lightweight tag

```bash
git tag <tag-name>
```

---

### 📌 Create annotated tag

```bash
git tag -a v1.0 -m "Message"
```

---

### 📌 Tag a specific commit

```bash
git tag -a v0.9.0 <commit-id> -m "old release"
```

---

### 📌 Push a single tag

```bash
git push origin <tag-name>
```

---

### 📌 Push all tags

```bash
git push origin --tags
```

---

### 📌 View tag details

```bash
git show <tag-name>
```

---

### 📌 Delete tag locally

```bash
git tag -d <tag-name>
```

---

### 📌 Delete tag from remote

```bash
git push origin --delete <tag-name>
```

---

# 🧪 Practical: Git Tag (Step-by-Step)

## 🔹 Step 1: Create Repository

```bash
git init tag-demo
cd tag-demo
```

---

## 🔹 Step 2: Create Commits

```bash
echo "Version 1" > app.txt
git add .
git commit -m "Initial commit"

echo "Feature added" >> app.txt
git commit -am "Feature commit"
```

---

## 🔹 Step 3: Create Tag

### Annotated Tag (Recommended)

```bash
git tag -a v1.0 -m "First stable release"
```

---

## 🔹 Step 4: Verify Tag

```bash
git tag
```

👉 Output:

```
v1.0
```

---

## 🔹 Step 5: View Tag Details

```bash
git show v1.0
```

---

## 🔹 Step 6: Push Tag to Remote

```bash
git remote add origin <repo-url>
git push origin v1.0
```

---

## 🔹 Step 7: Tag Older Commit

```bash
git log --oneline
git tag -a v0.9.0 <commit-id> -m "Old version"
```

---

## 🔹 Step 8: Delete Tag

### Local:

```bash
git tag -d v1.0
```

### Remote:

```bash
git push origin --delete v1.0
```

---
