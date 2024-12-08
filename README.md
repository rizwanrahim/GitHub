
# How to Configure GPG for GitHub

Follow these steps to set up and verify your GPG key for GitHub.

## 1. Generate a GPG Key

```bash
gpg --full-generate-key
```

- Select `RSA and RSA (default)`.
- Choose a key size of `4096` bits.
- Set the expiration to `0` (never expires).
- Confirm by typing `y`.

### 2. Optional: Secure Your Certificate
- You can set a password for added security or leave it blank.

### 3. List Your Newly Generated Key

```bash
gpg --list-secret-keys --keyid-format=long
```

### 4. Export Your Key

```bash
gpg --armor --export [key]
```

- Replace `[key]` with the key ID found after `rsa4096/`.

### 5. Add the Key to GitHub
- Copy the exported key and add it to your GitHub settings under **GPG Key**.

## 6. Configure Git for GPG Signing

```bash
git config --global commit.gpgsign true
git config --global tag.gpgsign true
git config --global user.name "[username]"
git config --global user.email "[email]"
git config --global user.signingkey "[key]"
```

- Replace `[username]`, `[email]`, and `[key]` with your GitHub username, email, and GPG key ID.

## 8. Restart GPG Agent

If GPG is down, restart it using:

```bash
gpg-connect-agent -v
```

## 10. Fix GPG Path Issues

If needed, specify the GPG executable path:

```bash
git config --global gpg.program "C:\Program Files (x86)\GnuPG\bin\gpg.exe"
```

---
Ensure you follow these steps precisely to successfully configure GPG for your GitHub account.
