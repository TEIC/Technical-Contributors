---
title: Technical Guide
nav_order: 3
---


# Technical Contributor Program
## Guide

### GitHub Authentication

#### SSH Key or Personal Access Token Authentication {#ssh-key-or-personal-access-token-authentication}

Since the [deprecation of basic authentication](https://github.blog/security/application-security/token-authentication-requirements-for-git-operations/) (password-based authentication) for Git operations, it is now necessary to use either a SSH key or a personal access token to authenticate Git operations. The Technical Council recommends using the SSH authentication method. While SSH keys can be read-only or read-write enabled, or scoped to specific repositories, the chief advantage of using SSH keys for authentication is not having to enter your username and Personal Access Token with every Git operation. Although a personal access token has a finer-grained permissions model in comparison, SSH keys have a better security profile than Personal Access Tokens as they are not transmitted with every Git operation.

#### [Generating a new SSH key for GitHub authentication](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

Generate a new SSH key on your local machine following the instructions below. After completing these steps and generating your SSH key pair, follow the [Adding the SSH key to GitHub](#adding-the-ssh-key-to-github) instructions to enable SSH authentication for Git operations.

1. Open Terminal. Paste the text below, substituting in your GitHub email address.

    `ssh-keygen \-t ed25519 \-C "YOUR_NAME@gmail.com"`  
2. This creates a new SSH key, using the provided email as a label.  
   `Generating public/private ALGORITHM key pair`  
3. When you're prompted to `"Enter a file in which to save the key"`, you can press **Enter** to accept the default file location. Please note that if you created SSH keys previously, ssh-keygen may ask you to rewrite another key, in which case we recommend creating a custom-named SSH key. To do so, type the default file location and replace id\_ssh\_keyname with your custom key name.  
4. Enter a file in which to save the key `(/home/YOU/.ssh/ALGORITHM):\[Press enter\]`  
5. At the prompt, type a secure passphrase. For more information, see "[Working with SSH key passphrases](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases)."

    `Enter passphrase (empty for no passphrase): \[Type a passphrase\]`
    `Enter same passphrase again: \[Type passphrase again\]`  
     
6. You should get a message which includes the file path to your private and public keys

   Your identification has been saved in `/home/your_name/.ssh/id\_ed25519`

   Your public key has been saved in `/home/your_name/.ssh/id\_ed25519.pub`

7. Paste the following command to list the public key for GitHub. Usually, the public key has the suffix `'.pub'`.

    `cat \~/.ssh/id\_ed25519.pub`
    
#### Adding the SSH key to GitHub {#adding-the-ssh-key-to-github}

1. Go to your GitHub account, select **Settings**.  
2. Select **SSH and GPG** keys.  
3. In the SSH Keys section, select **New SSH Key**.  
4. Add a title for the device in the **Title** field  
5. Select the type of key from the **Key Type** dropbox menu.  
6. In the **Key** text box, add the public key.   
7. Click **Add SSH key**.

#### Generating a GitHub Personal Access Token {#generating-a-github-personal-access-token}

The following procedure was written and provided by [Joey Takeda](https://alliance-jenkins.dhil.lib.sfu.ca/job/lim/lastSuccessfulBuild/artifact/public/docs/getting_started.html#getting_started_setting-up-oxygen-first-time).

1. Navigate to GitHub ([https://github.com](https://github.com/)), log in, and then click on your user icon in the right hand corner to open the side menu. Then click **Settings**.  
2. In settings, click **Developer Settings** at the bottom of the left-hand menu.  
3. Click **Personal access tokens** and select **Tokens (classic)**.  
4. Click on the right hand side dropdown menu labelled **Generate new token**, and select **Generate new token (classic)**.  
5. In the **Note** text field, enter a name for your token (e.g. oXygen).   
6. From the expiration drop down menu, select **No expiration**.  
7. Under the **Select scopes** section, select the **repo** and **user** scopes.  
8. Click **Generate Token** at the bottom of the screen.  
9. You will now see a token, which is effectively the same as a password for GitHub. Make sure to copy the token by selecting the copy button and save the token using a secure password manager.

#### Cloning a repository {#cloning-a-repository}

1. On GitHub, navigate to the main page of the repository.  
2. Above the list of files, click **Code**.  
3. Copy the URL for the repository.  
   1. To clone the repository using HTTPS, under **HTTPS**, click the copy icon.  
   2. To clone the repository using an SSH key, including a certificate issued by your organization's SSH certificate authority, click **SSH**, then click the copy icon.  
   3. To clone a repository using GitHub CLI, click **GitHub CLI**, then click the copy icon.  
4. Open Terminal.  
5. Change the current working directory to the location where you want the cloned directory using the command `cd`. For example, if you have created a folder for GitHub, enter `cd GitHub`.  
6. Type `git clone`, and then paste the URL you copied earlier: `git clone git@github.com:TEIC/TEI.git`  
7. Press **Enter** to create your local clone.  
8. Repeat these steps to clone the TEI Stylesheets repository: `git clone git@github.com:TEIC/Stylesheets.git`

#### Troubleshooting cloning errors

When cloning a repository it is possible that you might encounter some errors.

If you are unable to clone a repository, check that:

* You can connect using HTTPS. For more information, see [Troubleshooting cloning errors](https://docs.github.com/en/repositories/creating-and-managing-repositories/troubleshooting-cloning-errors).  
* You have permission to access the repository you want to clone. For more information, see [Troubleshooting cloning errors](https://docs.github.com/en/repositories/creating-and-managing-repositories/troubleshooting-cloning-errors#check-your-permissions).  
* The default branch you want to clone still exists. For more information, see [Troubleshooting cloning errors](https://docs.github.com/en/repositories/creating-and-managing-repositories/troubleshooting-cloning-errors#error-remote-head-refers-to-nonexistent-ref-unable-to-checkout).  
* [Troubleshooting connectivity problems](https://docs.github.com/en/get-started/using-github/troubleshooting-connectivity-problems)
