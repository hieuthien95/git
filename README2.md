# (IX) Làm việc với Remote
1. Show remotes
   ```
   $ git remote
   origin
   
   $ git remote -v
   origin  https://github.com/hieuthien95/demo-repo.git (fetch)
   origin  https://github.com/hieuthien95/demo-repo.git (push)
   ```
2. Add remote Repo
   ```
   $ git remote add thien-remote https://github.com/hieuthien95/demo-repo.git
   ```
3. Fetching an Pull from Remotes
   ```
   $ git fetch thien-remote
   $ git pull thien-remote
   ```
4. Push to Remote: sẽ push data dưới repo local lên repo remote
   ```
   $ git push thien-remote master
   ```
5. Inspecting a Remote
   ```
   $ git remote show thien-remote
   ```
6. Remove and Rename Remotes
   ```
   $ git remote rename thien-remote tenmoi
   $ git remote
   tenmoi

   $ git remote rm ten-remote
   ```

## 2. Add remote Repo:
__Khi đã có repo local, muốn add vào repo remote khac__
```
$ git remote add thien-remote https://github.com/hieuthien95/demo-repo.git
$ git remote
thien-remote
```

## 3. 
__lay thong tin ve__
```
$ git fetch thien-remote
warning: no common commits
remote: Enumerating objects: 83, done.
remote: Counting objects: 100% (83/83), done.
remote: Compressing objects: 100% (63/63), done.
remote: Total 83 (delta 18), reused 57 (delta 3), pack-reused 0
Unpacking objects: 100% (83/83), done.
From https://github.com/hieuthien95/demo-repo
 * [new branch]      master     -> thien-remote/master
```
__lay data ve__
```
$ git pull thien-remote master --allow-unrelated-histories
```

# (IX) Làm việc với Tag






