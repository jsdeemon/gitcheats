# Git Cheat sheet
### Pull requesting: 

1. Fork the repo 
2. Clone forked repo 
3. check to new branch: 
```bash
$ git checkout -b newbranchName 
```
4. Make upstream original repo: 
```bash
$ git remote add upstream https://github.com/username/originalrepo
```
5. Work on your branch and make commits 
6. Push:
```bash
$ git push -u origin newbranchName
```
7. Complete pull request on the github web page

8. To update repository from original:
```bash
$ git pull upstream main
```
### Interactive rebase 
To optimize and clean up commit history
!!! Do NOT use interactive rebase on commits that you have already pushed / shared on a temote repository
Instead, use it for cleaning up your local commit history before merging it into a shared team branch 

Return back to 3 commits 
```bash 
$ git log --oneline 
$ git rebase -i HEAD~3
```
To change commit message need to change first word from 'pick' to 'reword'
Save and close the window with commits 
Then change text of commit in new window and close it
Interactive rebase keywords:
squash - combines commit with previos commits 

### Cherry picking
Cherry picking need for special situations 
need a good reason to use it 
Moving commit to a different branch in case you made a commit to wrong branch
1. Go to rhe branch where you wanna to remove commit
```bash
$ git checkout feature/newsletter
```
2. Remove commit to that branch
```bash 
$ git cherry-pick hashOfCommit
```
for example
```bash
$ git cherry-pick 20db43dj 
```
to delete commit from master branch
```bash
$ git ckeckout master 
$ git reset --hard HEAD~1
```

### Reflog
it is like a git diary 
a protocol of HEAD pointer movements

Recovering deleted commits with Reflog 
```bash
$ git reflog 
$ git branch feature/login b3sg3hj
```

### Submodules 
in case of copu-pasting third party code in your project 
example
```bash
$ mkdir lib
$ cd lib 
git submodule add https://github.com/ysername/reponame 
``` 
To update submodules
```bash
$ git submodule update --init --recursive
```
To clone
```bash
$ git clone --recurse-submodules https://github.com/username/reponame.git
```

### Search & find
Filter your commit history
by date
```bash
$ git log --after="2022-1-25"
$ git log --after="2022-1-25" --before="2022-1-30"
```
by message
find a certain commit message by containing keyword
```bash
$ git log --grep="keyword"
```
by author
```bash
$ git log --author="AuthorName" 
```
You can combine
``bash
$ git log --author="AuthorName" --after="2022-1-25" --before="2022-1-30"
```
by file
```bash
$ git log -- fileName
```
by branch 
to find all commits that are in main, but not in feature/login
```bash
$ git log feature/login..main
```

### Discarding changes
1. Discardig all local changes in file
```bash
$ git diff fileName.js 
$ git restore fileName.js 
```
!!!Discarding uncommitted local changes cannot be undone!!! 
2. Resoring a deleted file 
```bash
$ git restore fileName.js 
```
3. Discarding chunks / lines in a file 
```bash
$ git diff fileName 
$ git restore -p fileName 
```
    
TO RESTORE ALL CAHNGES
```bash
$ git restore . 
```
!!!dicrding uncommitted changes cannot be undone !!!

5. Fixing the last commit 
```bash
$ git commit --amend -m "Correct" 
```
!!! "--amend" rewrites history! Never change history for commits that have already been pushed to a remote repository! 
