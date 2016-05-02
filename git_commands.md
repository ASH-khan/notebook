# Most important GIT commands

#####How to set git configurations
    git config --global user.name "name"
    git config --global user.email "email"
    git config --global core.editor "atom -wl1"
    git config --global color.ui true

######GIT Autocompletion script
    curl -OL https://github.com/git/git/raw/master/contrib/completion/git-completion.bash

######Rename and hide the auto completion file
    mv ~/git-completion.bash ~/.git-completion.bash

######To make the auto completion file work add the following script into .bash_profile
    if [ -f ~/.git-completion.bash ]; then
      source ~/.git-completion.bash
      fi
      
###### GIT is a three tree architecture

    i.e. Repository =======> Staging index =========> working directory
    
######GIT help command
    git help "command name"
    
######GIT man command
   display the manual i.e $ man man or $ man help etc
   
######Initializing ,adding ,commiting, and Status commands
    git init                            // how to intialize or start tracking a folder or a repository
    
    git add file-name                   // to add a single file into staging index
    
    git add .                           // to ad all files from working directory into staging index
    
    git commit -m " a good message"     // to commit changes from staging index into reposoitory
    
    git commit -am "a good message"     // adding and commiting from staging index into repository in one shot
    
    git status                          // viewing the status 

######Working with the staging environment, reverting commited files
    git checkout index.html             // to undo changes in the working directory
    
    git checkout -- fileName            // to undo changes -- means to stay in the same branch
    
    git reset HEAD fileName             // to undo / unstage changes from staging index back into working directory
    
    git commit --amend -m "message"     // amending the last commit adding the changes to the last commit.
    
    git checkout SHA-1 filename         // SHA-1 must be the first 8 or 10 characters of the commit you want to retrieve
                                        // retrieving older version of file

    git revert SHA-1                    // reverting a commit

    git rm --cached filename            // to ignore already tracked file

######Dangerous and power full reset command to reset multiple commits
    git reset --soft SHA-1              // the safe way --soft only change the pointer

    git reset --mixed SHA-1             // mixed way --mixed change the staging index to match repository
                                        // does not change working repository

    git reset --hard SHA-1              // hard way --hard changing staging and working directory both to match repository

######Removing untracked files
    git clean -n                        // this will remove files from staging index to working directory to be ready for                                       // removal
    
    git clean -f                        // this will remove all the working directory files

    git rm --cached filename            // to ignore already tracked file







    


    
######The GIT log command (viewing the commit log)
    git log
    
    git log -n 5                        // to view / show the last 5 commits
    
    Using since ,until, and author name etc with the log commands
    
    git log --since = date                // show commits log since the date given
    
    git log --until = date                // show commits log until the given date
    
    git log --author = "author name"
    
    git log --oneline                     // very good command to show the commit log in oneline
    
    git log --oneline 5                   // to show 5 commits in oneline
    
    git log --grep = "REgExpression"      // to search for certain regular expression in the commit log
    
    git log SHA1..SHA2 --oneline          // to show the range from SHA1 to SHA2
    
    git log SHA2.. index.html             // to show commit log from SHA2 to end for inex.html file.
    
    git log -p
    
    git log --stat --summary
    
    git log --format  = oneline
    
    git log --format = short
    
    git log --format = full or fuller or email
    
    git log --oneline --graph --all --decorate  // very good command shows in color and more readable form
    
    git log show SHA-1
    
######Comparing commits
    git diff SHA-1
    
    git diff SHA-1..SHA-1
    
    git diff --stat --summary SHA-1..SHA-1
 
    git diff -b SHA-1..SHA-1

    git diff -w SHA-1..SHA-1

######Viewing changes with diff comparing versions
    git diff

    git diff filename.txt

    git diff color-words filename

    git diff -w
    
######Viewing changes that are already staged
    git diff --staged

######How git track the changes
    using SHA-1 or checksum Algorithm
    SHA-1 is a 40 hexadecimal string (0-9 a-f)

######HEAD in git : lets know a bit more about HEAD in GIT
    HEAD always point to the last commit in the repository
    
    git log HEAD                                // will display the last SHA-1

######div deep in HEAD
    cat HEAD                                    [result refs/heads/master]

    cd refs

    cd heads

    cat master                                  [will be always showing the last commit HEAD]    

######Deleting files
    git rm file-name.extension

    git commit -m "deletion message"    
    
######Moving and renaming files
    git mv original-file-name new-file-name
    
######Pushing local repository into github
    git remote add <alias> <url>

    git remote add origin https://github.com/Avenger4568/git-practice.git

    git remote

    git remote -v

######Branching
    git branch
 
    git branch -r // will show the remote branches

    git branch -a // will show both local and remote

######Information about branches are always stored in heads directory
    cat .git/refs/heads

######Creating a new branch
    git branch new-branch-name

######Switching branches or checking out new branch
    git checkout branch-name                                // active branch name

######Creating and switching branch in a single command
    git checkout -b branch-

######Comparing branches
    git diff branch..branch

######The best way to check changes that are merged is:
    git branch --merged

######Renaming branch
    git branch -m old-name new-name

######Deleting branch
    git branch -d branch name

    git branch -D branch name                               // forcing deleteion without alert
    
######Merging branches make sure you are on the receiving branch.
    git merge branch-name (this is fast merge)

    git merge --no-ff branch-name                           //no fast merge good if you want to add documentation
    
######Aborting the merge incase of conflict
    git merge --abort

######Can also see where git stores these info
    cat .git/config

######Removing the remote repository
    git remote rm origin

#####To push changes to remote repository or creating a remote branch
    git push -u origin master

######Stashing changes
    git stash save "message"

######Viewing remote stash
    git stash list
    
    git stash show stash@{0}

    git stash show -p stash@{0}

    git stash pop stash@{index}

######Retrieving stashed changes
    git stash pop stash@{index} // or apply

######Deleting stashed changes
    git stash drop stash@{index}

    git stash clear
