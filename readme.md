#Topics to cover#
Single developer workflow for easy getting started.

##GIT (really simple explained)##
* git is a local version control software which can also push/pull changes to a remote repository
* commit is equivalent to a checkpoint 
* branch is a separate line of code.

##Git basic workflow##

* single branch
* branch per feature
* branch per release

##Basic Commands##

* ``` git init ```
* Only first time configuration 
* ``` git config --global user.name "John Doe" ```
* ``` git config --global user.email johndoe@example.com ```
* ``` git status ``` 
* ``` git add . ```
* ``` git commit -m "My custom message" ```
* ``` git log ```

##Reset,Undo, etc commits && changes
* ``` git checkout . ``` (undo all non commited changes, you may also do it for specific files)
* ``` git reset --soft HEAD~1 ``` (undo last commit while keeping files)
* ``` git reset --hard ``` (Resets to a last commit deleting all files and changes. Its considered dangerous because it cannot be undone).
* ``` git reset --hard HEAD~1 ``` (Resets to an specific commit leaving a clean directory. In this case to the last commit. Number 1 can be changed for the desire commit rollback number)

##Revert
Removes commits and creates a new one without deleting history
git revert --no-commit 0766c053..HEAD
git commit

##Amend Commits
You may need to fix a commit in the case where you forgot to include a file or a change you may do this with the ammend argument:

* ``` git add . ```
* ``` git commit --amend ``` (this will promp you for a commit message)
* ``` git commit --amend -m "Just added a little change" ```



##Tags
They annotate (tag) specific points in history such a releases or any other important checkpoint. Its useful when specifying releases. Also github creates a link directly to releases as zip so other users can download the repo as a zip file.

* ``` git tag v1.0.0 ``` (simple tag)
* ``` git tag -a v1.0.0 -m "release v1.0.0" ``` (message must be descritive as it will show up in github pages"
* ``` git tag ``` (shows existing tags)
* ``` git tag v1.0.0 ``` (will show the commit of the current tag)
* ``` git tag -D v1.0.0 ``` (will remove the tag)
* ``` git push origin :refs/tags/v1.0.0 ``` (will remove the tag remotely)

Tags are not pushed by default you have to do it manually

* ``` git push origin --tags ``` (pushes all tags)
* ``` git push origin v1.0.0 ``` (pushes only the specified tag)
 
##branching##
* ``` git branch ```
* ``` git branch myBranchName ```
* ``` git checkout myBranchName ```
* ``` git merge nameOfBranch ```

###Remove remote branches###
* ``` git push origin --delete <branchName> ```

##Remote repositories##
* ``` git remote add origin url ```
* ``` git push -u origin branchName ```
* ``` git remote -v ``` (shows current remote repositories) 
* ``` git remote set-url origin https://github.com/username/repo-name.git ``` (the url is the new repo)
###Merge remote changes###
There are different ways of doing this. The following git command wil merge remote changes but its most likely that you want to review changes first before merging, other commands are avaliable for this.

* ``` git pull `` Will download all changes overwriting non conflicting files
* ``` git pull --rebase master ``` Will download an specific branch (master in this case) and will prompt when conflicts appear. 
* ``` git rebase --continue ``` one you have deal with the conflicts you can mark the file as fixed with ``` git add filename.ext `` and after that you execute rebase --continue to move on.
* ``` git rebase --skip ``` as the arguments says it skips the merge.
* ``` git rebase --abort ``` will leave the original branch as it is.



##update .gitignore
* ``` git rm -r --cached . ```
* ``` git add . ```
* ``` git commit -m "gitignore updated" ```

