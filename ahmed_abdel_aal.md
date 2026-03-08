# SSH (Secure Shell)

## Introduction

SSH (Secure Shell) is a network protocol that allows users to securely connect to another computer over an unsecured network. It is widely used by system administrators, developers, and IT professionals to remotely manage servers and systems. SSH provides a secure channel over the internet by encrypting the data transmitted between the client and the server.

SSH was designed as a replacement for older remote login protocols such as Telnet and rsh, which transmitted information in plain text. Because those protocols were insecure, SSH was developed to ensure confidentiality, integrity, and authentication in remote communications.

## History of SSH

SSH was first developed in 1995 by **Tatu Ylönen**, a researcher at the Helsinki University of Technology in Finland. The initial version was created after a password-sniffing attack occurred on the university network. Since then, SSH has evolved and become a standard tool used in operating systems such as Linux, macOS, and even Windows.

Today, the most commonly used implementation is **OpenSSH**, which is an open-source project that provides tools for secure remote login and other secure network services.

## How SSH Works

SSH works using a **client-server model**. The SSH client connects to an SSH server running on a remote machine. During the connection process, SSH performs several steps to establish a secure communication channel:

1. **Authentication** – The client proves its identity to the server using a password or SSH keys.
2. **Encryption** – Data transmitted between the client and server is encrypted to prevent interception.
3. **Integrity Verification** – SSH ensures that the data being transmitted is not altered during communication.

SSH uses cryptographic techniques such as **public-key cryptography**, **symmetric encryption**, and **hash functions** to secure the connection.

## SSH Authentication Methods

### 1. Password Authentication

The user logs in by providing a username and password for the remote machine.

Example:

```bash
ssh username@hostname
```
