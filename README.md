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
