# learning_git
## this repo is used to learn git and github

git config --global user.name <name>
git config --global user.email <email>

git config --global color.ui auto // for coloring

git init . //initilazing git in local machin the first time
           // if we clone the git we do not have to do git init

git add . // to add all file to the staging area
git add <file name> //add single file to the staging area
git add -A // add all file with out respect to the current folder
           //git add . only add the current folder file
           // git add -A this add all the file even out side of current folder

git commit -m "" //for commit and add message
git commit --amend -m "" //to ammend the current message we were 
                         //commited
git log //show the commitd file

git log --oneline //show all the commit in one line 

git diff // show the different 

git restore <file name>// restore back to previous status

#######Push#########
push an existing repository from the command line
git remote add origin <repo name like https://github.com/elias-teshome/learning_git.git>
git branch -M main
git push -u origin main //this is for the first time push

git push //this is later push

when we already push local repo to github we do not have to 
do git push -u origin main just git push is enough

###########Pull#############
pull is the revers of push, get file from github to local machine

git pull

##########Branches###############
git branch // tells you which branch are currently working
           // only tell us the local branch
git branch -r // the same thing but tell us the remote branch

git branch -d <branch name> //deleting local branch not the remote


git branch -a //show all branches

git branch <name>// to create branch

git checkout <branch name>//to switch branches

git checkout -// this switch to the previus branch

//the local branch should be pushed to the github 
at the first time use 

git push -u origin <branch name> or  git push --set-upstream origin <branch name>


//not the first time use 
git push

git checkout -b <branch name>// creating and checkout to the new branch. this is 2 
                        //steps 

deleting local branch use:

 git branch -d branch_name
 git branch -D branch_name
The -d option is an alias for --delete, which only deletes the branch if it has already been fully merged in its upstream branch. You could also use -D, which is an alias for --delete --force, which deletes the branch "irrespective of its merged status." [Source: man git-branch]
Also note that git branch -d branch_name will fail if you are currently in the branch you want to remove. The message starts with error: Cannot delete the branch 'branch_name'. If so, first switch to some other branch, for example: git checkout main.

deleting remote branch use:

git push origin --delete {the_remote_branch}

in short

Deleting a remote branch

git push origin --delete <branch>  # Git version 1.7.0 or newer
git push origin -d <branch>        # Shorter version (Git 1.7.0 or newer)
git push origin :<branch>          # Git versions older than 1.7.0

Deleting a local branch

git branch --delete <branch>
git branch -d <branch> # Shorter version
git branch -D <branch> # Force-delete un-merged branches

########merge ##############
becare full to merge your branch to the main or master
branch instead of doing git merge <branch name> in the main branch.
use a pull requesst and some one upprove you code to merge then 
you can merege that to main. this is all done in the github sit not in the bash 

after resieving a request from some body then you can merge to main


############git work flow#################
you should always pull the latest from the main branch first
then creat your the branch by using git checkout -b <branch name>//this is two steps
then work on your branch may have many commit and then if conflict happes
first squash all the commit and stash it then rebase the main to your branch then add the stash on top of it
the push to your branch safelly finally ask a pull request to merge to main

###############rebase#####################
take the latest changes from main branch and add our chnage on top of it.

git pull -r origion main or git pull --rebase origion main// this bring the latest change in main and  add to 
our branch the put our branch on top of it.
when this happen conflict may occur so, resolve conflice first manualy then 

use :
git add .
git rebase --continue

again conflict occure may be use 

git add .
git rebase --continue

use the above command repeatedly until all the conflict gone
then finaly rebase successfully done use 

gut push -f// force push to your branch.



