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
   
####### Initializing ,adding ,commiting, and Status commands
    git init                            // how to intialize or start tracking a folder or a repository
    
    git add file-name                   // to add a single file into staging index
    
    git add .                           // to ad all files from working directory into staging index
    
    git commit -m " a good message"     // to commit changes from staging index into reposoitory
    
    git commit -am "a good message"     // adding and commiting from staging index into repository in one shot
    
    git status                          // viewing the status 

###### Working with the staging environment, reverting commited files
    git checkout index.html             // to undo changes in the working directory
    
    git checkout -- fileName            // to undo changes -- means to stay in the same branch
    
    git reset HEAD fileName             // to undo / unstage changes from staging index back into working directory
    
    git commit --amend -m "message"     // amending the last commit adding the changes to the last commit.
    
    git checkout SHA-1 filename         // SHA-1 must be the first 8 or 10 characters of the commit you want to retrieve
                                        // retrieving older version of file

    git revert SHA-1                    // reverting a commit

    


    
####### The GIT log command (viewing the commit log)
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
    

    
    
