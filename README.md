# Help Note

##Git Command
### To clone perticualr branch of git
```bash
git clone -b <branch_name> <remote_repo>(git@github.com:prashantkoshta/angularjs-dashboard.git)
```
### To checkout perticular branch
```bash
git checkout <branch_name>
```
### To create new branch form existing branch. 
- Checkout branch from which you want to create new branch. Like i checkout master and from master i am createing new branch `dev_0.1`
```bash
git checkout <exiting_branch_name>
git checkout -b <new_branch_name>
git push <remote-name> <branch_name>
```
Where `<remote-name>` is typically `origin`, the name which git gives to the remote you cloned from.
Example:
```bash
git checkout master
git checkout -b dev_0.1
git push origin dev_0.1
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
### Merging branch and solving conflits
Assuming you have 2 branch master and dev_0.1. dev_0.1 is 2 commit behind the master. Now we have to merge master changes into dev_0.1. So my dev_0.1 will includ all master recent changes. 
```bash
git checkout <branch_name> Like dev_0.1
git merge <remote_name>/<branch_name> Like git merge orgin/master
```
- It may show confilit or auto merge changes.
- If it show confilit then your branch bash path show like `(dev_0.1|MERGING)`. In this case we have confilict on code. It dispaly like this in confilict files.
```bash
<<<<<<< HEAD
	res.send("Hello world now");
=======
	res.send("Hello World Master Change");
>>>>>>> origin/master
```
- Next step remove confilict from files and chek file status and commit then push.
```bash
git status
git commit -m "<YOUR_COMMENTS_ON_COMMIT>"
git push
```
