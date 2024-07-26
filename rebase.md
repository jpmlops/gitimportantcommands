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

