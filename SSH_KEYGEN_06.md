# 🔑 **24. SSH Keys**

### Generate SSH Key

```bash
ssh-keygen
```

### Key Files

* `id_rsa` → Private key
* `id_rsa.pub` → Public key

### Custom Algorithm

```bash
ssh-keygen -t rsa
ssh-keygen -t dsa
```
t = type of algorithm

### Custom Key Name

```bash
ssh-keygen -t rsa -f ~/.ssh/my_rsa_key
```
ssh-keygen → command to generate SSH keys
-t rsa → type of key (RSA algorithm)
-f ~/.ssh/my_rsa_key → file name + location

### Add to GitHub
* Go to GitHub → Settings → SSH and GPG Keys
* Click New SSH Key
* Paste → Save( Public key paste here)

* Verify:

   ```bash
   ssh -T git@github.com
   ```
* Update remote URL to SSH
* Delete saved HTTPS credentials
* Push using SSH alias

---
### What is a Pull Request (PR)?

A Pull Request (PR) is a formal request to merge your changes from one branch into another (commonly from a feature or hotfix branch → into the main/master branch) on GitHub.

---
### Why is a PR Important?

PRs are especially useful when working in a team or collaborating on code, because they ensure that code is:

* Reviewed before merging
* Approved by the right person
* Tested before going live

---
## Common Use Cases

* You fixed a bug or added a new feature in a branch (hotfix, feature/login, etc.).
* You now want that code to go into master or main.
* Instead of merging it directly, you raise a PR for:
* Team to review
* Ensure there are no conflicts
* Approve and merge safely

---
