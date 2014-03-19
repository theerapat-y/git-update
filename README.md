git-update
==========

A lazy way to update many git repositories at once

Put git-update script with repo-list to the root path of your project
then change the repo list to match your repo.
 
to run ./git-update [-rvpb:P:f:][--branch: --fall:] [branch] [--path:] [workpath]
-v, --verbose   Print out all debug message
-r, --reset     Unsaved work will be discard (prompt)
-p, --prune     Remove all local branches with no remote branch
-b, --branch    Branch to go to; able to use part of the name, default is develop
-P, --path      Set base working path
-F, --fall      Fallback branch, default is develop
 
e.g. ./git-update -vb SOK-308 -F develop
 
log file is store in /tmp/git-update_DATETIME.log
**chmod is required to make git-update executable**
 
For Mac OS X users:
readarray is not available on bash 3.2 on OS X
to use this script, please install bash 4.2 (via homebrew) by following these steps
 
$ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
$ brew install bash
$ sudo mv /bin/bash /bin/bash.3.2.bk
$ sudo ln -s /usr/local/Cellar/bash/4.2.xx/bin/bash /bin/bash (replace xx with subversion number)
 
then restart terminal