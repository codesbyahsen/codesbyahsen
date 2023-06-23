# Git Handbook
Introduction to the git commands. In this guide, we will explore the functionality and usage of Git.
<br/> <br/>


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
git stash push -m "Message here"
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