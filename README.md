# Gitflow

### Commands reminder to start project with Gitflow
1) Init folder and first commit
```
echo "# gitflow" >> README.md
git init
git add README.md
git commit -m "first commit"
git push -u origin master
git remote add origin https://github.com/benjaminviaud/gitflow.git
```

2) Create `develop branch` and move inside
```
git checkout -b develop
```

3) Create `feature branch` and move inside
```
git checkout -b feature/name-of-feature
```

4) Work on `feature branch` and when I finished, push to remote repository
```
git push origin feature/name-of-feature
```

5) Go back on `develop branch`
```
git checkout develop
```

6) Merge the `feature branch` with `develop branch`  and remove it
(--no-ff option to no fast-forward)
```
git merge --no-ff feature/name-of-feature
git branch -d feature/name-of-feature
```
7) Push to the remote `develop branch`
```
git push origin develop
```

8) Create a `release branch`
```
git checkout -b release-0.1 develop
```
