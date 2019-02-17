When working with **git** there are some best practices.
- always have a branch for a specific need (bug, feature, etc)
- when done, delete branch on server **and** locally (you can always recreate)

# Steps For Working With Git
1. [Create branch](https://github.com/ProsperousHeart/cheatsheets/blob/master/Tools/git.md#how-do-i--create-a-new-branch) from main
   - if done locally, you will need to:
     - create branch locally
     - [push to GitHub](https://github.com/ProsperousHeart/cheatsheets/blob/master/Tools/git.md#how-do-i-push-my-new-branch-to-github)
   - if done on GitHub, you will need to:
     - create branch on GitHub
     - on local git, ensure you're working on **master** branch
     - [pull from remote](https://github.com/ProsperousHeart/cheatsheets/blob/master/Tools/git.md#how-do-i-get-my-branch-on-github-to-my-local-branch)
2. Perform your work
3. Add changes to git [staging](https://github.com/ProsperousHeart/cheatsheets/blob/master/Tools/git.md#staging)
4. [Commit](https://github.com/ProsperousHeart/cheatsheets/blob/master/Tools/git.md#commit) changes
5. [Push to remote](https://github.com/ProsperousHeart/cheatsheets/blob/master/Tools/git.md#how-do-i-get-my-branch-from-local-to-remote-git) branch (not origin)
6. Request pull on GitHub to merge into __master__
7. Checkout your **_master_** branch
8. In git, run `git pull` and fix any merge issues. (Which there shouldn't be. If there are, fix and then do a `git push REMOTENAME master`)
9. When done with branch, run:  `git checkout master`
10`. Follow the steps to [delete your branch](https://github.com/ProsperousHeart/cheatsheets/blob/master/Tools/git.md#how-do-i-delete-my-branch).
