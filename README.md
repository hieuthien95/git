https://www.youtube.com/playlist?list=PLNRc263j7V3uUviCSOamkXQ77mfXyCgI_

# (IV) Week 4
## 1. Config
```
$ git config --global user.name "ThienBH"
$ git config --global user.name
ThienBH

$ git config --global user.email "hieuthien95@gmail.com"
$ git config --global user.email
hieuthien95@gmail.com

$ git config --global core.editor "'E:\Soft\extract\nodepad++\notepad++.exe' -multiInst -nosession"
$ git config --global core.editor
'E:\Soft\extract\nodepad++\notepad++.exe' - multiInst -nosession

$ git config --list
core.symlinks=false
core.autocrlf=true
core.fscache=true
color.diff=auto
color.status=auto
color.branch=auto
color.interactive=true
help.format=html
rebase.autosquash=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
credential.helper=manager
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
core.editor='E:\Soft\extract\nodepad++\notepad++.exe' - multiInst -nosession
user.email=hieuthien95@gmail.com
user.name=ThienBH
```
```
git help
git <verb> --help
git help <verb>

$ git help
$ git clone --help
$ git help commit
```

# (V) Week 5
## 1. New repository local
```
$ git init
Initialized empty Git repository in C:/Users/hieut/Desktop/git-place/week 5/.git/

hieut@DESKTOP-M6CBJL7 MINGW64 ~/Desktop/git-place/week 5 (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        New folder/

nothing added to commit but untracked files present (use "git add" to track)

$ git add "New folder"

$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   New folder/readme.txt

$ git commit -m "init and add readme"
[master (root-commit) 85d78ff] init and add readme
 1 file changed, 1 insertion(+)
 create mode 100644 New folder/readme.txt

$ git status
On branch master
nothing to commit, working tree clean

$ git log
commit 85d78ff48e20f69f6b6e10746d63fc9618d64dc1 (HEAD -> master)
Author: ThienBH <hieuthien95@gmail.com>
Date:   Tue Mar 12 16:50:53 2019 +0700

    init and add readme
```

## 2. Repository remote
```
$ git clone https://github.com/hieuthien95/demo-repo.git
Cloning into 'demo-repo'...
remote: Enumerating objects: 58, done.
remote: Counting objects: 100% (58/58), done.
remote: Compressing objects: 100% (40/40), done.
remote: Total 58 (delta 4), reused 51 (delta 1), pack-reused 0
Unpacking objects: 100% (58/58), done.


hieut@DESKTOP-M6CBJL7 MINGW64 ~/Desktop/git-place/week 5.2/demo-repo (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    cai dat vuejs.txt - Shortcut.lnk

no changes added to commit (use "git add" and/or "git commit -a")

$ git add .

$ git commit -m "xoa file tao lao"
[master 79e9f73] xoa file tao lao
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 cai dat vuejs.txt - Shortcut.lnk

$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

$ git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 226 bytes | 226.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/hieuthien95/demo-repo.git
   f6d8073..79e9f73  master -> master

```
# (VI) Week 6
1. Checking the Status of file
   ```$ git status```
2. Tracking new files (staging)
   ```$ git add file_name```
3. Staging Modified files
   ```$ git status```
4. Short status
   ```$ git status -s
   $ git status --short```
5. Ignoring files: https://github.com/github/gitignore
   ```$ touch .gitignore```
6. Viewing Staged and Unstaged changes: khi 1 file đã staged, mà có thêm chỉnh sửa
   ```$ git diff
   $ git diff --staged```
7. Committing you changes
   ```$ git commit -m "message..."
   $ git commit       // de open editor```
8. Skipping the Staging area
   ```$ git add .
   $ git add -a
   $ git add --all```
9. Removing file
   ```$ git rm --cached <file>...```
10. Moving file: rename
   ```$ git mv ReadMe.txt ReadMe.md```

Untracked		Unmodified 			Modified		Staged

	[add the file----------------------------->
	
					        [edit file-->
					
									            [stage file--->
									
	<remove file----]
	
					        <-------------------commit]
          
```
$ git init
Initialized empty Git repository in C:/Users/hieut/Desktop/git-place/week 6/.git/
```

## 2. Tracking new files (staging)
** add file ReadMe.txt vào thư mục bằng explorer **
```
hieut@DESKTOP-M6CBJL7 MINGW64 ~/Desktop/git-place/week 6 (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        ReadMe.txt

nothing added to commit but untracked files present (use "git add" to track)

$ git add .

$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   ReadMe.txt
```

## 3. Staging Modified files
## 6. Viewing Staged and Unstaged changes
** edit ReadMe.txt mà hồi nãy đã add (staged) **
```
$ git status
On branch master

No commits yet

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   ReadMe.txt
```
```
$ git diff
diff --git a/ReadMe.txt b/ReadMe.txt
index 513fa74..9314cce 100644
--- a/ReadMe.txt
+++ b/ReadMe.txt
@@ -1 +1 @@
-this is first commit
\ No newline at end of file
+this is 2 commit
\ No newline at end of file
```

## 10. Moving file
```
$ git mv ReadMe.doc abc/ReadMe.txt

$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        renamed:    ReadMe.txt -> abc/ReadMe.txt  
```


