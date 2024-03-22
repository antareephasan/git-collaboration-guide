# Git Collaboration Guide
A guide for helping new comers to use git for team projects.

## Topics
- Basic Commands
- Working In Team

*Keywords* :
Reposity, repo, Remote, Local, recurisive, directory, upstream

## Basic Commands

- **Init**: User for initializing an empty local repository

- **Add**: Add a file in the git stage

- **Push**: Used for pushing code changes into a remote repository

- **Commit**: Used for listing changes into existing local repository

- **Pull**: Used for pulling new codes from a remote repository

- **Clone**: Used for cloning a remote repository  

- **Checkout**: Used for switching branches or creating new one

- **Merge**: Used for merging 2 different branches of same git repository

- **Stash**: More like commit, stages and saves changes of the current working branch


## Create a repository

- Go to your github and click create repository
- Give a name for the repo
- Give a description (optional)
- Select private or public (private means no one else can access this repo and public means everyone can access)
- Click create
- Now you need to connect the created repo in your local machine where your code is or where you will start writing code
- navigate to your folder in a command line or shell
- write this commands one by one
- `git init` this will initialize a local repo
- `git add .` this will stage the current directory
- `git commit - m "message"` this will log the files in the directory
- `git branch -M main` this will mark the main branch as master
- `git remote add origin https://github.com/antareephasan/git-collaboration-guide.git` this will connect the remote repository you created with local repo
- `git push -u origin main` this will finally push the files into the remote repository.
- `-u` means upstream branch, this is used so that you don't have to include `origin branchname` everytime you push

## How to clone a Remote Repository?

- Visit the Remote repository you want to clone
- Copy the HTTPS web URL for the repo which may look like this `https://github.com/antareephasan/spotify-clone.git`
- open command in your local machine
- navigate to your desired directory where you want to clone and execute this command
- `git clone https://github.com/antareephasan/spotify-clone.git`

## How to Commit changes and Push in a Remote Repository

- this will only work if you have already created and connected a remote repository with this directory.
- Add the file or files you want created or changed using `add` command
- example: `git add Readme.md`
- You will usually see peeple using `.` . This dot (.) means the all the files in the current directory recurisively.
- after adding your files, you have to commit the changes.
- to commit use this command `git commit -m "First commit"
- Here the -m means the message for the commit
- After commiting you need to push the code in the remote repository
- use this command for push `git push origin main`
- here the main 

## WTF is Stash

- Stash is a way to save your current branch changes in your local repository which you can pop back later
- This is used when your main/master branch is ahead of your current working branch
- In the above scenario if you try to merge your main branch with you current branch you can loose your current branch new changes.
- For avoiding this scenario you stast or commit your current branch changes and then merge the main/master branch.
- After merging you pop back your changes in your current branch.
- If the main branch and your current branch has changes in the same directory it may have conflicts. Git will show you the conflicts which you have to manually resolve.


# Team Work

- Let's talk about the team work scenario first.
- Imagine 3 person which can be your friends or colleague, working on a project as a team.
- So the team came to a decision to use git for the project where all the members can work on the same repository.
- First, one of the members creates a repository and invites all other members into the repo for proper permissions.
- Then one of the member does some inital setup and pushes the code into the main repository.
- All of the members has been given different feature to work on. Let's say you got the ProfilePage section.
- Now how will you start?

## Let's Dive in
*Assuming you have the basic knowledge of git operations and at least created a single reposity and pushed code in it*
*If not you can start reading from the begining of this guide**

**Her some example links and names is used for the guide**

Repository Name: `expense-tracker`
The repostiry HTTPS URL : `https://github.com/touhid-hossain/expense-tracker.git`
The main branch name is: `main`
The branch you will be using : `test-branch`

## First Step
- First Open a command prompt or shell (Windows prompt, git bash, linux command shell etc.)
- cd to the directory where you want to keep your project and clone it
- `git clone https://github.com/touhid-hossain/expense-tracker.git`
- Now you have the initial setup file
- Now create a branch for your work let's name it `test-branch`
- `git checkout -b test-branch`
- now if you run `git status` you will see you are the test-branch.
- Now write your code and commit changes and then push to the newly created-branch
- Now what if  your other team members already did some changes and merged with the main repository???
- In that case if you try to merge your branch with the main branch there will be a lot of conflicts
- To avoid this issue you must pull from the main branch to have up to date code. This is a important practice.
- To do this first your need to commit your current working branch(test-branch) changes or stash the changes.

1 **Commit Option**
- For commit run these commands
- `git add . `
- `git commit -m "message"`
  
2 **Stash Option**
- For stash run this command
- `git stash`
  
## Pulling Main
- after executing them checkout to main branch
- `git checkout main`
- then pull the latest code from the main branch
- `git pull origin main`
- then go back to your working branch `test-branch`
- `git checkout test-branch`
- Now you will see you don't have the new code yet for that you need to merge the main branch with this branch
- To do that run this command `git merge origin/main`
- Now you will see you have the latest code.

**Commit option:** *If you have choosen the commit option continue or jump to stash option*
  
- If you have choosen the `commit` option you will see that your changes and latest changes from main is there.
- You might have conflicts if you and your other members have worked on same files.
- Git will point out these conflicts and you will have to resolve them manually.
  
**Stash option:** *If you have choosen the commit option continue from next section*
  
- If you have choosen the stash method then you will not see your changes in the test-branch.
- For bringing your changes back you either have to pop your stash. For that run the below command
- `git stash pop`
- Now you will see your changes mergerd with the latest main branch changes.
- You might have conflicts if you and your other members have worked on same files.
- Git will point out these conflicts and you will have to resolve them manually.

## Finally Push the merged code

- After resolving conflicts if needed, now you can continue and stage, commit and push your branch. run the below commands for that
- `git add .`
- `git commit -m "new chnages`
- `git push origin test-branch`
- To avoid conflicts team members should work on different files at a time.

## Merge branch with Main

- Now go to Github and create a pull request from your working branch (test-branch)
- If no conflicts you can finally Merge.
- Or if you have senior developers who will review your code and they will merge the changes for you.

## Continue Same Steps for next feature

- After merging, now your branch and the main and has the same code
- If no need you can delete the test-branch or if you prefer you can work on the same branch for next update.
- Follow the same steps.
  
**Remember:** *Pull from main branch before pushing for having latest codes and avoid conflicts*

**Tip**: *avoid conflicts team members should work on different files at a time.*








