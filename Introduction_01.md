#  GIT & GITHUB

---

#  GITHUB

* GitHub is a Source Code Management (SCM) platform used to store and manage project source code in a secure and organized way.  

* It allows us to store, manage, and share code, and helps teams collaborate easily during software development.  

* GitHub also provides powerful features such as:
  - Version control  
  - Issue tracking  
  - Pull requests  
  - Code reviews  
  - Project collaboration tools  
* These help teams work efficiently and maintain high-quality code.

---

##  Tools Like GitHub

- GitLab  
- Bitbucket  
- Azure Repos  
- SourceForge  
- AWS CodeCommit  
- Gitea  

---

#  ADMINISTRATOR

##  Summary Flow: GitHub Organization Setup

1. Create a GitHub account  
2. Create an organization under the account  
3. Create teams inside the organization  
4. Invite members to the organization  
5. Assign members to appropriate teams  
6. Create repositories for your projects  
7. Add teams or individual users to the repositories  
8. Set correct permissions:
   - Read  
   - Write  
   - Admin  
9. Manage access as needed  

---

## ⚠️ Sensitive Actions (Only When Required & Approved)

### ❌ Remove member from team
Team → Click Member → Remove  

### ❌ Delete team
Team → Settings → Delete team  

### ❌ Delete repository
Repo → Settings → Scroll to bottom → Delete this repository  

### ❌ Delete organization
Org → Settings → Danger zone → Delete organization  

---

#  GIT

Git stands for **Global Information Tracker**.  

It is a version control tool used to track changes in files throughout the development process.  

Git helps maintain multiple versions of the same file, allowing developers to:
- Compare changes  
- Revert changes  
- Manage versions easily  

It is:
- Free  
- Open-source  
- Widely used in software development  

---

#  GIT WORKFLOW (Git Lifecycle)

git init → git add → git commit → git push

<img width="1339" height="277" alt="image" src="https://github.com/user-attachments/assets/9037a792-4b9b-4986-980f-8fe0800edd87" />

---

#  WORKING DIRECTORY (Working Area)

- The Working Directory is your local project folder where you create, edit, and modify files.
- Any newly created or changed files appear here first as untracked or modified.
- This is where you create/edit files. 

---

#  STAGING AREA

- When you run git add, the files move from the working directory to the staging area.
- Here, Git prepares the selected files to be saved.
  
```

git add file_name

```
---

#  LOCAL REPOSITORY

- When you run git commit, the files move from the staging area to the local repository.
- Your changes are now safely saved in your local Git database.
- 
```

git commit -m "message"

```
- Changes are stored in local Git database  

---

#  REMOTE REPOSITORY

- When you run git push, your committed changes go from the local repository to the remote repository like GitHub/GitLab/Bitbucket.
- 
```

git push origin main

```

---

# COMPLETE FLOW SUMMARY

```

Working Directory → Staging → Local Repo → Remote Repo

Edit → git add → git commit → git push

```
---
