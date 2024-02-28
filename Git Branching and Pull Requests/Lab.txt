1.Using Git Commands

Stefan Stoyanov@USER MINGW64 ~
$ git clone https://github.com/SUContent/playground
Cloning into 'playground'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 6 (delta 0), reused 1 (delta 0), pack-reused 0
Receiving objects: 100% (6/6), done.

Stefan Stoyanov@USER MINGW64 ~
$ dir
Postman
PrintHood
Recent
Saved\ Games
Searches
SendTo
Start\ Menu
playground

Stefan Stoyanov@USER MINGW64 ~
$ cd playground

Stefan Stoyanov@USER MINGW64 ~/playground (main)
$ git add .

Stefan Stoyanov@USER MINGW64 ~/playground (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md


Stefan Stoyanov@USER MINGW64 ~/playground (main)
$ git commit -m "changes"
[main b9a893b] changes
 1 file changed, 2 insertions(+)

Stefan Stoyanov@USER MINGW64 ~/playground (main)
$ git push

2.Git Conflict Scenario

Stefan Stoyanov@USER MINGW64 ~/playground (main)
$ git clone https://github.com/gambittest/main.git
Cloning into 'main'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.

Stefan Stoyanov@USER MINGW64 ~/playground (main)
$ cd main

Stefan Stoyanov@USER MINGW64 ~/playground/main (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

Stefan Stoyanov@USER MINGW64 ~/playground/main (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

Stefan Stoyanov@USER MINGW64 ~/playground/main (main)
$ git add .

Stefan Stoyanov@USER MINGW64 ~/playground/main (main)
$ git commit -m "conflict"
[main b59da97] conflict
 1 file changed, 2 insertions(+)

Stefan Stoyanov@USER MINGW64 ~/playground/main (main)
$ git push

3.Git Branches
Stefan Stoyanov@USER MINGW64 ~/Desktop
$ git clone https://github.com/iamstefanstoyanov/TestRepo.git
Cloning into 'TestRepo'...
warning: You appear to have cloned an empty repository.

Stefan Stoyanov@USER MINGW64 ~/Desktop
$ git status
fatal: not a git repository (or any of the parent directories): .git

Stefan Stoyanov@USER MINGW64 ~/Desktop
$ cd TestRepo

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git status
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html
        styles.css

nothing added to commit but untracked files present (use "git add" to track)

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git add .

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git commit -m "new files"
[main (root-commit) 267ae35] new files
 2 files changed, 22 insertions(+)
 create mode 100644 index.html
 create mode 100644 styles.css

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 653 bytes | 163.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/iamstefanstoyanov/TestRepo.git
 * [new branch]      main -> main

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git branch add-title

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git checkout add-title
Switched to branch 'add-title'

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (add-title)
$ git add .

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (add-title)
$ git commit -m "Title added!"
[add-title (root-commit) 267ae35] new files
 1 files changed, 12 insertions(+)
 create mode 100644 index.html

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (add-title)
$ git push

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (add-title)
$ git push --set-upstream origin add-title

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git checkout main

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git merge add-title

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git push

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git branch d add-title

Stefan Stoyanov@USER MINGW64 ~/Desktop/TestRepo (main)
$ git push origin d add-title