# Fork Workflow

## 01 to 03 are one time steps when you are configuring the repo
01. Clone fork
```
git clone git@github.com:USERNAME/FORKED-PROJECT.git
```

02. Add 'upstream' repo to list of remotes
```
git remote add upstream https://github.com/UPSTREAM-USER/ORIGINAL-PROJECT.git
```

03. Verify the new remote named 'upstream'
```
git remote -v
```

## Repeat
04. Fetch from upstream remote
```
git fetch upstream
```

05. View all branches, including those from upstream (Optional)
```
git branch -va
```

06. Checkout your master branch and merge upstream
```
git checkout master
git merge upstream/master
```

07. Checkout the master branch - you want your new branch to come from master
```
git checkout master
```

08. Push the latest master to origin so that it can be in sync with upstream
```
git push origin master
```

09. Create a new branch named newfeature (give your branch its own simple informative name) and checkout (This will be by default fast-forward branch)
```
git checkout -b newfeature
```

**Now do all the changes you need**

10 Add all and commit
```
git add --all
git commit -am "Your commit message"
```

11. (IMP) Fetch upstream master and merge with your repo's master branch (this step is really important if you don't want conflicts while you push)
```
git fetch upstream
git checkout master
git merge upstream/master
```

12. (Optional) If there were any new commits, rebase your development branch
```
git checkout newfeature
git rebase master
```

13. (Optional) Rebase all commits on your development branch. In case you want to squash your smaller commits into larger commits
```
git checkout 
git rebase -i master
```

14. Push the changes to origin
```
git push origin newfeature
```

15. If you are done with the feature you were working on, delete the branch
```
git branch -d newfeature
```
