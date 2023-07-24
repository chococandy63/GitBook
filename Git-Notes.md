
# GIT THEORY
<br>

### What is Git?

- ```Git``` is a version control software that stores your code, tracks the code changes, and let you see them whenever required.<br><br>
- It is Open Source and can be downloaded on git-scm.com. <br><br>

### What is Github?

```Github``` is a website that interacts with Git version control which let developers collaborate and participate in open source contributions, 
 and performs the operations on their project or repositories.<br><br>


### Github workflow?

#### - Branching
If you want to work on a exisiting project that is posted on github then all of the code that is on
production is stored in a master branch but if you want to make changes to the exisiting
codebase then create a new branch.

```Important```: Always create a new branch and avoid making changes directly to the master branch.
Create a new branch that seems like exact replica of the master branch.

#### - Commits
- After creating a branch, you introduced a set of changes. 
- Make a commit which stores those changes  by taking
a snapshot of your project/repo at that point in time. 
- Once you commited few changes then you open a PR.


#### - Pull Request 
```PR``` lets you compare the branch you made and the master branch.
Developers can look at the differences and if those differences are appropriate then
creator of that project might accept your PR or can also suggest some changes.


#### - Collaborate
Further you can add more commits to improve your code and finally send a PR which is (let say) accepted.
Congrats, you are successful in collaborating to this project.

#### - Merge 
Creator will merge your PR if he/she finds it bug-free and acceptable.
This is done by adding your new branch and commits to the master branch.
All of those snapshots are in the production branch.<br><br><br>


### GITHUB workflow for open source
If you want to make changes to projects where you dont have ```write access``` then you  
will have to follow this open source workflow.

##### - FORK
If you are forking any project then you are creating a exact copy of repo  under your account.

##### - Why forking?
Because we dont have ```write permissions``` to original repo.

##### -How to contribute?
       Step1: Create a fork.
              Now, You have write access to your forked repo. 
       Step2: Make commits on your fork.
       Step3: Open pull request directly from     
              your forked project to original project.
<br><br><br>

### Working on project locally?


##### - Working on project remotely

Working on github.com then you are working on remote repository. 

##### - Working locally
- To do that you need to clone the repo.
- Git is distributed so you can have the copy of the entire project on your own computer.
- Git lets you work on those repository locally in your system without any network coonection and continue your work.


##### - Cloning repo
```Cloning``` means creating a copy of a repo. 
If you want to work on a project on your own develpment environemnt then u have to clone 
the repo.You can easiy clone on pc by using github desktop app, terminal or IDE.

    - You can still communicate with the remote repo that is stored on github.com. you have to sync the changes manually.

    - When you push changes to remote then somone else can pull those changes to their own local environment.
<br><br><br>

## Git Basic commands(working with command line)

-> `git clone {repo_url}` Cloning a repo down to your local machine

-> `git pull` Bringing down the changes from remote repo to your local machine
 
-> `git branch` Creates a branch on your local machine

-> `git checkout` Checking out a branch means whatever changes you are making on a 
branch you want them to be inside this specific branch

-> `git status` Tells you whats going on. You can use this command at any point in time.

Now you have created a new branch and introduced some changes and want to send a PR, for that:<br>

-> `git add {folder_name}` Adds the files that you have changed

-> `git commit -m "commit-message"` Stores your changes as commits

-> `git push` Push the changes made locally to remote repo

or

-> `git push origin master` Origin sets the location of our git repo and master is the branch where we want to push.
<br><br>

### Commit?
It is repesented by 40 characters SHA 1 hash,
in those 40 characters, there is a blob of changes which
is a reduced version of that code, it also includes the 
metadata and what is the parent commit, all this data is stored and
compressed in that 40 characters sha 1 hash which means
that commit id is very very important.
<br><br>

### 2 step commit?
Why to use ```git add``` and ```git commit``` ?
- Git lets you choose exatly which files you want to include in the next commit so you add that file 
- Git add and it moves the file to the staging area where git commit only includes that particular file.
- All those snapshots are stored in a 40 characters SHA 1 history.
<br><br>

### Git merge?
A PR can be merged directly on github.com (remote)
you can merge the branches to the master branch
using. You can also merge locally by git merge.

`git merge`
<br><br>

### Merge conflicts?
A ```Merge conflict``` occurs when there is a change in the same
file in the same line on two branches you are trying to merge 
together.

GIT tells you theres a merge conflict,
next step will be to check:<br>

`git status` tells exactly which files will have a conflicts in them.
Then open those files and look for
these merge files markers

> <<<<<<<<<<<<< HEAD ==============
> >>>>>>>>>>BRANCH A

Pick a version of code that you need and remove the other one, one version will be above equal sign and other will  be below,

Save those changes and commit them, GIT will know that merge conflict has been resolved.
<br><br>

### Divergent Branches?

when two branches don't have a common commit their history, they are called divergent
when you showed git log as graph, everytime you saw that the branches had a common commit back in history


### Git rebase?
- When you introduce a changes in branch and later find those changes irrelevant or maybe wrong.<br>
- Then you use git rebase to change
the history,
you may want your history to be reflective of different natue
and you may want your history to show the changes and make it more linear,
that's where you use git rebase.
<br><br>

### How to Delete Git Remote Origin from Repository Using git remote rm origin Command?

To remove the remote origin from a Git repository, first, switch to the Git repository and check the remote list. Then, run the “$ git remote rm origin” command and verify it by executing the “$ git remote -v” command.


### How do I undo my Last Commit?

- ```Git revert```: when u revert you are not technically undoing a commit, you are creatng a new commit with the
exact opposite changes of whichever commit that you would undo
- This means commit id remain unchanged so its safe
to do changes to the commit that you already pushed to 
remote repo.

- ```git reset``` - for local 
- ```git commit-amend```- not to undo history but to change the commit message
- ```git cherry-pick```- doesnt undo a comit but it does actually change a commit id

Be careful when u are changing a commit id and that commit is already on remote
repo
<br><br>

### Pull request?
- It is a request to have your code pulled into another branch. 

- If you want your code to pulled from feature branch
to master branch then you make a PR from feature branch to master branch.

- Once you made a PR, anyone can review your code, make changes and suggest you some changes.

- You can also make update your code after creating a PR by making additional commits and then pushing them into github.

- Once your PR is being merged its a good practice to delete your feature branch and switch back to master branch
and then again if you want to make changes you create a new branch and then follow the same steps.
<br><br>

### Some more useful git commands:

- ```git log --oneline```  shows the log in one line(title of the commit made with the hash and branch)

- ```git init``` initiliaze git repo in any folder


- ```git remote add origin {link}``` create a remote refrence

- ```git remote -v``` check if the remote refrence is beig created or not. It shows all the remote repos connected to this repo.

- Whenever you create a new branch then you haave to set the upstream(on which branch you want to push).
- ```git push -u origin master``` the ```-u``` flag is used to set the upstream which tells the location where you have 
to push by default.
- Now in future you can only type git push to push the changes without using ```-u origin master```.

- ```git checkout {branch_name}```  switch between branches.

- ```git branch``` to list the branches.

- ```git checkout -b {new_branch_name}``` create a new branch.

- ```git diff``` check the chanes we done to code, shows the lines of code that we changed.

When you merged a branch then it is being merged to master only on remote repo but not on your local system
you need to explicitly run command to pull down those changes to your system to work further.
```Important```: Avoiding this step may cause merge conflicts later.

- ```git pull``` Now your local master branch is updated and you can see the changes that are being merged.

- ```git branch -d {name-of-branch-you-want-to-delete}``` Deleting your used branches because you dont really reuse them again.

- ```git log``` log of all the commits, arranged in reverse chronological order. You can see the latest commit at the top.
<br><br>


### Undoing your changes:

```UNDO``` your commits.
If you changed a file index.html and added that file ```git add index.html```
after running ```git status```, you can see that the file is being staged but what if you want to undo your stages.

Undo your stages:<br>
- ```git reset {file_name}``` or ```git reset```

Now```git status```, you can see the file is no longer staged.

Undo a commit:<br>

- ```git reset HEAD~1```  Head is the pointer to the last commit and ```~1``` tells the git that instead of pointing to the last commit, you want to go back
1 commit further so that head will point 1 commit further that will completly undo the commit.

```git status``` shows that it unstaged and uncommited those last changes.


Next if you do ```git diff```

You can see the changes.

If  you have many different commit, you might want to go back to a specific commit.
for that you dont have any multiple pointers in git like  ```HEAD```
instead you can use ```git log``` to see the history of commits where you can 
copy the ```hash``` of the commit. Suppose if you want to switch to any other commit then copy its hash.
 
- To unstage the changes: ```git reset {hash_of the commit}```

- To unstage as well as remove: ```git reset --hard {heash of the commit}```

You can see that ```HEAD``` is pointing to a different commit.
<br><br>

## Tools & Concepts for Mastering Version Control with Git:

Next Blog :)













