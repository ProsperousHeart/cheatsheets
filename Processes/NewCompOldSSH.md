<a href='https://www.learntocodeonline.com/'>![Learn To Code Online By Clicking Here](../Images/learn-to-code-online.png?raw=true "Learn To Code Online")</a>

In my day job, every few years we are forced to switch computers. And this can really put a kink in your work as a programmer. For example - having all of your work be synched but being unable to connect to Github.

That's why I wanted to provide this information. I spent a whole lot of time trying to figure it out and it was just a few simple commands and GitHub integration.

Please note that I am using **Git Bash for Windows** so it may be a little different for you.

# New Commands & Explanations

When you run `git fetch --all` you will update all local copies of remote branches. Also, `git pull --all` will update your local tracking branches, but depending on your local commits and how the 'merge' configure option is set it might create a merge commit, fast-forward or fail. ([Source](https://stackoverflow.com/a/10312587/10474024))

When you want to fetch the branches and respective commits from your upstream repo, you will run `git fetch upstream`. ([Source](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/syncing-a-fork))

In the rest of this doc, you will find some of the issues, errors, and resolutions I was running into.

# What You'll Need

I already had SSh keys set up from before, but didn't realize it.

# The Process

When trying to re-setup my machine for coding, I wanted a fresh start on some of my projects. So I deleted and then re-copied from GitHub. But when I checked the branches with `git branch` I only saw **master**, and when I ran `git branch -r` to see the remove branches, there were more!

I tried `git fetch` and `git fetch --all` to no avail. It would not pull down the branches. There were many issues I ran into, so I'm going to share how I was able to resolve.

## Adding Upstream

If you try to run `git fetch upstream` and get something like this:

    fatal: 'upstream' does not appear to be a git repository
    fatal: Could not read from remote repository.
    
    Please make sure you have the correct access rights and the repository exists.

... then you need to set up your upstream. This is for each project.

You will need to run:  `git remote add upstream git@github.com:USERNAME/REPOSITORY.git`

This will add your github repo as the upstream - which is great! You should now be able to fetch the branchs and their respective commits from the upstream repo with: `git fetch upstream`

... unless you get this error message:

    The authenticity of host 'github.com (192.30.255.112)' can't be established.
    RSA key fingerprint is SOME_KEY_FINGERPRINT_NOT_SURE_IF_SAME_FOR_ALL.
    Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
    Warning: Permanently added 'github.com,192.30.255.112' (RSA) to the list of known hosts.
    git@github.com: Permission denied (publickey).
    fatal: Could not read from remote repository.
    
    Please make sure you have the correct access rights and the repository exists.

Or if you tried to run `git fetch --all` and got this message:

    Fetching origin
    Fetching upstream
    git@github.com: Permission denied (publickey).
    fatal: Could not read from remote repository.
    
    Please make sure you have the correct access rights and the repository exists.
    error: Could not fetch upstream

Which brings us to the next step.

## Fixing publickey Permission Denied Error

While [this GitHub help article](https://help.github.com/en/github/authenticating-to-github/error-permission-denied-publickey) was definitely helpful, it wasn't 100% what I needed for my situation. But mostly gave me what I needed.

When it tells you to run `ssh -vT git@github.com` to check if you are connecting to the right server, I got the **publickey** error. So I then went to the section [Make Sure You Have A Key That Is Being Used](https://help.github.com/en/github/authenticating-to-github/error-permission-denied-publickey#make-sure-you-have-a-key-that-is-being-used).

I started the agent:  `eval "$(ssh-agent -s)"`

When I tried to verify if I had a private key generated and loaded into SSH using `ssh-add -l` or even `ssh-add -l -E md5` I received the following error:

    The agent has no identities.

Great. So that means that keys used by ssh (stored in files such as ~/.ssh/id_rsa, ~/.ssh/id_dsa, etc.) are either missing, they are not known to ssh-agent (which is the authentication agent), or that their permissions are set incorrectly.  ([Source](https://stackoverflow.com/a/28444641/10474024))

Next stop was I **thought** to create a pair with `ssh-keygen -t rsa` but I received this message:

    Generating public/private rsa key pair.
    Enter file in which to save the key (/c/Users/kkeeton/.ssh/id_rsa):
    /c/Users/kkeeton/.ssh/id_rsa already exists.
    Overwrite (y/n)?

Egads! It's already there? No, I don't want to overwrite - I don't know what's there! So on to the next step ... Checking to see what is in there by running:  `ls -al ~/.ssh`

Sure enough I see something similar to this:

    total 49
    drwxr-xr-x 1 kkeeton 1049089    0 Nov  7 09:16 ./
    drwxr-xr-x 1 kkeeton 1049089    0 Mar 25 16:22 ../
    -rw-r--r-- 1 kkeeton 1049089 3326 Feb  1  2019 git_rsa
    -rw-r--r-- 1 kkeeton 1049089  752 Feb  1  2019 git_rsa.pub
    -rw-r--r-- 1 kkeeton 1049089 1675 Jan  9  2018 id_rsa
    -rw-r--r-- 1 kkeeton 1049089  399 Jan  9  2018 id_rsa.pub
    -rw-r--r-- 1 kkeeton 1049089 2140 Mar 26 09:01 known_hosts

Seeing that it did in fact have the files I was looking for (`id_rsa` and `id_rsa.pub`) I then ran the following:

1. `eval $(ssh-agent -s)` (this was likely unnecessary since I had run it before but ran it anwyay to ensure the service was running)

2. `ssh-add ~/.ssh/id_rsa` which gave me the following response:

`Identity added: /c/Users/kkeeton/.ssh/id_rsa (/c/Users/kkeeton/.ssh/id_rsa)`

It was now time to add the SSH key into my GitHub.

## Adding New SSH Key To GitHub

I don't know how I had it set up on my old machine, since there were no SSH keys in my GitHub. Regardless, this was still the next step. For this, I just followed [this GitHub help page](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)

Here are the steps:

1. Copy the SSH to your clipboard:  `clip < ~/.ssh/id_rsa.pub`

2. In the upper-right corner of any page, click your profile photo, then click **Settings**.
![alt text](https://help.github.com/assets/images/help/settings/userbar-account-settings.png "Location Of Settings")

3. In the user settings sidebar, click **SSH and GPG keys**.
![alt text](https://help.github.com/assets/images/help/settings/settings-sidebar-ssh-keys.png "Settings Option")

4. Click **New SSH key** or **Add SSH key**.
![alt text](https://help.github.com/assets/images/help/settings/ssh-add-ssh-key.png "Button Location")

5. In the "Title" field, add a descriptive label for the new key.

6. Paste your key into the "Key" field.
![alt text](https://help.github.com/assets/images/help/settings/ssh-key-paste.png "Visual Of Key field")

7. Click **Add SSH key**.
![alt text](https://help.github.com/assets/images/help/settings/ssh-add-key.png "Button View")

8. If prompted, confirm your GitHub password.
![alt text](https://help.github.com/assets/images/help/settings/sudo_mode_popup.png "Confirmation View")

Once all of this was done, I had no more issues trying to run `git fetch --all` to ensure I had all of my branches.

# One Last Thing

There are now 2 ways this can go.

## Option 1 - Hunky Dory

I had another repo that I ran `git fetch origin` and `git fetch all` on with no issues, but the branches still not showing locally. All I had to do was run `git branch BRANCHNAME` (where BRANCHNAME was the branch on github) and it gave me a message like this:

    Switched to a new branch 'BRANCHNAME'
    Branch 'updates' set up to track remote branch 'BRANCHNAME' from 'origin'.

And it was smooth sailing from there!

## Option 2 - Not So Hunky Dory

As you can see in the above section, there were no issues. But that EXACT SAME PROCESS would not work in the original folder I was in. While I didn't have an issue running `git fetch --all` ... I still didn't see all of the branches locally! And the process above wouldn't work. I got a response like this:

    error: pathspec 'BRANCHNAME' did not match any file(s) known to git
    hint: 'BRANCHNAME' matched more than one remote tracking branch.
    hint: We found 2 remotes with a reference that matched. So we fell back
    hint: on trying to resolve the argument as a path, but failed there too!
    hint:
    hint: If you meant to check out a remote tracking branch on, e.g. 'origin',
    hint: you can do so by fully qualifying the name with the --track option:
    hint:
    hint:     git checkout --track origin/<name>
    hint:
    hint: If you'd like to always have checkouts of an ambiguous <name> prefer
    hint: one remote, e.g. the 'origin' remote, consider setting
    hint: checkout.defaultRemote=origin in your config.

Here are the steps to resolve.

**One Line Option**:  `git checkout -b BRANCHNAME origin/BRANCHNAME`

And the branch will then be added!

## Option 3 - GET IT ALL

I only found this after writing the document ... And it worked!

To get all branches and all their stuff at once, run these three commands:

    git branch -r | grep -v '\->' | while read remote; do git branch --track "${remote#origin/}" "$remote"; done
    git fetch --all
    git pull --all

# Additional Links

You may also be interested in these additional links for future reference:
- GitHub Help - [Connecting to GitHub with SSH](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)
- GitHub Help - [Error:  Permission Denied (publickey)](https://help.github.com/en/github/authenticating-to-github/error-permission-denied-publickey)
- StackOverflow - [How To Get Remote Branch As Local Branch](https://stackoverflow.com/a/10313379/10474024)
- StackOverflow - [Get All Branches From All Remotes](https://stackoverflow.com/a/10312587/10474024)