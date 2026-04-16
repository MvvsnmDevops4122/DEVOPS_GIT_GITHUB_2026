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

### Custom Key Name

```bash
ssh-keygen -t rsa -f ~/.ssh/my_rsa_key
```

### Setup Process

1. Check existing keys
2. Delete known_hosts
3. Generate new key
4. Add public key to GitHub
5. Verify:

   ```bash
   ssh -T git@github.com
   ```
6. Update remote URL to SSH
7. Delete saved HTTPS credentials
8. Push using SSH alias

---
