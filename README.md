# gitReference
Reference document for using Git

### Basic Snapshotting
    git add .
Update the index using the current content found in the working tree to prepare the content for the next commit

    git status
Display paths that have differences between the index and the current HEAD commit

    git commit -m "<message>"
Record changes to the local repository using the given `<message>` as the commit message


### Sharing and Updating Projects
    git push
Update the remote repository with the committed objects

    git pull
Incorporate changes from a remote repository into the current branch


### Branching
    git branch
Show all of the local branches of your repository, the starred branch is the branch you are on

    git rev-parse --abbrev-ref HEAD
Show only the name of the branch you are on

    git fetch
Fetch branches and/or tags (refs) from the remote repository

    git checkout <branch>
Switch to the specified `<branch>`

    git switch <branch>
[EXPERIMENTAL] Switch to the specified `<branch>`

___


### Typical Workflows
###### First-Time Local Set Up 

1. Set your user name

        git config --global user.name "FirstName LastName"

2. Set your user e-mail address

        git config --global user.email "email@example.com"

###### To create a new local repository and sync with newly created remote

1. On the GitHub web site, create a new repository

2. On your local machine

    a. Initialize the local directory as a Git repository
   
        git init
        
    b. Add the files in your new local repository, this stages them for the initial commit
   
        git add .

    c. Commit the files that you have staged in your local repository
   
        git commit -m "Initial commit"

    d. At the top of your GitHub repository's "Quick Setup" page, click to copy the \<remote repository URL> field
 
    e. In the terminal, add  \<remote repository URL> where  local repository will be pushed
 
        git remote add origin <remote repository URL>

    f. Verify the new \<remote repository URL>


        git remote -v
 
    g. Set to the master branch
 
        git branch -M master

    h. Push the your initial local repository to GitHub
 
        git push -u origin master

###### To update your local and remote repository with current changes

    git add .
    git status
    git commit -m "<message>"
    git push

###### To update a repository on a local machine

    git pull

###### To create (and switch to) a new branch

1. On the GitHub web site, in the repository that you would like to create a new branch of, pull down the `Branch:` button and type the name of the new branch in the "Find or create a branch..." box (typical branch naming is `feature/<description>` where <description> is a short moniker for the purpose of this branch (*e.g.* `feature/conan` to indicate a branch where Conan C/C++ package manager features were added)

2. On your local machine

        git fetch
        git checkout <branch>
        git branch
        
###### To switch another branch

    git checkout <branch>

___


### Set Up SSH Key Authentication

Most Git servers (like GitHub) can authenticate using a SSH public key. In order to provide a public key, you must generate one (you should check your `~/.ssh` directory for files named `id_rsa` and `id_rsa.pub`, your private and public key, respectively, before creating new ones).

This process is similar across all Linux operating systems.

###### SSH Key Generation

1. To generate a public/private key pair, simply type

        ssh-keygen

 You can accept the default name for the private key.  Be sure you enter a passphrase (and re-enter it) when prompted.

2. To display your public key, type

        cat ~/.ssh/id_rsa.pub

###### Add Your SSH Key to GitHub 

1. Copy the SSH key displayed above to your clipboard

2. On the GitHub site

   a. In the upper-right corner of any page, click your profile photo, then click **Settings**

   b. In the user settings sidebar, click **SSH and GPG keys**

   c. Click **New SSH key** or **Add SSH key**

   d. In the "Title" field, add a descriptive label for this key. For example, if you're using a personal Mac laptop, you might call this key "MacBook Pro"

   e. Paste your SSH key into the "Key" field

   f. Click **Add SSH key**

   g. If prompted, confirm your GitHub password

