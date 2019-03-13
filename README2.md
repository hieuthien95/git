# (IX) Làm việc với Remote
1. Show remotes
   ```
   $ git remote
   origin
   ```
   ```
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
   ```
   ```
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
   $ git remote rm ten-remote
   ```
   ```
   $ git remote rename thien-remote tenmoi
   $ git remote
   tenmoi
   ```

## 2. Add remote Repo:
_Khi đã có repo local, muốn add vào repo remote khac_
```
$ git remote add thien-remote https://github.com/hieuthien95/demo-repo.git
$ git remote
thien-remote
```

## 3. Fetching an Pull from Remotes
_lấy thông tin về_
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
_lấy data về_
```
$ git pull thien-remote master --allow-unrelated-histories
```

# (IX) Làm việc với Tag
1. List Tags
   ```
   $git tag
   ```
   ```
   $git tag -l "v.1.0.*"
   ```
   ```
   $ git ls-remote --tag thien-remote
   ```
2. Annotated Tags
   ```
   $ git tag -a v1.0 -m "create tag 1.0"
   ```
3. Lightweight Tags
   ```
   $ git tag v1.0
   ```
4. Tagging later
   ```
   $ git tag v1.0 commit_id
   ```
5. Sharing Tags
   ```
   $ git push remote_name v1.0
   ```
   ```
   $ git push remote_name --tags
   ```
6. Checkout Tags
   ```
   $ git checkout -b branch_name name_tag
   ```
7. Delete Tag
   ```
   $ git tag -d v1.0 v1.1
   Deleted tag 'v1.0' (was 74d356b)
   Deleted tag 'v1.1' (was 74d356b)
   ```
   ```
   $ git push remote_name --delete tag_name
   ```

## 2. Annotated Tags
```
$ git tag -a v1.0 -m "create tag 1.0"

$ git tag
v1.0

$ git show v1.0
tag v1.0
Tagger: ThienBH <hieuthien95@gmail.com>
Date:   Wed Mar 13 01:15:05 2019 +0700

create tag 1.0

commit 2de1baec913a89efe1ab9a80f75dcb6f4d2386ce (HEAD -> master, tag: v1.0, thien-remote/master)
Merge: 5263271 7061e9c
Author: ThienBH <hieuthien95@gmail.com>
Date:   Wed Mar 13 00:45:48 2019 +0700

    Merge branch 'master' of https://github.com/hieuthien95/demo-repo
```

## 5. Sharing Tags
```
$ git push thien-remote v1.0
Enumerating objects: 93, done.
Counting objects: 100% (93/93), done.
Delta compression using up to 4 threads
Compressing objects: 100% (73/73), done.
Writing objects: 100% (93/93), 86.23 KiB | 1.83 MiB/s, done.
Total 93 (delta 20), reused 0 (delta 0)
remote: Resolving deltas: 100% (20/20), done.
To https://github.com/hieuthien95/demo-repo.git
 * [new tag]         v1.0 -> v1.0

$ git push thien-remote --tags
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/hieuthien95/demo-repo.git
 * [new tag]         v0.1 -> v0.1
```

## 6. Checkout Tags
```
$ git checkout -b branch_demo_tags v1.0
Switched to a new branch 'branch_demo_tags'

$ git branch
* branch_demo_tags
  master

$ git push thien-remote branch_demo_tags
Total 0 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'branch_demo_tags' on GitHub by visiting:
remote:      https://github.com/hieuthien95/demo-repo/pull/new/branch_demo_tags
remote:
To https://github.com/hieuthien95/demo-repo.git
 * [new branch]      branch_demo_tags -> branch_demo_tags
```

# (XIII) Branch, Merge branch và xử lý Conlicts
## 1. Branch
**List Branch**
```
$ git branch
  branch_demo_tags
  master
* testing_br
```
**Thêm Branch**
```
$ git branch "ten_branch"
```
**Swich Branch**
```
$ git checkout ten_branch
Switched to branch 'ten_branch'
```

## 2. Merge branch
```
$ git merge branch_2_name
```
```
$ git branch
  branch_demo_tags
  master
* testing_br

$ git checkout master
Switched to branch 'master'

$ git merge testing_br
Already up to date.

$ git push --set-upstream thien-remote testing_br
Total 0 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'testing_br' on GitHub by visiting:
remote:      https://github.com/hieuthien95/demo-repo/pull/new/testing_br
remote:
To https://github.com/hieuthien95/demo-repo.git
 * [new branch]      testing_br -> testing_br
Branch 'testing_br' set up to track remote branch 'testing_br' from 'thien-remote'.
```

## 3. Xử lý Conlicts
```
$   git config --global diff.tool bc
$   git config --global difftool.bc.path "C:\Program Files (x86)\Beyond Compare 3\BCompare.exe"

$   git config --global merge.tool bc
$   git config --global mergetool.bc.path "C:\Program Files (x86)\Beyond Compare 3\BCompare.exe"
```
```
$ git pull

$ git merge origin/testing_br
Auto-merging ReadMe - Copy.txt
CONFLICT (content): Merge conflict in ReadMe - Copy.txt
Automatic merge failed; fix conflicts and then commit the result.

$ git mergetool
Merging:
ReadMe - Copy.txt

Normal merge conflict for 'ReadMe - Copy.txt':
  {local}: modified file
  {remote}: modified file
ReadMe - Copy.txt seems unchanged.
Was the merge successful [y/n]?
```

# (XIV) Quản lý nhánh local
```
$ git branch
  branch_demo_tags
  master
* testing_br
```
_Xem commit mới nhất của mỗi Branch_
```
$ git branch -v
* master 723f0e8 dđ
```
```
$ git branch --merged
  branch_demo_tags
  master
* testing_br

$ git branch --no-merged
```
_Xóa branch local_
```
$ git branch -d branch_name
```

# (XVI) Làm việc với branch trên remote
_Liệt kê các branche/tags_
```
$ git ls-remote thien-remote
$ git remote show thien-remote

$ git ls-remote
From https://github.com/hieuthien95/demo-repo.git
a5d67efbd8646e353734916b8163dbedf273271b        HEAD
2de1baec913a89efe1ab9a80f75dcb6f4d2386ce        refs/heads/branch_demo_tags
a5d67efbd8646e353734916b8163dbedf273271b        refs/heads/master
ad8848bc69cd61c065b4afcb85cc954c6f948519        refs/heads/testing_br
ce2fc49fd06e65e03b796454596f313e5a9556d2        refs/tags/v1.0
2de1baec913a89efe1ab9a80f75dcb6f4d2386ce        refs/tags/v1.0^{}
```
_Xóa branch_
```
$ git push origin --delete branch_demo_tags
To https://github.com/hieuthien95/demo-repo.git
 - [deleted]         branch_demo_tags
```
_config khi lam qua https_
```
$ git config --global credential.helper cache
```
_checkout 1 nhánh từ remote về local_
```
$ git checkout -b thien-remote/testing_br
Switched to a new branch 'thien-remote/testing_br'
```
```
$ git branch -vv
```
