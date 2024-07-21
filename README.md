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