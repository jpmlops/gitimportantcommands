# Some notes on rebasing

> Sample: git pull --rebase

In Git, there are two main ways to integrate changes from one branch into another: 
1. the merge and 
2. the rebase.

In this section you’ll learn what rebasing is, how to do it, why it’s a pretty amazing tool, and in what cases you won’t want to use it.


>> important tools for merging - <MELD>

## Extract a file from another branch


> Sample: git show some-branch:some-file.js

Sometimes it is nice to take a pick at an entire file on a different branch, without switching to this branch.

You can do so via <git show some-branch-name:some-file-name.js>, which would show the file in your terminal.

You can also redirect the output to a temporary file, so you can perhaps open it up in a side by side view in your editor of choice.

> git show some-branch-name:some-file-name.js > deleteme.js

> Note: If all you want to see is a diff between two files, you can simple run:
git diff some-branch some-filename.js

![alt text](image.png)

## Git Standard vs Git Interactive Rebase
Git rebase is in interactive mode when the rebase command accepts an — I argument. This stands for Interactive. Without any arguments, the command runs in Standard mode. In order to achieve standard rebasing, we follow the following command:

`git rebase master branch_x`
> where branch_x is the branch we want to rebase

The above command is equivalent to the following command and will automatically take the commits in your current working branch and apply them to the head of the branch which will be mentioned:

> `git rebase master`

Whereas, in Interactive rebasing, you can alter individual commits as they are moved to the new branch. It offers you complete control over the branch’s commit history. In order to achieve interactive rebasing, we follow the following command:

> git checkout branch_x

> git rebase -i master

This command lists all the commits which are about to be moved and asks for rebasing all commits individually and then rebasing them according to the choices you entered. This gives you complete control over what your project history looks like.

## Git Rebase Commands
The following are the most used Git rebase commands:

1. git rebase master: The command “git rebase master” can be used to make all modifications found in your master branch part of your current branch.
2. git rebase –continue: When we are rebasing the branches we will face some conflicts and issues then we need to resolve the issue. After resolving the issue we again continue the rebasing processes for that we use “git rebase –continue”.
3. git rebase –abort: “Git rebase –abort” command cancels a rebase that is currently underway and restores the branch to its initial state.
4. git rebase –skip: When rebasing the branches we might face some unresolved conflicts to skip the particular encounters we will use  “git rebase –skip”. Skipping the commit is not good practice it will damage your codebase.
5. git rebase -I HEAD~3: With the help of this command, you can interactively rebase the most recent three commits onto the active branch. You can choose which commits to rebase, alter commit messages, and squash or divide commits in the interactive editor that is opened.

