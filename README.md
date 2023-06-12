# Gitlab-quick-notes
Small and easy cheatsheet for gitlab with only the commands you are going to actually use in your everyday workday.
The point is not to show you everything you can do in Gitlab but just what you need to start working with it.


## Squash commits:
```git reset --soft HEAD~n``` to reset the last n commits while keeping the changes in the working directory.
```git commit -m "comment wip"``` to create a new commit with all the changes.
```git push --force``` to forcefully update the remote branch.

## Fix branch while in review:
If you need to update the last commit while someone is reviewing the branch, use ```git commit --fixup "hash of the commit you want to update"``` to create a fixup commit.
To incorporate the fixup commit into the original commit, use ```git rebase --autosquash --interactive "hash of the commit before the first commit of this branch"```.
Finish by using ```git push --force``` to update the remote branch.

## Rebase a branch:
First, use ```git fetch``` to retrieve the latest changes from the remote repository.
Then, use ```git rebase origin/develop``` to rebase your branch on top of the updated origin/develop branch.
Finally, use ```git push --force``` to update the remote branch with the rebased changes.

## Stop tracking changes in file:
Exclude a file or folder from version control ```git update-index --skip-worktree <path-name>```

## Stash
To save local changes to a branch, use ```git stash save "message explaining what you were doing"```
To apply the latest stash, use ```git stash apply``` or ```git stash pop``` to apply and remove the stash.
To remove a specific stash, use ```git stash drop stash@{n}```.

## Reset local changes in a file
```git checkout thefilename.py``` to discard the local changes made to a specific file.

## To change the commit message of the last commit
```git commit --amend -m "new message"```

## Add a file to the last commit that hasn't been pushed yet
```git commit --amend <hash_of_commit>``` to add a file to the last commit.
  
## Move a local commit from one branch to another and return the initial branch to its state before the commit
```git cherry-pick <commit-hash>``` to move a commit to another branch.
```git reset --hard <commit-hash>``` to go back to the initial branch state before the commit.
If the commit created new files, use ```git clean -df``` to remove them.

## Remove untracked files and directories
```git clean -df``` to remove untracked files and directories.

## Revert some changes after other people have pulled those changes:
Use ```git revert <commit-hash>``` to create a new commit that undoes the changes made in a previous commit.

## Cherry-pick a commit
```git cherry-pick <commit-hash>``` to apply a specific commit from another branch to the current branch.

## Add a new SSH key to GitLab
Generate a new SSH key using ```ssh-keygen -t ed25519 -C "your_email@example.com"```
Retrieve the generated SSH key by running ```cat ~/.ssh/id_rsa.pub```
Add the SSH key to your GitLab profile by pasting it there.

You can download and install Git Bash, which provides a Git command-line interface for Windows users.
Visit the Git for Windows website to download the installer.
These are the explanations of the commands you provided. Remember to refer to official documentation or additional resources for more in-depth explanations and examples.
