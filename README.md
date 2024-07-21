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

> git blame filename    => to find the person responsible for every line of the file


Note: git reset --hard [commit hash code]  => to go a perticular commit


## Three stages in git, and how to move between them

> Sample git reset --hard HEAD and git status -s

As you may already know by now, a file in git can be in 3 stages:
1. Not staged for commit
2. Staged for commit
3. Committed