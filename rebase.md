# Some notes on rebasing

> Sample: git pull -—rebase

>> important tools for merging - <MELD>

## Extract a file from another branch


> Sample: git show some-branch:some-file.js

Sometimes it is nice to take a pick at an entire file on a different branch, without switching to this branch.

You can do so via <git show some-branch-name:some-file-name.js>, which would show the file in your terminal.

You can also redirect the output to a temporary file, so you can perhaps open it up in a side by side view in your editor of choice.

> git show some-branch-name:some-file-name.js > deleteme.js

> Note: If all you want to see is a diff between two files, you can simple run:
git diff some-branch some-filename.js