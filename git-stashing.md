


## Git Stash

`Stash` takes the uncomitted changes and put them aside while reverting your repo back to match the previous commit.


- Used when you want to temporarily put some files aside.
- Git stores stashes in a stack like structure. 
- You can store multiple stashes at a time each with their
individual files.
- They can be easily popped out of stack and applied whenever needed.
- When you are applying stashes there can be merge conflicts.

`git status`
lets you see that new files that you have created since your last commit, `git stash` can only work on the files that are
stashed... so you have to stash the files first by using `git add` command.

Now `git stash` will take all the files and put them aside and create a stack of all your stash entries.

You can see that by typing
`git stash list` to see all the entries 
and if you wanna see whats inside each entry then enter
`git stash show`.

Now if you do `git status` you will see that branch is clean, your files are safely stored and you can get them later whenever you want to work on them.

If you want to do that then enter
`git stash pop` which tells git to apply the stash on top of the head commit and remove the stash entry.

You can see that it says dropped stash entry.

### Naming Stash Entry

`git stash -m 'NAVBAR'`

`git stash list` contains all stash entry with readble names.

If you have stashed multiple commits and you want to unstash them but by simply running
`git stash pop` will drop the last commit that you stashed but lets say you want to pop any other stash.
For that you can specify the index of the stashes.
by entering

`git stash pop --index 1` will pull the stash which has index 1.

Entering `git stash list` doesnt show the stash that we just pulled. Hence, proved that the stash is deleted.

You can always drop a stash entry by entering

`git stash drop stash name` to delete any stash.

`git stash clear` to delete all the entries.

### Stash conflict: merge conflicts when u are doing git stash.


`git stash list`


`git stash pop 1`: Got a merge conflict, then the git abort the pop operation and put back the file to the stash
and tells us what the problem was, in this case the  `index.html` which is present in working directory has modifications
and those modifications conflict with some changes made to the same `index.html` from stash.

`git status`: `index.html` is modified

Also check `git stash show 1`: You can see there that the `index.html` is also modified.

Git doesn't know how to combine both of them, how do we fix it?

1. Stash the working directory changes in their own stash
and apply the navigation component after that, no merge conflict in this case because we reverted the working directory back to a
clean slate,

2. Popping out those changes into a second branch using 
`git stash branch`.
Then later you can merge that branch to your main branch using `git merge`.

`git add .`
`git commit -m "added logo"`
(Now we have commited)
`git stash pop`:
You will see the stash conflict.

Open that file and look for these weird markers:
`<<<updated upstream ===========      >>>>stashed changes`

Goal is to manually replace this. Save and exit.

`git status`: Again nothing actually changes because we have to stage.
`git add index.html`
`git status`: No merge conflict 

You can technically move on but you should create a new coomit: `git commit -m "xyz"`

`git log --oneline`

`git stash list`

You can see the stash entry is still there so you need to manually delete it by `git stash drop 1`.

`git stash list`: Now that stash entry is being deleted.









































