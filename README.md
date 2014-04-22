# git-update

A lazy way to update many git repositories at once

Put git-update script with repo-list to the root path of your project
then change the repo list to match your repo.
 
## How to run 

./git-update [-rvcpb:P:f:][--branch: --fall:] [branch] [--path:] [workpath]


* -v, --verbose   Y'all know what it's for :)
* -r, --reset     Unsaved work will be discard (prompt)
* -p, --prune     Remove all local branches with no remote branch
* -c, --compare   Compare ahead/behind to the fallback branch (still in beta)
* -b, --branch    Target branch to checkout to; able to use part of the name, default is develop
* -P, --path      Set base working path
* -F, --fall      Fallback branch, default is develop
 
```
./git-update -vb feature-01 -F develop
```

**chmod is required to make git-update executable**

### Log

Log file is store in /tmp/git-update_DATETIME.log.
 
## For Mac OS X users
readarray is not available on bash 3.2 on OS X
to use this script, please install bash 4.2 (via homebrew) by following these steps

```
$ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
$ brew install bash
$ sudo mv /bin/bash /bin/bash.3.2.bk
$ sudo ln -s /usr/local/Cellar/bash/4.2.xx/bin/bash /bin/bash (replace xx with subversion number)
```

then restart terminal

## Alias
Shell alias is recommended to make git-update easy for everyday use.

Bash alias can be set in ~/.bashrc (or ~/.bash_profile in OS X)

See more about Bash alias [here](http://tldp.org/LDP/abs/html/aliases.html).

```
alias update='$HOME/work/git-update/git-update -v'
alias gomaster='$HOME/work/git-update/git-update -vb master'
```

bash restart is required after .bashrc update.

## git-clone

Companion to the git-update script

Let you clone many repos from what's in repo_list with one command.

* -v 			Verbose
* -d 			Target directory, default is $HOME/src/startsiden
* -u 			Run git-update after finish repo cloning, branch name required as args

```
./git-clone -vd "$HOME/work"
```
