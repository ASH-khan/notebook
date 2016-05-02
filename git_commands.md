# Most important GIT commands

###How to set git configurations
    git config --global user.name "name"
    git config --global user.email "email"
    git config --global core.editor "atom -wl1"
    git config --global color.ui true

####GIT Autocompletion script
    curl -OL https://github.com/git/git/raw/master/contrib/completion/git-completion.bash

###rename and hide the auto completion file
    mv ~/git-completion.bash ~/.git-completion.bash

###To make the auto completion file work add the following script into .bash_profile
    if [ -f ~/.git-completion.bash ]; then
      source ~/.git-completion.bash
      fi


