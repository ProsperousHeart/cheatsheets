When working with **git** there are some best practices.
- always have a branch for a specific need (bug, feature, etc)
- when done, delete branch on server **and** locally (you can always recreate)

# Steps For Working With Git
1. [Create branch](https://github.com/ProsperousHeart/cheatsheets/blob/master/Tools/git.md#how-do-i--create-a-new-branch) from main
2. Perform your work
3. Add changes to git staging
4. Commit changes
5. Push to remote branch (not origin)
6. Request pull on GitHub to merge into __master__
7. Checkout your **_master_** branch
8. In git, run `git pull` and fix any merge issues. (Which there shouldn't be. If there are, fix and then do a `git push REMOTENAME master`)
9. When done with branch, run:  `git checkout master`
10`. Follow the steps to [delete your branch](https://github.com/ProsperousHeart/cheatsheets/blob/master/Tools/git.md#how-do-i-delete-my-branch).
