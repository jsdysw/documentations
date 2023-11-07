# git-tutorial

source : https://backlog.com/git-tutorial/kr/

### Glosary
- work tree : work place
- index : space for ````add````s, staging
- repository : space for ````commit````s
- stash : temporary space to save current work without commit and checkout another branch

### remote repository
| Command | usage |
| --- | --- |
| init | ````git init```` |
| status | ````git status```` |
| add all | ````git add -A```` |
| add file | ````git add filename```` |
| commit | ````git commit -m "message"```` |
| log | ````git log```` |
| clone | ````git clone url```` |
| remote list | ````git remote -v```` |
| remote add | ````git remote add origin url```` |
| pull(merge commit) | ````git pull origin master```` (-> solve conflict -> commit) |
| fetch | ````git fetch origin```` |
| push | ````git push origin master```` |

### branch
| Command | usage |
| --- | --- |
| list branch | ````git branch```` |
| make branch | ````git branch name```` |
| delete branch | ````git branch -d name```` |
| checkout | ````git checkout name```` |
| make and checkout | ````git checkout -b name```` |
| merge(fast-forward) | ````git merge branchname ````|
| merge(non fast-forward) | ````git merge branchname```` (-> solve conflict -> add,commit) |
| integrate & merge | ````git merge --squash branchname```` -> add -> ````git commit```` |
| rebase | ````git rebase branchname```` (-> solve conflict -> add -> ````git rebase --continue````) -> ````git checkout branchname```` -> ````git merge firstbranch```` |

### change commit
| Command | usage |
| --- | --- |
| edit commit message | ````git commit --amend```` |
| revert (recent commit) | ````git revert HEAD```` |
| reset(hard) | ````git reset --hard commitToGo```` |
| cherry pick | ````git cherry-pick commit```` |
| integrate commits | ````git rebase -i HEAD~~```` -> squash|
| edit commit | ````git rebase -i HEAD```` -> edit -> add, commit --amend -> (solve conflict -> add) -> ````git rebase --continue```` | 
* git reset --hard ORIG_HEAD : to reset rebase -i

### tag
| Command | usage |
| --- | --- |
| make tag | ````git tag tagname```` |
| tag list | ````git tag```` |
| tag list with comment | ````git tag -n```` |
| log with tag name | ````git log --decorate```` |
| make tag with comment | ````git tag -a tagname```` |
| make tag with comment2 | ````git tag -am "message" tagname```` |
| delete tag | ````git tag -d tagname```` |




