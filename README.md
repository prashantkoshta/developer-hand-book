# Help Note

##Git Command
### To clone perticualr branch of git
```bash
git clone -b <branch_name> <remote_repo>(git@github.com:prashantkoshta/angularjs-dashboard.git)
```
### To checkout perticular branch
```bash
git checkout  -b <branch_name>
```
### To commit changes on git
- check git status
```bash
git status
```
- add modifed files. `.` show add all modified files. If you need to add specific file give file name instead of `.`.
```bash
git add .
```
- Check file status
```bash
git status
```
- Commit changes
```bash
git commit -m "<YOUR_COMMENTS_ON_COMMIT>
```
- Push changes
```bash
git push
```
### Set Beyond Compare as difftool for git.
```bash
git config --global diff.tool bc3
git config --global difftool.bc3.path "C:/Program Files (x86)/Beyond Compare 3/BCompare.exe"
```
### Show last log. -4 show last 4 logs.
```bash
git log -4
```
### To check file difference by BC tool.
```bash
git difftool
```
### To check difference between local version with remote version.
```bash
git fetch origin
git diff <branch_name> origin/<branch_name>
```
If difftool already set then
```bash
git fetch origin
git difftool <branch_name> origin/<branch_name>
```
### To clean untracked git file
```bash
git clean -df
```

### To reset local version with remote branch (revert local changes)
```bash
git reset --hard HEAD
```

### Show list of file changed form last commit. If you like to see previos 2 then use `HEAD~2`.
```bash
git diff --name-only HEAD HEAD~1
```
