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
# Why GitHub is Widely Used**

* Helps store and manage code safely
* Tracks every change using version control(GIT)
* Makes collaboration simple for teams
* Supports CI/CD, DevOps workflows
* Integrates with many tools (Jenkins, SonarQube, VS Code, etc.)
* Easy to maintain versions, branches, and pull requests

---

##  Tools Like GitHub

- GitLab  
- Bitbucket  
- Azure Repos  
- SourceForge  
- AWS CodeCommit  
- Gitea  

---
**ADMINISTRATOR**
### **1.3 Summary Flow: GitHub Organization Setup**
-
<img width="994" height="466" alt="image" src="https://github.com/user-attachments/assets/ab52e7ca-0272-4f35-8246-dab0484c7dab" />
---
1.Create a GitHub account
2.Create an organization under the account
3.Create teams inside the organization
4.Invite members to the organization
5.Assign members to appropriate teams
6.Create repositories for your projects
7.Add teams or individual users to the repositories
8.Set correct permissions (Read / Write / Admin) based on role
9.Manage access as needed
10.Remove members, delete teams, or repositories — only when required and with proper approval


## **2. GitHub Setup Steps**

### **Step 1: Create a GitHub Account**

### 1. Open GitHub
- Go to **https://github.com**
- Click **Sign Up**

### 2. Enter Your Details
- Enter your **email address**
- Create a **password**
- Choose a **username**
- Click **Create account**

### 3. Verify Your Email
- GitHub will send a **verification code** to your email
- Enter the code on the verification page
- Click **Continue**

### 4. Complete the Signup
- Your GitHub account is now created
- You can sign in anytime using your registered email and password


### **Step 2: Create an Organization**

### 1. Open Organization Settings
- After signing in, click your **profile icon** (top-right corner)
- Select **Your organizations**

### 2. Create a New Organization
- Click **New organization**
- If you already have organizations, they will be listed here

### 3. Choose a Plan
- Select the **Free** plan (sufficient for learning and small teams)

### 4. Enter Organization Details
- Provide an **organization name**  
  Example: `my-company-org`
- Enter your **email address**
- Click **Next**

### 5. Finalize Organization Creation
- Provide optional details if required
- Click **Complete setup**

Your GitHub organization is now created.


### **Step 3: Create Teams**

### 1. Open Your Organization
- Go to the **homepage** of the organization you created

### 2. Create a New Team
- Click **Teams**
- Then click **New team**

### 3. Enter Team Details
- Give your team a **name**
  - Example: `dev-team`, `qa-team`, `ops-team`

### 4. Create the Team
- Click **Create team**

Your team is now created inside the organization.


### **Step 4: Invite People to the Organization**

### 1. Open the People Section
- Go to your organization
- Click **People**
- Click **Invite member**

### 2. Send an Invitation
- Enter the person's **GitHub username** or **email address**
- Click **Send invitation**

### 3. View Invited Users
- You can see all pending invites under the **Invitations** section

### 4. When Users Accept
- Once they accept the invite, they will appear in the **Members** list under **People**

### 5. Add Members to a Team
- Choose the team you want to add them to (e.g., `dev-team`)
- Click **Add a member**
- Select the user from the list
- Confirm to add them to the team


### **Step 5: Create a Repository (Project Code)**

### 1. Go to Your Organization
- Open your organization homepage
- Click **New repository**

### 2. Enter Repository Details
- Provide a **repository name**  
  Example: `my-project`, `webapp`, `devops-demo`

### 3. Choose Visibility
- **Public** → Anyone can view the code  
- **Private** → Only people you allow can access it  
  *(Recommended for company or team projects)*

### 4. Optional Settings
- Add a **description**  
- Add a **README** (optional)  
- Add a **.gitignore** if needed  
- Choose a **license** (optional)

### 5. Create the Repository
- Click **Create repository**

### 6. Access the Repository
- After creation, you will see the repository URL  
  Example:  
  `https://github.com/my-org/my-project`

This URL is used to clone the repository into your local system or add remote origin.

### **Step 6: Add a Team to the Repository**

### 1. Open Repository Settings
- Go to your repository
- Click **Settings**
- Select **Manage access**

### 2. Add a Team
- Click **Invite a team**
- Select the team you created earlier  
  Example: `dev-team`, `qa-team`

### 3. Set Team Permissions
Choose permission based on your project needs:

- **Read** → Can only view code  
- **Write** → Can push code  
- **Admin** → Full control of the repository  

### 4. Confirm Access
- Save the permissions
- The team will now appear in the **Manage access** section

Now your team has access to the repository.

---

## **3. Step 7: Give Access to Individual Users**

### **8.1 GitHub Permission Levels**

* **Read** → can only view code
* **Write** → can push changes
* **Admin** → full control over repo
* **Maintain** → manage repo settings
* **Triage** → manage issues & pull requests only

### **8.2 Examples**

**8.2.1 Team Example**

* Add `dev-team` with **Write** access
  (All developers can push code)

**8.2.2 Individual Example**

* Add `john-dev` with **Read** access
  (John can only view the repository)

### **8.3 Change Access Anytime**

* You can update permissions (Read → Write → Admin) anytime

---

## **9. Step 8: Delete Users, Teams, or Repos (Only When Needed)**

These are sensitive actions. Perform them only with approval.

* Remove member from team: Go to Team → Click Member → Remove
* Delete team: Team → Settings → Delete team
* Delete repository: Repo → Settings → Scroll to bottom → Delete this repository
* Delete organization: Org → Settings → Danger zone → Delete organization

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
