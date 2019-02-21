# Git

Whether through a training or via hands on experience, this section will provide clear shortcuts to using git efficiently.

# Clone

## How Do I Clone A Repo From GitHub?

1. Create a repo
2. Get the HTTPS URL
3. Using git, navigate to the folder you wish to clone it into
4. Run this command where URL is the URL from GitHub:  `git clone URL`

## Not All Of My Branches Were Cloned!

[This article](https://stackoverflow.com/a/72156/10474024) explains it beautifully, but basically ...

1. After you clone your repo, change into the directory.
2. If you run `git branch` you may be missing some. To see all run: `git branch -a`
3. To peek at upstream branch, run `git checkout origin/BRANCH` ... But if you want to work in it run:  `git checkout BRANCHNAME`

This will now be on your local machine.

# Branch

This section will be used to cover working with branches

## How Do I:  Create A New Branch?

1. Using your local git, navigate to the folder you need to be in. (Assuming you have already set up your remote repo.)
2. Run the following command:  `git branch BRANCHNAME` (where BRANCHNAME is whatever branch you want to call it)
3. Run the following command: `git checkout BRANCHNAME`

Or if you know you'll be going straight into this new branch?
Then all you need to do for 2 & 3 is run: `git branch -b BRANCHNAME`

You will now be inside your new branch! Need to get back?
`git checkout master`

PS - there are other options you can do with this. Be sure to checkout documentation.

## How Do I Know What Branches I Currently Have?

Just run: `git branch`

## How Do I Move Between Branches?

Just run: `git checkout BRANCHNAME`

## How Do I Push My New Branch To GitHub?

Run this command:  `git push -u REMOTENAME BRANCHNAME`

If it's your repo, default REMOTENAME is origin.

PS - If you do this, then the subsequent pushes don't need the `-u` anymore:
```
git push REMOTENAME BRANCHNAME
```

## How Do I Create An Upstream To My Branch On GitHub?

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

Or you can just [follow the above suggestion](https://github.com/ProsperousHeart/cheatsheets/blob/master/Tools/git.md#how-do-i-push-my-new-branch-to-github).

## How Do I Get My Branch From Local To Remote Git?

If you have your upstream setup, then just run:  `git push REMOTENAME BRANCHNAME`

Where __REMOTENAME__ is the name given to your remote location (default is _origin_)...
And **BRANCHNAME** is the name of your branch.

## How Do I Get My Branch On GitHub To My Local Branch?

When in the working branch you wish to update, run: `git pull`

This basically is a `git fetch` and `git merge` in one command.

## How Do I Delete My Branch?

[This](https://stackoverflow.com/questions/2003505/how-do-i-delete-a-git-branch-both-locally-and-remotely?rq=1) was an excellent explanation for both local and remote.

### Locally

Just run:  `git branch -d BRANCHNAME`

### Remote

Just run:  `git push --delete REMOTENAME BRANCHNAME`

OR even:  `git push <remote_name> :<branch_name>`

## How Do I Get My Branch On GitHub To My Local Branch?

When in the working branch you wish to update, run: `git pull`

This basically is a `git fetch` and `git merge` in one command.

# Staging

This is where you add changes to your staging area before committing your changes. This simply means git knows about the change but it is not a permanent change in your repo.

## How Do I Add Files/Folders To Staging?

To add a single file: `git add FILENAME`

To add a folder:  `git add FOLDERNAME`

To add all changes: `git add .`

## How Do I Remove Them From Staging?

Just ru the following to remove all changes:  `git reset HEAD~`

# Commit

After you've added files to your staging, you now need to commit the changes.

Be sure to [check out this styleguide](http://udacity.github.io/git-styleguide/) from Udacity.

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

## How Can I Get Information About The Remote?

[This](https://stackoverflow.com/a/4089452/10474024) did a great job of explaining.

Assuming referential integrity broken (or you just want the URL): `git config --get remote.origin.url`

Assuming referential integrity is in tact or you require full output: `git remote show origin`

When using `git clone` the default name for source is **origin** and using the following command will display info about this remote name:  `git remote show`

This **_show_** command will let you know the names of all the remotes you have for the current branch.

The following will show all for your specified branch (like origin):  `git remote show BRANCHNAME`

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

# How To Ignore Files Or Folders

Got this from [here](https://medium.com/@haydar_ai/learning-how-to-git-ignoring-files-and-folders-using-gitignore-177556afdbe3).

To ignore a file, set of files or folder you will need to add them to the `.gitignore` file.

This needs to be in the **root** of your project folder.

To specify a particular file: `FILENAME.extension`
To specify all types of files:  `*.extension`
To specify a folder & it's contents:  `FOLDERNAME\`

When you add those lines to the file, they will no longer show up when running: `git status`

However, if they were already part of the project?

It doesn't remove them from there and they will not be ignored.
