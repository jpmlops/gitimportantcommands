# Basic Branching and Merging

Let’s go through a simple example of branching and merging with a workflow that you might use in the real world. You’ll follow these steps:

- Do some work on a website.

- Create a branch for a new user story you’re working on.

- Do some work in that branch.

At this stage, you’ll receive a call that another issue is critical and you need a hotfix. You’ll do the following:

- Switch to your production branch.

- Create a branch to add the hotfix.

- After it’s tested, merge the hotfix branch, and push to production.

- Switch back to your original user story and continue working.

## Basic Branching

First, let’s say you’re working on your project and have a couple of commits already on the master branch.

You’ve decided that you’re going to work on issue #53 in whatever issue-tracking system your company uses. To create a new branch and switch to it at the same time, you can run the git checkout command with the `-b` switch:

> $ git checkout -b iss53 <br>
> Switched to a new branch "iss53"

This is shorthand for:

> $ git branch iss53 <br> git checkout iss53

> NOTE

- Before you do that, note that if your working directory or staging area has uncommitted changes that conflict with the branch you’re checking ouT
- Git won’t let you switch branches. It’s best to have a clean working state when you switch branches.
- There are ways to get around this (namely, stashing and commit amending)
