# Gitflow - Commands Reminder

### New project
1) Init folder and first commit
```
echo "# gitflow" >> README.md
git init
git add README.md
git commit -m "init commit"

OR

git init
git commit --allow-empty -m "init branch master"
```
And push to remote repo
```
git remote add origin https://github.com/benjaminviaud/gitflow.git
git push -u origin master
```

2) Create `develop branch` and move inside
```
git checkout -b develop
```

3) Create `feature branch` and move inside
```
git checkout -b feature/name-of-feature
```

4) Work on `feature branch`.

If I would like to share with other people for improve this feature (pull request), or work with other people on this feature, or other reason, push to remote repository
```
git push origin feature/name-of-feature
```

5) If I finished the feature, I go back on `develop branch`
```
git checkout develop
```

6) Merge the `feature branch` with `develop branch`  and remove it
```
git merge --no-ff feature/name-of-feature
git branch -d feature/name-of-feature
```
7) Push to the remote `develop branch`
```
git push origin develop
```

8) Create a `release branch` and move inside
```
git checkout -b release-0.0.1 develop
```

9) Work on `release branch` just for fix bugs. Large new features strictly prohibited.
```
git commit -a -m "version number 0.0.1"
```

10) When the `release branch` has finished
```
git checkout master
git merge --no-ff release-0.0.1
```

11) Add a tag for this release
```
git tag -a 0.0.1
```
12) Push the tag to the remote repository
```
git push origin --tags
```

### Clone project

1) Clone a project
```
git clone https://github.com/benjaminviaud/gitflow.git

cd gitflow
```

2) Clone one remote branch
```
git checkout name-of-the-remote-branch
```

3) Go to the step 3 New project (see above)


### Remiser (stash)

#### Mettre de côté un travail en cours (et le reprendre plus tard)
1) remiser l'état en cours avec les fichiers non suivi (-u untracked file)
```
git stash push -u -m "ajouter mes fichiers à la zone Remise (stash)"
```

2) restaurer l'état remisé

a) et supprimer de la remise la sauvegarde (pop)
```
git stash pop --index
```
b) sans supprimer de la remise la sauvegarde (apply)
```
git stash apply --index
```

### Revenir sur un commit
 
1) pour annuler le commit et revenir à l'état indexé
```
git reset --soft HEAD~1
```

2) pour annuler le commit et revenir à l'état de la copie de travail
```
git reset --mixed HEAD~1
```

3) pour annuler tout travail dans le commit et dans les 3 zones (copie de travail, index, dépot local)
```
git reset --keep HEAD~1
```