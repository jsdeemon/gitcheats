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
