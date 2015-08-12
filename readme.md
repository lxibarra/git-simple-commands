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

#Basic Commands#

* git init
* Only first time configuration 
*  * git config --global user.name "John Doe"
*  * git config --global user.email johndoe@example.com
* git status
* git add .
* git commit -m "My custom message"
* git log

##Reset commits
* git reset --soft HEAD~1 (undo last commit) 
 
##branching##
* git branch
* git branch myBranchName
* git checkout myBranchName
* git merge nameOfBranch

##Remote repositories##
* git remote add origin url
* git push -u origin branchName

##update .gitignore
* git rm -r --cached .
* git add .
* git commit -m "gitignore updated"

