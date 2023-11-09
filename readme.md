#   Setting-up-ssh-key-with-github-for-ubuntu
-   SSH stands for Secure Shell. SSH is a way to securely communicate with a remote computer. SSH is used for executing commands remotely by interacting with another system’s operating shell.
-   Using SSH, you can connect with GitHub without supplying your username and personal access token in each visit.

##  Prerequisites
-   Ubuntu server
-   GitHub Account

Step 1: Generating a new SSH key
-   Open your terminal and use the following line to create a new SSH key. In the place of email@gmail.com , enter the mail to which your GitHub account is linked.

```
ssh-keygen -t rsa -b 4096 -C "email@gmail.com"

```
-   Press Enter to save the key in the default location.

Step 2: Enter the passphrase
To add an extra layer of security, you can add a passphrase to your SSH key.
You can add the passphrase and save it on ssh-agent. If you don’t want to add it just proceed to the next step by pressing Enter twice.

Step 3: Adding your SSH key to ssh-agent
We can add our key using the following line
`
eval "$(ssh-agent -s)"

`
`
ssh-add ~/.ssh/id_rsa

`

Step 4: Add your key to GitHub
-   In order to get our key, use the following command
`
cat ~/.ssh/id_rsa.pub

`
-   Then copy the content (starting from ssh-rsa). Now open your GitHub account and do the following steps :

-   Click on your profile in the top right corner and select Settings from the drop-down box.

![git setting menu](./git-account.webp)

-   Now from the Account Settings section present on the left, select SSH and GPG keys

![git ssh key menu](./git-profile-ssh-menu.webp)

-   To add a new key, Click on New SSH key

![git add new ssh menu](./new-ssh-key.webp)

-   Under the title section, add a name to your key. Then in the key section, paste the key that we copied from our terminal. Finally, click on Add SSH key

##   You have successfully added a new SSH key to your GitHub account. Hope you found it useful.

#   Let's clone your reposirtory
-   git clone <ssh url>
`git clone git@github.com:dineshpithiya/setting-up-ssh-key-with-github-for-ubuntu.git
`
