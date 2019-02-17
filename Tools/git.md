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

## How Do I Push My New Branch To GitHub?

Run this command:  `git push -u REMOTENAME BRANCHNAME`

If it's your repo, default REMOTENAME is origin.

PS - If you do this, then the subsequent pushes don't need the `-u` anymore:
```
git push REMOTENAME BRANCHNAME
```

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

## How Do I Delete My Branch?

[This](https://stackoverflow.com/questions/2003505/how-do-i-delete-a-git-branch-both-locally-and-remotely?rq=1) was an excellent explanation for both local and remote.

### Locally

Just run:  `git branch -d BRANCHNAME`

### Remote

Just run:  `git push --delete REMOTENAME BRANCHNAME`

OR even:  `git push <remote_name> :<branch_name>`

# Commit

After you've added files to your staging, you now need to commit the changes.

## How Do I Commit My Code?

Run this command:  `git commit`

If set up properly, it will open your code editor for you to write a message.

Otherwise, run:  `git commit -m "Some message here"`

## How Do I Undo My Last Commit?

If you have not yet pushed to your server, you can follow these commands as per [this StackOverflow](https://stackoverflow.com/a/927386/10474024):

1. `git reset HEAD~`

You can now make changes, stash, etc.

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

# How To Check Differences

## For Local Files

When you use `git status` you are able to see which files are changed in the working directory, but not the actual changes. That's where `git diff` comes in. It will show you **how** or what changes were made.

This will show all current changes in working directory that have not yet been staged.

## What About Local Staged Files?

Just run: `git diff --staged`

## And If They're Committed?

Run `git log` to see overview of recent commits. You can add the **-p** flag to get the detailed "patches" (changes) of each commit.

`git log -p`

## Check For Difference Between Remote And Local

Normally if you run `git fetch` you can get the remote's data without integration into your current code. You can then run `git merge` ...

Or you can simply run `git fetch` which does both for you.

Please see a more detailed explanation [here](https://git-scm.com/docs/git-stash).

## How To Compare Branches

Just run: `git diff BRANCH1..BRANCH2`

## How To Compare Different Versions In A Branch

Just run:  `git diff VERSION1..VERSION2`

You can get this info from running: `git log`

# How To Exit Diff Or Log

Sometimes you get a long list of changes when running `git diff` or `git log`.

So how do you quit? Just press: `q`
