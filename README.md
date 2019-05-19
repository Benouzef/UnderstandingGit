# UnderstandingGit
Understanding Git commands

Objective is to let people (including myself :)) understand clearly Git commands when they have another background (for example antiques such as Visual Source Safe or TFS - TFS not being antique btw)


## Git Reset (with the help of https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified)
You can go back and forth in History and see files locally changed in your working directory using :
```
git reset --hard 'something'
```
1. Make sure you have a clean local directory with no changes to stage or commit (use git status)
2. If you're up to date with your remote branch (master) with a git pull, you should have a clean work tree

### Making sure everything is clean before playing around
- Type 'git pull' and then 'git status' 
You should have something looking like this
```
PS <Your working directory>\Code\UnderstandingGit> git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

### Type git reset --hard HEAD
This should leave you at the place you were :)
No changes and you have not jumped back in time yet.
```
PS <Your working directory>\Code\UnderstandingGit> git reset --hard HEAD
HEAD is now at 7c99fb9 Fourth commit - content in third file has changed
PS <Your working directory>\Code\UnderstandingGit> git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

### Type git reset --hard a0705a5a385b58f79360221d6fe2953928deb23f
```
PS <Your working directory>\Code\UnderstandingGit> git reset --hard a0705a5a385b58f79360221d6fe2953928deb23f
HEAD is now at a0705a5 Initial Commit
PS <Your working directory>\Code\UnderstandingGit> git reset --hard HEAD
HEAD is now at a0705a5 Initial Commit
PS <Your working directory>\Code\UnderstandingGit> git status
On branch master
Your branch is behind 'origin/master' by 3 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
```
Now you're back in time and your local folder has been updated to reflect the situation at "Initial Commit"
When you type "git status", the current branch is behind by a few commits.

### Jumping back to present
You just have to type git pull to get back to present

```
PS <Your working directory>\Code\UnderstandingGit> git pull
Updating a0705a5..7c99fb9
Fast-forward
 GoingBackAndForthInTime/SecondFile  | 1 +
 GoingBackAndForthInTime/ThirdCommit | 4 ++++
 2 files changed, 5 insertions(+)
 create mode 100644 GoingBackAndForthInTime/SecondFile
 create mode 100644 GoingBackAndForthInTime/ThirdCommit
 ```

### What if I want to change the past?
Beware that typing git reset --hard <commit hash> changes the files on your local directory
You can make changes locally and then you will have to either discard changes either try to change the past...
By default "git pull" will fail nicely if you don't decide beforehand.

### Git Pull (easy)
### Git Status (easy)
### Discard changes : from VSCode


Do not forget https://help.github.com/en/articles/basic-writing-and-formatting-syntax for styling
