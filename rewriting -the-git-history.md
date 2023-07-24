

### Rewriting Git History

How to edit previous commits if needed?


- Amending commits: If i want to add more files to the last commit then you can amend the commit by following these
steps:
Step1: First stage those files which you want to add
git add file1.md file2.md

Step2: Run ```git commit --amend --no-edit```
--no edit wont change the commit message

Now, you can see that commit history is the same but the commit hash is changed because we have rewriting history
run git status to ensure if both the files are being added or not.

## Working with interactive REBASE

-  Rewording commit messages: If you did some typo mistakes to your commit or you want to change the commit message
then for this we will use these steps(we cant use git ammend because amend works only for the last commit back from HEAD)

We will use git rebase:
``` git rebase -i HEAD~2 ```

will tell git that we want to amend the last two commits back from HEAD.

Default terminal text editor opens
then change the pick to reword infront of the commit which is mispelled
Save and close the file.

Another text editor opens:
now edit the words you want in your commit message.
Save and close the file.

NOw git has succesffully rebased and updated commit message

check by
```git log --oneline```
but different commit ID because git did rewrite the commit history.


- Deleting commits: As the name suggests if you want to delete any commit from your history.
run
```git rebase -i HEAD~3 ```

git will again pop up default text editor, it will show the last 3 commits back from HEAD where you want to change
change pick to drop
Save and close the file

now you see that your commit is being deleted.
check ```git log --oneline```



- Reordering commits: If you want to reorder the commits like you want the second commit to be the first then enter
```git rebase -i HEAD~2```
again the text editor opens
which shows the last 2 commits back from head simply cut the second commit and put it before the first commit.
Save and exit the file.GIt automatically rewrites the history.


```git log --oneline``` : to check your changes.

- Squashing commits: WHen you want to combine two or more commits because maybe they all are related to the same
feature or bug and you dont want them to be a separate commit, so you squash all of them into a one single commit.

Using interactive rebase

```git rebase -i HEAD~3```

now git provides two options for combining fixup and squash,
we will use fixup: it melds the commits into a previous commit and discard their commit messages
change pick to fixup
save and close the file
hit enter.
see the output:
```git log --oneline```


- Splitting commits: YOu decide that some commits are better off when they are commited differently.
FOr ex: if you added two commits are not related to each other but they are commited together then split them using:

```git rebase -i HEAD~3```

options edit 
change pick to edit where u want to split.
save and exit

git status:
u will see interactive rebase in progress,
now u will unstage the commit and the unstage all the files in it.

```git reset HEAD^``` : unstage all those files.

now git status:
u will see those files are now unstages. Red highlights.
now u have to stage and commit them differently.
by using:
```git add filename1 ```
```git commit -m "commit message 1"```

```git add filename2```
```git commit -m "commit message 2"```

now we have commited two files instead of oonly one.
now get back to the rebase operation and finish them by entering:
```git rebase --continue```

now succefully rebased and updated the history.
check: ```git log --oneline ```
