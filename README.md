# What is Git?

- Git is a free version control system designed to handle projects with speed and efficiency
- It allows you to track changes to your code over time
- Enables you to collaborate with others on the same codebase
- It provides a record of all changes made to your code, i.e who made them and when which is useful for debugging and auditing



## Git Basics

### Key Terms

- **Fork**: A copy of a repository.
- **Repository**: A directory containing all project files.
- **Commit**: A unit of change.
- **Clone**: A copy of a repository on your local machine.
- **Origin**: The default remote name for a cloned repository.
- **Head**: The current branch being worked on.
- **Index**: The directory with files ready to be committed.
- **Push**: Sending commits to a remote repository.
- **Pull**: Fetching and merging changes from a remote repository.
- **Fetch**: Retrieving changes from a remote repository.
- **Staging area**: The directory that contains the files that are ready to be committed.
- **Working Directory**: The directory with files currently being worked on.
- **Branch**: A version of the codebase.
- **Checkout**: Switching between branches.
- **Merge**: Combining changes from two branches.

### Common Tasks

- Create a repository.
- Create a branch.
- Delete a branch.
- Make changes to a file.
- Commit changes.
- Stage changes.
- Push changes to a remote repository.
- Add files.
- Pull changes from a remote repository.
- Merge changes.
- Check the status of your working directory.
- Revert changes.

## Configuration

git config --global user.name "Your Name"
git config --global user.email "Your email"

## Git commands

. git init - Create a new local repository

This command initializes an empty Git repository in the selected folder.

#Create a new directory called my-project
$ git init my-project

. git status - show the status of the current branch
i.e Check for uncommitted changes

#check the status of the current branch

$ git status  # on branch main

. git clone - Clone a repository that already exists om GIthub to your local machine

$ git clone project-name 
#make sure to copy the URL from the repository you want to clone

. git add - Add files to the staging area

$ git add . # changes to be committed:
#when you add the dot, it adds all files in the current directory

$ git add file-name
#when you add file name, it adds the file with the name you specified

. git commit - commit changes to head (but not yet to remote repository)

$ git coommit -m "commit message"

. git pul - fetch and merge the changes from the remote main branch into your local main branch.

$ git pull origin main 
i.e 
From https://github.com/CliveOuma/student-management-system
 * branch            main       -> FETCH_HEAD
Merge made by the 'ort' strategy.
 README.md | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

. git push - push changes to remote repository (e.g Github)

$ git push origin main
i.e
Enumerating objects: 54, done.
Counting objects: 100% (54/54), done.
Delta compression using up to 4 threads
Compressing objects: 100% (49/49), done.
Writing objects: 100% (53/53), 339.15 KiB | 3.69 MiB/s, done.
Total 53 (delta 5), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (5/5), done.
To https://github.com/CliveOuma/student-management-system.git
   51e9e40..5afa07c  main -> main

. git fetch - Fetch changes on the remote server to your local main branch

$ git fetch origin main
i.e
remote: counting objects: 4, done.

. git merge - Merge a branch into a branch you are currently on

$ git merge branch-name 

. git branch - List, create, delete branches

i.e
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git branch
* master

$ git branch -d branch-name # Delete branch

. git checkout - switch branches or restore working tree files

$ git checkout branch-name # Switched to 'branch-name'

$ git checkout -b branch-name  # Create and switch to a new branch  "branch-name"

.git remote - Manage set of tracked repositories

$ git remote -v # checks configured remote repositories

$ git remote add origin <repository-url>
#If "origin" is not listed, you need to add it. Use the above command, replacing the URL with the actual URL of your remote repository:


$ git remote set-url origin <new-repository-url> # Verify repository url (Make sure the repository URL is correct. If you recently created the repository or if the URL has changed, update it using the above command)

. git log - show commit logs
          - view the history of a repository

$ git log # show commit logs

. git reset - Reset staging area to the last commit

$ git reset # i.e can be used to unstage files

. git rm - Remove files from the working tree and from the index

#Cleanup unnecessary files and optimize the local repository

$git gc

#Temporarily remove uncommitted changes and save them for later use

$ git stash

#Reapply previously stashed changes

$ git stash apply

$ git rm file-name # rm 'file-name'

. git mv - Move or rename a file, a directory

$ git mv file-from file-to # rename file1 => file2

. git diff - show the differences between teo commits, branches, filesor the working directory

$ git diff # diff --git a/README.md b/README.md

. git revert - Revert changes to a file

$ git revert file-name # Revert "Revert "Update README.md"


#This command fetches the changes from the remote main branch and merges them into your local main branch, even if the histories are considered unrelated.
After running the below command, you should be able to push your changes without encountering the "unrelated histories" error:

$ git pull origin main --allow-unrelated-histories

$ git push -u origin main --force
#Be cautious when using --force, especially if others are collaborating on the repository, as it rewrites history.

$ git config --global --add safe.directory
#The command adds an exception for the specified directory to the global Git configuration. It's essentially telling Git to consider this directory safe in terms of credential management.

$ git add -i
#This opens an interactive menu where you can selectively choose which changes to stage.



## Example Using vs code in my terminal

PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> cd C:\Users\clive.DESKTOP-4BRK07K\Documents\system
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git init
Initialized empty Git repository in C:/Users/clive.DESKTOP-4BRK07K/Documents/system/.git/
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git status
No commits yet

Untracked files:
        .gitignore
        my-backend/
        my-system/

nothing added to commit but untracked files present (use "git add" to track)
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git add .gitignore
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git commit -m "Add .gitignore file"
[master (root-commit) ed636d8] Add .gitignore file
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git commit -m "initial commit"     
[master bad08d2] initial commit
 38 files changed, 32988 insertions(+)
 create mode 100644 my-backend/Routes/AdminRoute.js
 create mode 100644 my-backend/Routes/StudentRoute.js
 create mode 100644 my-backend/package-lock.json
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git branch
* master
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git branch main
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git checkout main
Switched to branch 'main'
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git merge master
Already up to date.
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git remote add origin https://github.com/CliveOuma/student-management-system.git
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git push -u origin main
To https://github.com/CliveOuma/student-management-system.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/CliveOuma/student-management-system.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git pull origin main
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 874 bytes | 4.00 KiB/s, done.
From https://github.com/CliveOuma/student-management-system
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> origin/main
fatal: refusing to merge unrelated histories
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git pull origin main --allow-unrelated-histories
From https://github.com/CliveOuma/student-management-system
 * branch            main       -> FETCH_HEAD
Merge made by the 'ort' strategy.
 README.md | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> git push origin main
Enumerating objects: 54, done.
Counting objects: 100% (54/54), done.
Delta compression using up to 4 threads
Compressing objects: 100% (49/49), done.
Writing objects: 100% (53/53), 339.15 KiB | 3.69 MiB/s, done.
Total 53 (delta 5), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (5/5), done.
To https://github.com/CliveOuma/student-management-system.git
   51e9e40..5afa07c  main -> main
PS C:\Users\clive.DESKTOP-4BRK07K\Documents\system> 


## NB
- There are different Git workflows i.e Trunk, GitFlow, GitHubFlow
- The above guide is based on the GitHubFlow Workflow
