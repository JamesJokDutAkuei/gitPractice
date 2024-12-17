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
LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/bundle-2)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git branch
  dev
  ft/bundle-2
  ft/service-redesign
* main

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git checkout ft/service-redesign
Switched to branch 'ft/service-redesign'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ ls
README.md  index.css  index.html  index.js  services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ vi services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ vi services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git add .

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git commit -m "added a paragraph and h2"
[ft/service-redesign d7f4a20] added a paragraph and h2
 1 file changed, 2 insertions(+)

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git push origin ft/service-redesign
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 321 bytes | 321.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/service-redesign' on GitHub by visiting:
remote:      https://github.com/JamesJokDutAkuei/gitPractice/pull/new/ft/service-redesign
remote:
To https://github.com/JamesJokDutAkuei/gitPractice.git
 * [new branch]      ft/service-redesign -> ft/service-redesign

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$  git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ vi services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ echo "<p>Conflicting Service Changes</p>" >> services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git add .
warning: in the working copy of 'services.html', LF will be replaced by CRLF the next time Git touches it

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git commit -m "Add conflicting changes to services.html"
[main a223722] Add conflicting changes to services.html
 1 file changed, 1 insertion(+)

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 343 bytes | 343.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/JamesJokDutAkuei/gitPractice.git
   a491cfc..a223722  main -> main

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ ls
README.md  index.css  index.html  index.js  services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ cat services.html
<h1>Our Services</h1>
<p>Our services are life changing</p>
<p>Conflicting Service Changes</p>

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git checkout ft/service-redesign
Switched to branch 'ft/service-redesign'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git diff main
diff --git a/services.html b/services.html
index be93d05..1b74710 100644
--- a/services.html
+++ b/services.html
@@ -1,3 +1,3 @@
 <h1>Our Services</h1>
 <p>Our services are life changing</p>
-<p>Conflicting Service Changes</p>
+<h2>How?</h2>

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ vi services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git merge main
Auto-merging services.html
CONFLICT (content): Merge conflict in services.html
Automatic merge failed; fix conflicts and then commit the result.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign|MERGING)
$ vi services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign|MERGING)
$ git merge main
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign|MERGING)
$ git add .

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign|MERGING)
$ git status
On branch ft/service-redesign
All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
        modified:   services.html


LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign|MERGING)
$ git commit -m "merged files"
[ft/service-redesign e1f935b] merged files

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git push origin ft/service-redesign
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 212 bytes | 212.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/JamesJokDutAkuei/gitPractice.git
   d7f4a20..e1f935b  ft/service-redesign -> ft/service-redesign

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git merge main
Already up to date.
```


## Buddle 3

### Exercise 1

```bash

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git branch ft/team-page

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git checkout ft/team-page
Switched to branch 'ft/team-page'
M       README.md

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ ls
README.md  index.css  index.html  index.js  services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ vi team.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git add team.html
warning: in the working copy of 'team.html', LF will be replaced by CRLF the next time Git touches it

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git push origin ft/team-page
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'ft/team-page' on GitHub by visiting:
remote:      https://github.com/JamesJokDutAkuei/gitPractice/pull/new/ft/team-page
remote:
To https://github.com/JamesJokDutAkuei/gitPractice.git
 * [new branch]      ft/team-page -> ft/team-page

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ ls
README.md  index.css  index.html  index.js  services.html  team.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ cat team.html
<h1>Our Team</h1>

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git status
On branch ft/team-page
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md


LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git add .

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git commit -m "team file"
[ft/team-page 7a71bfc] team file
 2 files changed, 168 insertions(+)
 create mode 100644 team.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git push origin ft/team-page
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 1.48 KiB | 758.00 KiB/s, done.
Total 4 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/JamesJokDutAkuei/gitPractice.git
   7327306..7a71bfc  ft/team-page -> ft/team-page

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git branch ft/contact-page

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git checkout ft/team-page
Switched to branch 'ft/team-page'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git log
commit 7a71bfc63fa881eb59ecb2cf04e64cdfa6ff4179 (HEAD -> ft/team-page, origin/ft/team-page)
Author: James <jokakeerleek@gmail.com>
Date:   Tue Dec 17 23:51:19 2024 +0200

    team file

commit 7327306b269dbb2e7e04b9fa62a21b9dad58ad1d (origin/main, main, ft/contact-page)
Merge: a223722 e1f935b
Author: James Jok Dut Akuei <155956159+JamesJokDutAkuei@users.noreply.github.com>
Date:   Tue Dec 17 23:28:16 2024 +0200

    Merge pull request #2 from JamesJokDutAkuei/ft/service-redesign

    added a paragraph and h2

commit e1f935b75bbe255ed66f6bef624de7ecd8adbf13 (origin/ft/service-redesign, ft/service-redesign)
Merge: d7f4a20 a223722
Author: James <jokakeerleek@gmail.com>
Date:   Tue Dec 17 23:27:08 2024 +0200

    merged files

commit a223722bbff4aa0bb88c2d5cfc8168f3a0ba5d38
Author: James <jokakeerleek@gmail.com>
Date:   Tue Dec 17 23:12:50 2024 +0200

    Add conflicting changes to services.html

commit d7f4a2054d2996a26b22fa9c730fd3756e7468ab
Author: James <jokakeerleek@gmail.com>
Date:   Tue Dec 17 21:09:55 2024 +0200

    added a paragraph and h2

commit a491cfc8028b1f1f6f310aeb0b32c18ae20712dd
Author: James <jokakeerleek@gmail.com>
Date:   Tue Dec 17 21:03:05 2024 +0200

    added a paragraph

commit 667dc3210b0b706a3d495b3554a0393150575865
Author: James <jokakeerleek@gmail.com>
Date:   Tue Dec 17 20:51:18 2024 +0200

    Gym Git Exercise Solutions or terminal history

commit e494c79922e68a9a24c56ad2ca782ddbbb7a2537
Merge: 86fca50 1df2aaf
Author: James Jok Dut Akuei <155956159+JamesJokDutAkuei@users.noreply.github.com>
Date:   Tue Dec 17 20:32:43 2024 +0200

    Merge pull request #1 from JamesJokDutAkuei/ft/bundle-2

    Add services.html page

commit 1df2aaf1f36f0b9ef041450122f5ce1e5057da16 (origin/ft/bundle-2, ft/bundle-2)

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git checkout  ft/contact-page
Switched to branch 'ft/contact-page'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ git log -1
commit 7327306b269dbb2e7e04b9fa62a21b9dad58ad1d (HEAD -> ft/contact-page, origin/main, main)
Merge: a223722 e1f935b
Author: James Jok Dut Akuei <155956159+JamesJokDutAkuei@users.noreply.github.com>
Date:   Tue Dec 17 23:28:16 2024 +0200

    Merge pull request #2 from JamesJokDutAkuei/ft/service-redesign

    added a paragraph and h2

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ git cherry-pick  7a71bfc63fa881eb59ecb2cf04e64cdfa6ff4179
[ft/contact-page 5024f2b] team file
 Date: Tue Dec 17 23:51:19 2024 +0200
 2 files changed, 168 insertions(+)
 create mode 100644 team.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ ls
README.md  index.css  index.html  index.js  services.html  team.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ vi contact.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ git add .
warning: in the working copy of 'contact.html', LF will be replaced by CRLF the next time Git touches it

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ git status
On branch ft/contact-page
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   contact.html


LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ git commit -m "added a h1"
[ft/contact-page 3e82cf8] added a h1
 1 file changed, 1 insertion(+)
 create mode 100644 contact.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ git push origin ft/contact-page
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (7/7), 1.76 KiB | 599.00 KiB/s, done.
Total 7 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/contact-page' on GitHub by visiting:
remote:      https://github.com/JamesJokDutAkuei/gitPractice/pull/new/ft/contact-page
remote:
To https://github.com/JamesJokDutAkuei/gitPractice.git
 * [new branch]      ft/contact-page -> ft/contact-page

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ git branch ft/faq-page

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ git branch
  dev
  ft/bundle-2
* ft/contact-page
  ft/faq-page
  ft/service-redesign
  ft/team-page
  main

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ git branch -v
  dev                 86fca50 initial files
  ft/bundle-2         1df2aaf Add services.html page with content
* ft/contact-page     3e82cf8 added a h1
  ft/faq-page         3e82cf8 added a h1
  ft/service-redesign e1f935b merged files
  ft/team-page        7a71bfc team file
  main                7327306 Merge pull request #2 from JamesJokDutAkuei/ft/service-redesign

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/contact-page)
$ git checkout ft/faq-page
Switched to branch 'ft/faq-page'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/faq-page)
$ vi faq.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/faq-page)
$ git add .
warning: in the working copy of 'faq.html', LF will be replaced by CRLF the next time Git touches it

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/faq-page)
$ git commit -m "added a faq intro"
[ft/faq-page 80c8d48] added a faq intro
 1 file changed, 1 insertion(+)
 create mode 100644 faq.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/faq-page)
$ git push origin faq.html
error: src refspec faq.html does not match any
error: failed to push some refs to 'https://github.com/JamesJokDutAkuei/gitPractice.git'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/faq-page)
$ git push origin ft/faq-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 321 bytes | 321.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/JamesJokDutAkuei/gitPractice/pull/new/ft/faq-page
remote:
To https://github.com/JamesJokDutAkuei/gitPractice.git
 * [new branch]      ft/faq-page -> ft/faq-page

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/faq-page)
$ git checkout ft/team-page
Switched to branch 'ft/team-page'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git revert 7a71bfc63fa881eb59ecb2cf04e64cdfa6ff4179
[ft/team-page 62d8952] Revert "team file"
 2 files changed, 168 deletions(-)
 delete mode 100644 team.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ ls
README.md  index.css  index.html  index.js  services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git status
On branch ft/team-page
nothing to commit, working tree clean

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git add .

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git status
On branch ft/team-page
nothing to commit, working tree clean

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/team-page)
$ git push origin ft/team-page
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 327 bytes | 327.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/JamesJokDutAkuei/gitPractice.git
   7a71bfc..62d8952  ft/team-page -> ft/team-page

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/bundle-2)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git branch
  dev
  ft/bundle-2
  ft/service-redesign
* main

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git checkout ft/service-redesign
Switched to branch 'ft/service-redesign'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ ls
README.md  index.css  index.html  index.js  services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ vi services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ vi services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git add .

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git commit -m "added a paragraph and h2"
[ft/service-redesign d7f4a20] added a paragraph and h2
 1 file changed, 2 insertions(+)

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git push origin ft/service-redesign
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 321 bytes | 321.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/service-redesign' on GitHub by visiting:
remote:      https://github.com/JamesJokDutAkuei/gitPractice/pull/new/ft/service-redesign
remote:
To https://github.com/JamesJokDutAkuei/gitPractice.git
 * [new branch]      ft/service-redesign -> ft/service-redesign

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$  git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ vi services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ echo "<p>Conflicting Service Changes</p>" >> services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git add .
warning: in the working copy of 'services.html', LF will be replaced by CRLF the next time Git touches it

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git commit -m "Add conflicting changes to services.html"
[main a223722] Add conflicting changes to services.html
 1 file changed, 1 insertion(+)

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 343 bytes | 343.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/JamesJokDutAkuei/gitPractice.git
   a491cfc..a223722  main -> main

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ ls
README.md  index.css  index.html  index.js  services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ cat services.html
<h1>Our Services</h1>
<p>Our services are life changing</p>
<p>Conflicting Service Changes</p>

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git checkout ft/service-redesign
Switched to branch 'ft/service-redesign'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git diff main
diff --git a/services.html b/services.html
index be93d05..1b74710 100644
--- a/services.html
+++ b/services.html
@@ -1,3 +1,3 @@
 <h1>Our Services</h1>
 <p>Our services are life changing</p>
-<p>Conflicting Service Changes</p>
+<h2>How?</h2>

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ vi services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git merge main
Auto-merging services.html
CONFLICT (content): Merge conflict in services.html
Automatic merge failed; fix conflicts and then commit the result.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign|MERGING)
$ vi services.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign|MERGING)
$ git merge main
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign|MERGING)
$ git add .

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign|MERGING)
$ git status
On branch ft/service-redesign
All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
        modified:   services.html


LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign|MERGING)
$ git commit -m "merged files"
[ft/service-redesign e1f935b] merged files

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git push origin ft/service-redesign
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 212 bytes | 212.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/JamesJokDutAkuei/gitPractice.git
   d7f4a20..e1f935b  ft/service-redesign -> ft/service-redesign

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$ git merge main
Already up to date.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/service-redesign)
$
```

## Buddle 3

### Exercise 2

```bash


LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git checkout ft/faq-page
Switched to branch 'ft/faq-page'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/faq-page)
$ git branch -v
  dev                 86fca50 initial files
  ft/bundle-2         1df2aaf Add services.html page with content
  ft/contact-page     3e82cf8 added a h1
* ft/faq-page         80c8d48 added a faq intro
  ft/service-redesign e1f935b merged files
  ft/team-page        62d8952 Revert "team file"
  main                e7c7c04 Merge branch 'main' of https://github.com/JamesJokDutAkuei/gitPractice

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/faq-page)
$ git branch ft/home-page-redesign

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/faq-page)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ echo "<!-- Updated Main Branch -->" >> index.html
bash: !-: event not found

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ echo "<!-- Updated Main Branch -->" > index.html
bash: !-: event not found

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ echo "<!-- Updated Main Branch -->" >> index.html
bash: !-: event not found

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ ^C

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ ls
README.md  contact.html  faq.html  index.css  index.html  index.js  services.html  team.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ vi index.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git add index.html
warning: in the working copy of 'index.html', LF will be replaced by CRLF the next time Git touches it

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git commit -m "Update index.html with changes in main branch"
[main a9b89b0] Update index.html with changes in main branch
 1 file changed, 1 insertion(+)

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 312 bytes | 312.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/JamesJokDutAkuei/gitPractice.git
   e7c7c04..a9b89b0  main -> main

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (main)
$ git checkout ft/home-page-redesign
Switched to branch 'ft/home-page-redesign'

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/home-page-redesign)
$ git rebase main
Successfully rebased and updated refs/heads/ft/home-page-redesign.

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/home-page-redesign)
$ echo "<h1>Welcome to Our Redesigned Home Page</h1>" > home.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/home-page-redesign)
$ git add home.html
warning: in the working copy of 'home.html', LF will be replaced by CRLF the next time Git touches it

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/home-page-redesign)
$ git commit -m "Add redesigned home page content"
[ft/home-page-redesign 241ec69] Add redesigned home page content
 1 file changed, 1 insertion(+)
 create mode 100644 home.html

LENOVO@DESKTOP-94SL70P MINGW64 ~/gitPracticeProject (ft/home-page-redesign)
$ git push origin ft/home-page-redesign
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 322 bytes | 322.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/JamesJokDutAkuei/gitPractice/pull/new/ft/home-page-redesign
remote:
To https://github.com/JamesJokDutAkuei/gitPractice.git
 * [new branch]      ft/home-page-redesign -> ft/home-page-redesign


```
