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

#### Oxygen Git Client

The following instructions are intended for users who are using Oxygen and the Git Client plugin. 

##### Cloning the TEIC Repositories using Oxygen Git Client 
1. In Oxygen, go to the **Git** menu and select **Clone New Repository**  
2. In the **Clone Repository** window, add the URL link to the **Repository URL** field. For example, for the TEI repository add the web link: `https://github.com/TEIC/TEI.git`.  
3. For the **Checkout branch** field, select **\<Default branch\>**.  
4. For the **Destination path** field, select where you would like to clone the repository.  
5. At this point, you may be prompted to authenticate. To authenticate, enter your GitHub username and paste the GitHub token that you generated earlier as the password.  
6. Repeat the above steps for cloning the [Stylesheets](https://github.com/TEIC/Stylesheets.git) repository.

##### Connecting the TEIC Repositories to Oxygen Git Client {#connecting-the-teic-repositories-to-oxygen-git-client}

If you have already cloned the TEIC repositories via the command line using the password-protected SSH key as follows `git clone [git@github.com](mailto:git@github.com):TEIC/TEI.git`, you may be receiving an error message in the **Git Staging** tab in Oxygen stating that the cloned repositories cannot be reached.   
The following procedure documents how you can resolve this error message by adding the URL for the remote repository.

1. In Oxygen, select the **Git Staging** tab.   
2. The **Working Copy** drop down menu lists the available repositories, select **TEI**.  
3. From the Toolbar, select the **Git** menu or from the **Git Staging** tab, select the three vertical dots icon in the top right corner.  
   ![][image1]  
4. Select **Manage remote repositories.** You will see the **Remote repositories** window.  
5. Click on the remote repository (once selected it will be highlighted blue) and select **Edit**.   
   ![][image2]  
6. In the **Edit remote repository** window, update the **Remote URL** field with the web link for the repository, for example: [https://github.com/TEIC/TEI.git](https://github.com/TEIC/TEI.git).   
7. Repeat these steps for updating the Remote URL link for the [Stylesheets](https://github.com/TEIC/Stylesheets.git) repository.  
   ![][image3]  
8. Click **OK**. The Git Client should now be able to access and connect to the remote repository.

### Docker Commands Quick Reference Guide ([TCW32](https://tei-c.org/documentation/tcw32/)) {#docker-commands-quick-reference-guide-(tcw32)}

| Command | Function |
| :---- | :---- |
| docker start \-ai tei  | Starts the docker container for the TEI repositories |
| cd tei   | Changes directory to the docker container for the TEI repositories |
| cd /tei/TEI/P5  | Store the local builds within the docker container with the TEI repo, put them in the P5 folder |
| make clean validate html-web | To clean (delete previous builds) and validate and build the TEI web pages locally.  (**Note**: after the process finishes, you’ll have a directory called “Guidelines-web” in your P5 directory. Outside your Docker shell, you can browse to this folder, find the index.html file, and open it in a browser.) |
| make clean validate |  |
| make test |  |
| make clean validate html-web test exemplars |  |
| time make clean validate html-web test exemplars |  |
| Ctrl \+ Shift \+ D | Exit out of docker |

### Updating the TEI Guidelines files

1. Create a branch for the changes following steps 1 to 4 in the [**Updating the TEI Guidelines using Git**](#updating-the-tei-guidelines-using-git:) procedure.  
2. Make the changes to the file(s) in your chosen editor.  
3. Click **Save.**  
4. From **Document** in the left tab, select **Validate.**  
5. Click **Check Well-Formedness.**  
6. Click **Validate.**  
7. Commit your changes following steps 6 to 9 in [**Updating the TEI Guidelines using Git**](#updating-the-tei-guidelines-using-git:) procedure.

### Updating the TEI Guidelines using Git

1. Change directory to the TEI repository: `cd /mnt/c/Users/trish/GitHub/TEI/P5/`.  
2. Check if you are up to date with the latest version of the Guidelines: `git status`.  
3. Pull the latest version from GitHub: `git pull`.  
4. Before making any changes or updating a file, check out a new branch and name the branch using the following command and naming convention `yourname\_issuenumber`: `git checkout \-b trishaoconnor\_2356`.  
5. Make the changes to the files, see [**Updating the TEI Guidelines** **files**](#updating-the-tei-guidelines-files:).  
6. Commit your changes to the branch that you created for the request and give a brief description of the changes (\-a for add and \-m for message `"Insert message here"`): `git commit -a -m "Insert summary of change(s) here"` 
7. Push your changes to the dev branch (this creates a pull request):   
   `git push --set-upstream origin trishaoconnor\_2356`  
8. Click on the url link that Ubuntu returns to you, see ([**Updating the Pull Request on GitHub**](#pull-requests)).  
9. Remember to checkout out of the branch that you created for the changes: `git checkout dev`

### Pull requests
#### Updating a Pull Request on GitHub 

1. Fix the issue title so it does not run over.
2. Add a comment to describe the work done on the ticket.  
3. Assign someone to merge the branch into dev.   
4. Assign a reviewer to review the changes before the branch is merged into dev.  
5. Click **Create Pull Request**.

#### Updating the dev branch to merge a PR

1. First, switch to the branch listed in the PR. For example, to switch to branch `trishaoconnor\_XXXX`, enter `git checkout trishaoconnor\_XXXX`.  
2. Run command `git pull`.  
3. Run command `git merge -m "Add whatever is new in dev" dev`.  
   **Note:** The message is mandatory.
4. Run command `git status -uno`. 
5. Run command `git push` to push commits to the branch.

#### [Removing commits from a Pull Request](https://stackoverflow.com/questions/36168839/how-to-remove-commits-from-a-pull-request) {#removing-commits-from-a-pull-request}

| Command | Function |
| :---- | :---- |
| git checkout my-pull-request-branch | Change to your pull request branch ie.  git checkout trishaoconnor\_tcw31update |
| git rebase \-i HEAD\~n | Replace the n with the number of commits that you wish to rebase ie.  git rebase \-i HEAD\~8 For the number of commits, check the pull request on GitHub  |
| Replace `pick` with `drop` for the commits you want to discard. | A list of commits is generated, there will be a line for each commit which will contain the text `pick <commit id>`. The default label for each commit in the file is `pick`, so for every commit you want to drop, manually change the text `pick` to `drop`  |
| Save your changes and exit the editor (Ctrl \+ X) |  |
| git push \--force-with-lease | Pushes your changes to the pull request, removing any commits that you marked as `drop` and adding only the commits that you left marked as `pick`  |


### Working with forks from remote repositories
#### Adding a fork from a remote repository  {#adding-a-fork-from-a-remote-repository}

`$ git remote add  YOUR\_LOCAL\_NAME\_FOR\_OTHER\_REPO  URL\_OF\_OTHER\_REPO`

`$ git fetch  YOUR\_LOCAL\_NAME\_FOR\_OTHER\_REPO`

`$ git checkout \-b  YOUR\_LOCAL\_NAME\_FOR\_BRANCH  YOUR\_LOCAL\_NAME\_FOR\_OTHER\_REPO/BRANCH\_NAME\_IN\_OTHER\_REPO`

`$ git pull`

`$ \# make & commit changes as needed`

`$ git push  YOUR\_LOCAL\_NAME\_FOR\_OTHER\_REPO  HEAD:BRANCH\_NAME\_IN\_OTHER\_REPO`

| Example (cf. [\#2691)] (https://github.com/TEIC/TEI/pull/2691))|
| :---- |
| `git remote add jbampton git@github.com:jbampton/TEI.git` |
| `git fetch jbampton` |
| `git checkout \-b jbampton\_fix-spelling jbampton/fix-spelling` |
| `git pull` |

#### Merging dev into a fork from a remote repository {#merging-dev-into-a-fork-from-a-remote-repository}

| Example (cf. [\#2844](https://github.com/TEIC/TEI/pull/2844)) |
| :---- |
| `git remote add rettinghaus git@github.com:rettinghaus/TEI.git` |
| `git fetch rettinghaus`  |
| `git checkout \-b rettinghaus\_issue-2459 rettinghaus/issue-2459` |
| `git pull` |
| `git push rettinghaus HEAD:issue-2459` |

### [Merging local uncommitted changes to a new branch](https://stackoverflow.com/questions/556923/how-do-i-merge-my-local-uncommitted-changes-into-another-git-branch/556986#556986) {#merging-local-uncommitted-changes-to-a-new-branch}

| Command | Function |
| :---- | :---- |
| git stash  | Stashes your uncommitted local changes |
| git checkout branch2  | Switches to branch2 (change with your_name\_2 etc) |
| git checkout \-b branch2  | Creates and switches to new branch |
| git stash pop  | Pops your stash of uncommitted local changes into the new branch |

