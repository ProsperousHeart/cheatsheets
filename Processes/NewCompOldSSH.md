In my day job, every few years we are forced to switch computers. And this can really put a kink in your work as a programmer. For example - having all of your work be synched but being unable to connect to Github.

That's why I wanted to provide this information. I spent a whole lot of time trying to figure it out and it was just a few simple commands and GitHub integration.

# What You'll Need

I already had SSh keys set up from before, but didn't realize it.

# The Process

When trying to re-setup my machine for coding, I wanted a fresh start on some of my projects. So I deleted and then re-copied from GitHub. But when I checked the branches with `git branch` I only saw **master**, and when I ran `git branch -r` to see the remove branches, there were more!

I tried `git fetch` and `git fetch --all` to no avail. It would not pull down the branches. There were many issues I ran into, so I'm going to share how I was able to resolve.

## Adding Upstream

This is for each project.