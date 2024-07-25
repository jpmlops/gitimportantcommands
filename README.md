# Git Tips For Everyday Use

Most practical tips that I've learned along the way.

## Parameters for better logging

> Simple commnand: git log --online --graph

Important Parameters:

--author=""
--name-only
--oneline
--graph
--reverse
--after
--before

> Note: Git has a lot more command line parameters, Just run to <man git-log> to see

Example:

git log --author="Ales kras" --after="1 week ago"

## Log actual changes in a file

> Command: git log -p filename

This lets you view not only the commit messages, author and date, but actual changes that took place in each commit.

> git blame filename => to find the person responsible for every line of the file

Note: git reset --hard [commit hash code] => to go a perticular commit

## Three stages in git, and how to move between them

> Sample | git reset --hard HEAD and git status -s

As you may already know by now, a file in git can be in 3 stages:

1. Not staged for commit
2. Staged for commit
3. Committed

## Only “add” some changes from a file

> Sample git add -p

Somebody at git must really like the -p flag, because it always comes with some handy functionality.

In case of git add, it allows you to interactive select exactly what you want to be committed. That way you can logically organize your commits in an easy to read manner.

## Create aliases for your most frequently used commands

Git comes with built in aliases, for example you can run the following command once:

<git config --global alias.l "log --oneline --graph">

Which would create a new git alias named l, that would allow you to run:
<git l instead of git log --oneline --graph>.

Note that you can also append other parameters after the alias (i.e. git l --author="Alex").

Another alternative, is good old Bash alias.

For example, I have the following entry in my .bashrc file.

<alias gil=”git log --oneline --graph”>, allowing me to use gil instead of the long command,which is even 2 character shorter than having to type git l :).

## Quickly find a commit that broke your feature

> Sample: git bisect

- git bisect uses divide and conquer algorithm to find a broken commit among a large number of commits.

> git merge branchname => merge in current branch
> git diff [branch-name]..[another-branch-name]
> git reset
> git revert


> After megring `hotfix` to `master` - master is fast-forwarded to hotfix.

After your super-important fix is deployed, you’re ready to switch back to the work you were doing before you were interrupted. However, first you’ll delete the hotfix branch, because you no longer need it — the master branch points at the same place. You can delete it with the -d option to git branch:

```bash

$ git branch -d hotfix
Deleted branch hotfix (3a0874c).

```