# Git Exercises

## Buddle 1

### Exercise 1

```bash

LENOVO@DESKTOP-94SL70P MINGW64 ~
$ mkdir gitPracticeProject
LENOVO@DESKTOP-94SL70P MINGW64 ~
$ cd gitPracticeProject
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject
$ git init
Initialized empty Git repository in C:/Users/YourUsername/gitPracticeProject/.git/

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (master)
$ ls
index.css  index.html  index.js

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (master)
$ git branch -m main

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git add .

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git commit -m "Initial commit with project files"
[main (root-commit) ab12cd3] Initial commit with project files
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 index.css
 create mode 100644 index.html
 create mode 100644 index.js

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git remote add origin https://github.com/username/gitPracticeProject.git

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 213 bytes | 213.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/username/gitPracticeProject.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git checkout -b dev
Switched to a new branch 'dev'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git checkout -b test
Switched to a new branch 'test'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (test)
$ git checkout dev
Switched to branch 'dev'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git branch -d test
Deleted branch test (was ab12cd3).

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git branch
* dev
  main
```

### Exercise 2

```bash

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ touch home.html
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ vi home.html
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git status
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        home.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git add home.html
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git stash save "home.html changes"
Saved working directory and index state WIP on dev: ab12cd3 Initial commit with project files

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ touch about.html
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ vi about.html
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git add about.html
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git stash save "about.html changes"
Saved working directory and index state WIP on dev: ab12cd3 Initial commit with project files

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ touch team.html
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ vi team.html
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git add team.html
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git stash save "team.html changes"
Saved working directory and index state WIP on dev: ab12cd3 Initial commit with project files

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git stash list
stash@{0}: WIP on dev: ab12cd3 Initial commit with project files
stash@{1}: WIP on dev: ab12cd3 Initial commit with project files
stash@{2}: WIP on dev: ab12cd3 Initial commit with project files

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git stash pop stash@{1}
On branch dev
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   about.html

Dropped stash@{1} (was ab12cd3).

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git stash pop stash@{2}
On branch dev
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   home.html

Dropped stash@{2} (was ab12cd3).

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git add .
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git commit -m "Restored changes for home.html and about.html"
[dev f3a1b4d] Restored changes for home.html and about.html
 2 files changed, 2 insertions(+)
 create mode 100644 about.html
 create mode 100644 home.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git push origin dev
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Writing objects: 100% (6/6), 345 bytes | 345.00 KiB/s, done.
Total 6 (delta 0), reused 0 (delta 0)
To https://github.com/username/gitPracticeProject.git
 * [new branch]      dev -> dev

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git stash pop stash@{0}
On branch dev
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   team.html

Dropped stash@{0} (was ab12cd3).

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git reset --hard
HEAD is now at f3a1b4d Restored changes for home.html and about.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git status
On branch dev
nothing to commit, working tree clean


```

## Buddle 2

### Exercise 1

```bash

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (dev)
$ git checkout -b ft/bundle-2
Switched to a new branch 'ft/bundle-2'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/bundle-2)
$ touch services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/bundle-2)
$ echo "<h1>Our Services</h1>" > services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/bundle-2)
$ git status
On branch ft/bundle-2
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        services.html

nothing added to commit but untracked files present (use "git add" to track)

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/bundle-2)
$ git add services.html
warning: in the working copy of 'services.html', LF will be replaced by CRLF the next time Git touches it

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/bundle-2)
$ git commit -m "Add services.html page with content"
[ft/bundle-2 1df2aaf] Add services.html page with content
 1 file changed, 1 insertion(+)
 create mode 100644 services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/bundle-2)
$ git push origin ft/bundle-2
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 312 bytes | 312.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting:
remote:      https://github.com/JamesJokDutAkuei/gitPractice/pull/new/ft/bundle-2
remote:
To https://github.com/JamesJokDutAkuei/gitPractice.git
 * [new branch]      ft/bundle-2 -> ft/bundle-2


```
### Exercise 2


```bash



```
