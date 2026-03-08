# SSH in Git

## What is SSH?

SSH stands for **Secure Shell**.  
It is a cryptographic network protocol used to securely connect between computers over an unsecured network.

SSH provides a secure way to:
- Access remote servers
- Transfer files
- Authenticate users
- Work with version control systems like Git

When using Git with platforms such as **GitHub, GitLab, or Bitbucket**, SSH allows developers to securely connect to their repositories without entering their username and password every time.

---

## Why SSH is used with Git?

Using SSH with Git has several advantages:

- **Secure authentication**
- **Encrypted communication**
- **No need to type username and password repeatedly**
- **Faster and more convenient for developers**

Instead of logging in every time, Git uses an **SSH key pair** to verify your identity.

---

## How SSH Authentication Works

SSH authentication is based on **two keys**:

### 1. Public Key
- Shared with GitHub or the remote server
- Used to identify the user

### 2. Private Key
- Stored safely on your computer
- Used to prove your identity

When you try to connect to GitHub using SSH, GitHub checks your **public key** to verify your identity.
