# Git Handbook
Introduction to the git commands. In this guide, we will explore the functionality and usage of Git.
<br/> <br/>


## Table of Contents
- [What is Git?](#what-is-git)
- [Prerequisite](#prerequisite)
- [Check Git Version](#check-git-version)
- [Configuration - First Time Git Setup](#configuration---first-time-git-setup)
  - [Set Default User](#set-default-user)
  - [Set Default Editor](#set-default-editor)
  - [Handle Line Endings (Detail)](#handle-line-endings-detail)
  - [Set Default Branch Name](#set-default-branch-name)
  - [Check Settings](#check-settings)
- [Get Help](#get-help)
- [Initialize a Repository in an Existing Directory](#initialize-a-repository-in-an-existing-directory)
- [Add Local Git Repository to GitHub](#add-local-git-repository-to-github)
- [Clone an Existing Repository](#clone-an-existing-repository)
- [Check the Status of Files](#check-the-status-of-files)
- [Track New Files](#track-new-files)
- [Remove Files from Staging Area](#remove-files-from-staging-area)
- [Ignore Files from Track](#ignore-files-from-track)
- [Move Files](#move-files)
- [First Commit](#first-commit)
- [Check Commit Message](#check-commit-message)
- [Show the Changes in Files](#show-the-changes-in-files)
- [Fetch Changes to Git Repository from Remote](#fetch-changes-to-git-repository-from-remote)
- [Fetch Changes to Working Directory from Remote](#fetch-changes-to-working-directory-from-remote)
- [Push to Remote](#push-to-remote)
- [Inspect a Remote](#inspect-a-remote)
- [Create Branch for Feature or Issue](#create-branch-for-feature-or-issue)
- [Set Branch Upstream and Push](#set-branch-upstream-and-push)
- [Check Branch](#check-branch)
- [Switch Branches](#switch-branches)
- [Merge a Branch](#merge-a-branch)
- [Check Merged Branches](#check-merged-branches)
- [Delete a Branch](#delete-a-branch)
- [Delete a Remote Branch](#delete-a-remote-branch)
- [Git Stash](#git-stash)
  - [Stash All Files](#stash-all-files)
  - [Stash All Files with Message](#stash-all-files-with-message)
  - [Stash Untracked Files](#stash-untracked-files)
  - [Stash Specific File](#stash-specific-file)
  - [Stash Specific File with Message](#stash-specific-file-with-message)
  - [Show Stash List](#show-stash-list)
  - [Restore All Stashes](#restore-all-stashes)
  - [Restore Specific Stash](#restore-specific-stash)
  - [Delete All Stashes](#delete-all-stashes)
- [Git Reset](#git-reset)
  - [Git Reset Soft](#git-reset-soft)
  - [Git Reset Hard](#git-reset-hard)
- [Git Remote Setup with SSH Key](#git-remote-setup-with-ssh-key)
  - [Setup in Linux (Ubuntu)](#setup-in-linux-ubuntu)
  - [Setup in Windows](#setup-in-windows)


## **What is Git?**
Git is an open-source distributed version control system.

Version control systems help software teams in effectively managing changes to the source code of a product or service over time. By maintaining a database that tracks all modifications, they enable developers to revert to a previous version before any critical mistakes occurred. This safeguards the source code from disasters, human errors, and unintended consequences.
<br/> <br/>


## **Prerequisite**
Download and install git [here](https://www.git-scm.com/downloads)
<br/> <br/>


### **Check Git Version**
```
git --version
```
<br/> <br/>


### **Configuration - First Time Git Setup**
Setting global configuration variables is crucial, particularly when collaborating with other developers. It offers several significant benefits, such as facilitating the identification of the individual responsible for committing a specific code block. This capability enhances accountability and helps in effective collaboration within a development team. Example
<br/>


#### **Set Default User**
```
git config --global user.name "Ahsen Alee"
```

```
git config --global user.email ahsenalee@example.com
```
<br/>


#### **Set Default Editor**
It sets defualt editor, in my case I am using [VSCODE](https://docs.github.com/en/get-started/getting-started-with-git/associating-text-editors-with-git).

```
git config --global core.editor "code --wait"
```
<br/>


#### **Handle Line Endings ([Detail](https://docs.github.com/en/get-started/getting-started-with-git/configuring-git-to-handle-line-endings?platform=windows))**
For Windows:
```
git config --global core.autocrlf true
```

For Linux/MacOS:
```
git config --global core.autocrlf input
```
<br/>


#### **Set Default Branch Name**
By default Git will create a branch called `master` when you create a new repository with `git init`.
```
git config --global init.defaultBranch main
```
<br/>


#### **Check Settings**
```
git config --list
```
<br/> <br/>


### **Get Help**
```
git help config
```

```
git config --help
```
<br/> <br/>


### **Initialize a Repository in an Existing Directory**
Move in a your project folder using `CLI` 
For Windows:
```
cd C:/Users/user/my_project
```

For Linux:
```
cd /home/user/my_project
```

For MacOS:
```
cd /Users/user/my_project
```

and type then hit enter
```
git init
```
<br/> <br/>


### **Add Local Git Repository to GitHub**
```
git remote add origin https://github.com/example/example.git
```
<br/> <br/>


### **Clone an Existing Repository**
```
git clone https://github.com/example/example.git
```
<br/> <br/>


### **Check the Status of Files**
```
git status
```
<br/> <br/>


### **Track New Files**
For single file
```
git add README.md
```

For all files
```
git add .
```
Or
```
git add --all
```
<br/> <br/>


### **Remove Files from Staging Area**
For single file
```
git rm README.md
```
Or
```
git reset README.md
```

For all file
```
git reset
```
<br/> <br/>


### **Ignore Files from Track**
If you want to prevent certain files from being visible to others in your repository, such as files containing personal preferences or IDE-specific configurations, you can take the following steps:

```
touch .gitignore
```

To define which files should not be added to the Git repository, you can open the `.gitignore` file using a text editor. This file can be edited just like any other text file. You can enter specific rules or patterns into the file to indicate which files or directories should be ignored by Git. For example:

```
.project
```

```
*.js
```

Wildcard characters can be utilized in the .gitignore file to define broader patterns for ignoring files. In this example, a wildcard character is employed to specify that all files ending with the `.js` extension should not be added to the repository.
<br/> <br/>


### **Move Files**
```
git mv file_from file_to
```

For example
```
git mv README.md README
git rm README.md
git add README
```
<br/> <br/>


### **First Commit**
After adding all files in staging area make your first commit message
```
git commit -m "The commit heading" -m "The commit description"
```
<br/> <br/>


### **Check Commit Message**
```
git log
```

For short details
```
git log --oneline
```

For short and pretty
```
git log --pretty=oneline
```
<br/> <br/>


### **Show the Changes in Files**
```
git diff
```
<br/> <br/>


### **Fetch Changes to Git Repository from Remote**
This command bring changes to local git repository not in working directory

For single branch
```
git fetch origin <branch name>
```

For all branches
```
git fetch --all
```
<br/> <br/>


### **Fetch Changes to Working Directory from Remote**
This command bring changes to local git repository and in working directory
```
git pull origin <branch name>
```

For example
```
git pull origin main
```
<br/> <br/>


### **Push to Remote**
```
git push origin <branch name>
```

For example
```
git push origin main
```

Or just
```
git push
```
<br/> <br/>


### **Inspect a Remote**
```
git remote show origin
```
<br/> <br/>


### **Create Branch for Feature or Issue**
```
git branch <branch name>
```

For example
```
git branch testing
```
<br/> <br/>


### **Set Branch Upstream and Push**
```
git push --set-upstream testing
```
Or
```
git push -u origin testing
```
<br/> <br/>


### **Check Branch**
It shows all local branches in the repository
```
git branch
```

For both local and remote branches
```
git branch --all
```
Or
```
git branch -a
```
<br/> <br/>


### **Switch Branches**
```
git checkout testing
```
<br/> <br/>


### **Merge a Branch**
First checkout to the `main` branch you want to merge with and take a pull
```
git pull origin main
```

then merge with `testing` branch and push the changes
```
git merge testing
git push origin main
```
<br/> <br/>


### **Check Merged Branches**
```
git branch —-merged
```
<br/> <br/>


### **Delete a Branch**
```
git branch -d testing
```
<br/> <br/>


### **Delete a Remote Branch**
```
git push origin --delete testing
```
<br/> <br/>


### **Git Stash**
The git stash command is used to capture the current state of both the working directory and the index, allowing you to revert to a clean working directory while preserving your local modifications. This command effectively saves your changes temporarily and reverts the working directory to match the latest commit `HEAD` in the branch.

#### **Stash All Files**
```
git stash
```
<br/>


#### **Stash All Files with Message**
```
git stash save "Message here"
```
<br/>


#### **Stash Untracked Files**
```
git stash --include-untracked
```
<br/>


#### **Stash Specific File**
```
git stash push <filename>
```
<br/>


#### **Stash Specific File with Message**
```
git stash push -m "Message here" <filename>
```
<br/>


#### **Show Stash List**
```
git stash list
```
<br/>


#### **Restore All Stashes**
```
git stash apply
```
Or
```
git stash pop
```
<br/>


#### **Restore Specific Stash**
```
git stash apply stash@{0}
```
Or
```
git stash pop stash@{0}
```
<br/>


#### **Delete All Stashes**
```
git stash clear
```
<br/><br/>

### **Git Reset**
The git reset command is used to move the `HEAD` (the current branch pointer) and, optionally, the staged changes in the index, to a specific commit.

#### **Git Reset Soft**
`git reset --soft` is used to move the `HEAD` and the current branch pointer to a specific commit, but it does not change the working directory or the staged changes in the index. 
```
git reset --soft <desired_commit_hash>
```
<br/>


#### **Git Reset Hard**
`git reset --hard` is used to move the `HEAD`, the current branch pointer, and the working directory to a specific commit, and it forcefully discards all changes and staged modifications that are not part of that commit
```
git reset --hard <desired_commit_hash>
```
<br/><br/>

### **Git Remote Setup with SSH Key**
`SSH` is stand for _Secure Shell_ and primarily used for secure remote access to servers and devices.
<br/>


#### **Setup in Linux (Ubuntu)**
Ensure that all `SSH` key creation operations are conducted within this folder.
```
cd ~/.ssh
```

Generate `SSH` key pairs using the ssh-keygen command:
```
ssh-keygen -o -t rsa -C "ahsenalee@example.com"
```

To view the `SSH` key from the file use `cat` command
```
cat id_rsa.pub
```
<br/>


#### **Setup in Windows**
Generate `SSH` key
```
ssh-keygen -o -t rsa -C "ahsenalee@example.com"
```
The Windows `SSH` keys live in the `.ssh` folder under the current user’s home directory.

To open in shell use following command `cd <folder_location>`:
```
cd C:\Users\Owner\.ssh
```

To view the `SSH` key from the file use `type` command for _cmd_ or `Get-Content` for _powershell_

CMD
```
type id_rsa.pub
```

PowerShell
```
Get-Content id_rsa.pub
```
