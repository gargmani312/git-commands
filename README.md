# BASIC GIT COMMANDS
```THERE IS LISTING OF BASIC GIT COMMAND WILL HELP YOU IN YOUR DAILY WORKS.```

# Git Log:
Description: To check git log(commits details etc all list will come). \
```git log```


# Git Status:
Description: To check git status like in how many files your changed. \
```git status```


# Git Pull:
```git pull origin master```


# Git Diff:
Description: To check git what you changed in file. \
```git diff file-name```


# Git Add:
Description: To add file for push the code. \
```git add file-name```


# Git Commit:
Description: To add detail what changes you done. \
```git commit -m "someting is added"```

# Git show:
Description: To show commit detail what changes you done. \
```git show <commit-hash/id>"```


# Git Push:
Description: To push the code in mentioned branch. \
```git push origin branch-name```


# Git Fetch:
Description: To fetch all branch name. \
```git fetch --all```


# Git branch checkout:
Description: To checkout in paticular branch. \
```git checkout origin branch-name```


# Git file checkout:
Description: To checkout in paticular file in same branch / remove changes in paticular file in same branch. \
```git checkout file-name```



# Git Make New Branch:
Description: To make new branch. \
```git checkout -b new-branch-name``` \
To push the all changes in new branch after this command run the git add command then you can push you code in new branch.


# Pull request / Merge your branch into base:
Description: Pull request is all about asks/tell to maintainer/admin for review your branch code and merge into the base branch. \
steps of creating pull request: \
1). Make a new branch. \
2). Commit and push the changes in inherited branch. \
3). Go to github in commit/branch you have pushed. \
4). Click the Compare & pull request button. \
5). Select base branch there you want merge your branch. \
6). Click Create pull request. \
7). You can add there Reviewers and Assignees.  \
Same you can Merge pull request by Click the Merge pull request button. \
*It is the way too merge your branch into base branch when you are self Reviewers/Assignees.


# Git Reset:
Description: git reset command is used to reset the changes. \
* To reset branch" \
```git reset --hard branch-name```  
* To Reset commit: \
```git reset --hard commit_id``` \
Example:
* Suppose you have 2 commit in git log A,B.
* Now you pushed two more commit so now 4 commit in your git log A,B,C,D.
* you realize you have pushed wrong last two commit is C,D. So you want to reset your branch till commit B.
* Run  ```git reset --hard B_commit_id``` and ```git push origin main --force```.
* Now your head is on commit B and reset the changes till commit B. 
* And you have two commit A,B in git log and  C,D commit deleted permanently.
* This command you can use for delete wrong local commits(commits you have not pushed). but it will reset your commit changes till commit id you will pass. you can use git stash for save changes of commits you want to delete on local before reset commit.
* Don't use reset command to delete commit it will reset changes till commit/id you will pass and will delete above commits.


# Git Stash:
Description: git stash command used to save changes on local. \
```git stash``` \
```git stash list``` \
```git stash apply {unique id}``` \
```git stash pop``` \
```git stash clean``` 

Example 1: 
* save the changes in particular(index) file. 
* Run git stash save "changes in index file". 
* changes will save by name "changes in index file". 
* Run git stash list #To check all save satsh list. \
  i.e: stash@{0}: On main: changes in index file 
* Run git stash apply stash@{0} when you need changes again in index file.

Example 2: 
* Save changes to branch A. 
* Run git stash. 
* Check out branch B. 
* Fix the bug in branch B. 
* Commit and (optionally) push to remote. 
* Check out branch A. 
* Run git stash pop / git stash apply stash@{0} #to get your stashed changes back.


# Git cherry-pick:
Description: using Cherry picking command you can pick a commit from a branch and applying/inherit it to another. \
```git cherry-pick commit_id``` 

Example: 
* Save changes to branch A in file index.txt. 
* Run git commit -m "branch A index file changes". 
* Run git push origin A. 
* Run git log. 
* your last commit is 2ea77c01["branch A index file changes"].

* Check out branch B. \
* git cherry-pick 2ea77c01 # 2ea77c01 is commit_id. \
* you can check your branch A commit [branch A index file changes] changes comes in branch B index.txt file \
  Commit and (optionally) push to remote.


# Git merge:
Description: Git merge is a command that allows you to merge two branches. \
```git merge branch_name``` #branch_name is the branch you want to merge with current branch.

Example: \
1).Suppose originally there were 3 commits, A,B,C in branch main. \
2).your another developer who is working on branch develop have made two more changes with commit D, E so in branch develop now 5 commits A,B,C,D,E. \
3).Now you want those develop branch all commits in main. you need to run merge command. \
4). git checkout main. \
5). git merge develop. \
6). Now develop branch's D,E commits code is reflecting in main branch with new commit suppose M(ie: Merge branch 'develop' into main). So now there is 4 commit A,B,C and M in commit history. It preserves complete history and chronological order. \
If you get conflict while merging resolve conflicts git add (changes) git merge --continue.


# Git Rebase:
Description :Git rebase is a command that allows developers to integrate changes from one branch to another. \
```git rebase branch_name```  #branch_name is the branch you want to merge with current branch. 

Git Merge and Git Rebase are both used to combine the changes of branches but in a distinct way.

Example: \
1).Suppose originally there were 3 commits, A,B,C in branch main and same in develop branch. \
2).your another developer who is working on branch main have made two more changes with commit D, E so in branch main now 5 commits A,B,C,D,E. \
3).Now you want rebase those main branch all commits in develop. you need to run merge command. \
4). git checkout develop. \
5). git rebase main. \
6). Now main branch's D, E code is reflecting in develop branch as well as in commit history. So now there is 5 commit A,B,C,D,E in straight line  same as main branch in develop commit history. \
If you get conflict while rebasing resolve conflicts git add (changes) git rebase --continue.


# Git delete branch:
Description: To delete created branch. \
```git branch -d branch-name``` \
```git push origin --delete``` \
Example: \
First run this command ```git branch -d branch-name``` after then run ```git push origin --delete```.


# Git Revert:
Description: git revert command is used for undoing changes to a repository's commit. \
```git revert <commit-ID>``` \
```git push --force origin main``` \
Example: \
First run this command ```git revert <commit-ID>``` after then run ```git push --force origin main```.


# Git Delete the most recent commit:
Delete the most recent commit on local, keeping the work: \
```git reset --soft HEAD~1```  

Delete the most recent commit on remote: \
```git reset --hard HEAD~1``` \
```git push origin master --force``` 

Delete the most recent commit on remote by reset command:
* Suppose you have 3 commit in git log A,B,C and you want delete commit C.
* Copy C commit id/hash.
* Run  ```git reset --hard B_commit_id``` and ```git push origin main --force```.
* Now your head is on commit B and reset the changes till commit B. 
* And you have two commit A,B in git log and  C commit is deleted permanently.

*If you want again back your commit use cherry-pick command: \
```git cherry-pick commit_id```




# Git add or remove username/email:
By command: \
```git config --global user.name "gargmani312"``` \
```git config --global user.email "gargmani312@gmail.com"``` 

By changing in config file: \
Open .gitconfig file with ```nano ~/.gitconfig``` and add email and userer in opened file like as mantioned below: 
```
[user]
        name = gargmani312
        email = gargmani312@gmail.com
        useconfigonly = true
[credential]
        username = gargmani312
```
# Use Multiple Git Account In Linux
Create a folder in home directory name ```.git_cred```
Create separate file for each account e.g you have a account named ```gargmani``` you need to create a file named ```.gargmani``` and put the credentials as ```https://username:password@github.com``` After that go to project directory and then .git --> config and then update this file as 
```
[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
[remote "origin"]
	url = https://github.com/gargmani312/git-commands.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
	remote = origin
	merge = refs/heads/master
[credential]
        helper = store --file /home/mani/.git_cred/.gargmani
```