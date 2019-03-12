https://www.youtube.com/playlist?list=PLNRc263j7V3uUviCSOamkXQ77mfXyCgI_

# Week 4
## Config
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

# Week 5
## New repository local
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
## Repository remote
