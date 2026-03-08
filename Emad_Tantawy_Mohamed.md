## What is an SSH Key?

An SSH key is a pair of cryptographic keys used for secure communication between systems. The key pair consists of:

- ****Public Key:**** Shared with the remote system (like GitHub).
- ****Private Key:**** Kept secret and stored securely on your local machine.

### Public vs. Private Keys

The public key is added to your GitHub account, while the private key remains on your machine. When you initiate a Git operation, GitHub verifies that the private key on your system matches the public key associated with your account.

### Security Considerations

- ****Private Key Protection:**** Keep your private key secure; if compromised, unauthorized users could access your repositories.
- ****Passphrases:**** Adding a passphrase to your SSH key adds an extra layer of security.

### Benefits of Using SSH over HTTPS for Git Operations

- ****Security:**** SSH keys provide encrypted communication, making them more secure than using a username and password with HTTPS.
- ****Convenience:**** Once set up, SSH keys do not require you to re-enter credentials each time you interact with a remote repository.
- ****Automation:**** SSH keys are ideal for automated deployments and scripts, as they allow non-interactive authentication.

## How to Set Up an SSH Key for GitHub

SSH key is a safe way to connect to GitHub, without putting your username and password in the terminal you want to do something and this article will show you how to set it up.

### Step 1: Check for Existing SSH Keys

It is always wise to first verify if you already have a generated SSH key. You can do this by opening your terminal and running the following command

ls -al ~/.ssh

This will show all the SSH keys available in the ~/.ssh directory. If you notice files that are named with ****id_rsa.pub**** or ****id_ecdsa.pub****, you already have an SSH key pair.

### Step 2: Generate a New SSH Key

In case you do not have an SSH key, then you will have to create one first. Use the following command:

ssh-keygen -t rsa -b 4096 -C "gfg_email@example.com"

This command creates a new SSH key using the RSA algorithm, with the key size of 4096 bits. Replace gfg_email@example. com with the e-mail address used for your GitHub account

You’ll be prompted to choose a file location to save the key (press Enter to accept the default location) and to enter a passphrase for an added layer of security or if you want to skip passphrase, press Enter.

### Step 3: Add the SSH Key to the SSH-Agent

Once you have created your SSH key you want to add it to the SSH agent which is used to manage the SSH keys.

****Start the SSH agent with:****

eval "$(ssh-agent -s)"

****Then, add your SSH private key to the agent:****

ssh-add ~/.ssh/id_rsa

### Step 4: Adding SSH Key to your Github Account

Now, you need to add the generated SSH public key to your GitHub account. First, copy the contents of your public key:

cat ~/.ssh/id_rsa.pub | pbcopy  # For macOS  
cat ~/.ssh/id_rsa.pub | clip    # For Windows  
cat ~/.ssh/id_rsa.pub           # For Linux

Then, log in to your GitHub account and navigate to :

****Settings > SSH and GPG keys > New SSH key****

Paste your key into the "Key" field, give it a descriptive title like ****Github_ssh_key****, and click Add SSH key.

### Step 5: Test the SSH Key

Finally, you can test your SSH connection to GitHub by running:

ssh -T git@github.com

If everything is set up correctly, you should see a message like:

Hi Moksh45! You've successfully authenticated, but GitHub does not provide shell access.

## Managing SSH Keys

### 1. Reviewing and Removing SSH Keys from Your GitHub Account

It is recommended that users often check the SSH keys connected to his or her GitHub account and delete the ones that are not necessary for security reason.

### 2. Effective Approaches for Handling Many SSH Keys

When using multiple repositories, one needs to have a way of handling their SSH keys so that there is no clash.

### 3. Understanding deploy keys and their use in repository deployments

Deploy keys are specific SSH keys used for allowing read-only or read-write access to repositories for deployment purposes.