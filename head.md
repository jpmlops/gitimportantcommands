# What is HEAD in Git?

HEAD is a reference to the most recent commit in the current branch. 

When you create a new commit, Git automatically updates HEAD to point to the new commit. You can use the `git log --oneline` command to view the commit history of the current branch, and the commit at the top of the list is the one that HEAD is currently pointing to.
![alt text](image.png)

So, when we are talking about resetting to HEAD, it means resetting the current branch to the most recent commit. Apart from the HEAD, you can also reset to other commits with the `git reset --hard <commit-hash>` command.


> You can even use some numbers with HEAD itself to go back to a particular commit. For instance, HEAD{0} means the HEAD itself, HEAD{1} means the commit before the HEAD, HEAD{2} means two commits before the HEAD, and so on.

## How to Reset to HEAD in Git

The `git reset --hard HEAD` command would discard all uncommitted changes even if you’ve added them to the staging area.

## How to Reset to a Particular Commit with the Git Reset Command

You can now run `git reset --hard HEAD@{n}` to go back to a particular commit. 
> Be aware that the `git reset –hard HEAD` or `git reset –hard HEAD@{n}` command would remove your uncommitted changes, even if you staged them.

>What Flags Do We Use With the Git Reset Command?
 `git reset --soft HEAD~1`
 `git reset --mixed HEAD~1`
 `git reset --hard HEAD~1`


# Example

 ## What Is git reset --soft HEAD~1?

 we already covered these points - 
 
1. git reset changes where the current branch is pointing to (HEAD).

2. HEAD is a pointer or a reference to the last commit in the current branch. HEAD~3 would mean behind three commits from HEAD.

Let’s say we have the following commit tree:

`- c1 - c2 - c3`

Assuming HEAD is pointing to C3 and the index (stage) matches to C3.

When we execute git reset --soft HEAD~1, now HEAD points to C2, but the index (stage) will have changes from C3 and git status will show them as staged. Now if we run git commit at this point, we’ll get a new commit with the same changes as C3.

## What Is git reset --mixed HEAD~1?

`- c1 - c2 - c3`

Assume HEAD is pointing to C3 and the index matches C3.

When we execute git reset --mixed HEAD~1 then HEAD points to C2, also the index gets modified to match C2 (all the changes that were committed won’t be seen on stage but they are there in the working directory).

> Note that --mixed is the default option.

### What Is git reset <file>?
git reset: It removes from the index/staging area, but it leaves the file unchanged in the working directory. Basically, this command unstages a file without overwriting any changes.

## What Is git reset --hard HEAD~1

Assuming HEAD is pointing to C3 and the index matches C3.

`- C1 - C2 - C3`

--hard flag modifies HEAD, index and working directory. If we’re at C3 and run git reset --hard HEAD~1, then the changes committed to C3, uncommitted changes that we have in the staging area and all the changes in the working directory will be removed and the working directory will match C2 commit.

> HEAD, index and working directory all will have the same version of files.

## How To Undo a Remote Commit

There are times you want to undo a commit you have pushed to a remote repository. You can use git revert to undo it locally and push this change to the remote branch.

First, get the commit hash using git reflog.

> git reflog
Then revert it. Let’s assume my commit hash is 1257b6910, I’ll do the following:

> git revert 9157b6910
Finally, push this change to the remote branch.

# You Used git reset --hard and Need to Get That Code Back

Let's say you destroyed a commit using --hard, but then decided you need it back. 

Don’t worry! There’s still a way to get it back.

Type `git reflog` and you’ll see a list of (partial) commit SHA’s (basically commit hashes). This command shows a log of changes to the local repository’s HEAD. Now find the commit you destroyed and execute the below command.

> `git checkout -b NewBranchName CommitHashYouDestroyed`

Now you’ve restored that commit. Commits don’t actually get destroyed in Git for `90 days` or so, so you can usually go back and rescue one you didn’t mean to get rid of.  