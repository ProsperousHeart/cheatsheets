# Git

Whether through a training or via hands on experience, this section will provide clear shortcuts to using git efficiently.

# Branch

This section will be used to cover working with branches

## How Do I:  Create A New Branch?

1. Using your local git, navigate to the folder you need to be in. (Assuming you have already set up your remote repo.)
2. Run the following command:  `git branch BRANCHNAME` (where BRANCHNAME is whatever branch you want to call it)
3. Run the following command: `git checkout BRANCHNAME`

You will now be inside your new branch! Need to get back?
`git checkout master`

PS - there are other options you can do with this. Be sure to checkout documentation.

## How Do I:  Create An Upstream To My Branch On GitHub?

If you try to run `git pull` from a branch that does not have an upstream, you will get an error similar to this:

```
Kat (thank-you) cheatsheets $ git pull
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> thank-you
```

In this instance, it would look like:  `git branch --set-upstream-to=origin/thank-you thank-you`

What this does is that it allows you to pull down changes made directly to your branch on GitHub.

## How Do I Get My Branch From Local To Remote Git?

If you have your upstream setup, then just run:  `git push REMOTENAME BRANCHNAME`

Where __REMOTENAME__ is the name given to your remote location (default is _origin_)...
And **BRANCHNAME** is the name of your branch.

# Remote

This refers to your remote repo - like GitHub.

# Stash

`git stash` allows you to put whatever you're doing on hold. This is really effective for when let's say your boss wants you to drop what you're doing to fix a bug. You stash your current state of a file, change branch, do your work and all the updates, then get back your state!

1. Run this command in git:  `git stash`

Congrats! It's stashed.

## How To See What's Stashed?

Run this git command:  `git stash list`

## How Do I Get The Prior State?

Run this command:  `git stash pop`

Please see a more detailed explanation [here](https://git-scm.com/docs/git-stash).