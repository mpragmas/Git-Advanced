# Advanced Git Part1

```bash

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ touch test{1..4}.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git init
Reinitialized existing Git repository in C:/Users/HP/Documents/lesson/TheGym/Git Advanced/.git/

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git add test1.md && git commit -m "chore: Create initial file"
[master (root-commit) 5320ed0] chore: Create initial file
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test1.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git add test2.md && git commit -m "chore: Create another file"
[master 0cd9220] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test2.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git add test3.md && git commit -m "chore: Create third and fourth files"
[master 447bbe2] chore: Create third and fourth files
1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git add test4.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git commit --amend -m "chore: Create third and fourth files"
[master 660dea6] chore: Create third and fourth files
Date: Mon Mar 3 12:50:15 2025 +0200
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test3.md
create mode 100644 test4.md

#----------------------2--------------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git rebase -i HEAD~2
[detached HEAD a1aef64] chore: Create second file
Date: Mon Mar 3 12:49:57 2025 +0200
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test2.md
Successfully rebased and updated refs/heads/master.

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git log --oneline --graph --decorate --all

- 10d049c (HEAD -> master) chore: Create third and fourth files
- a1aef64 chore: Create second file
- 5320ed0 chore: Create initial file

#----------------------3--------------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git rebase -i HEAD~3
fatal: invalid upstream 'HEAD~3'

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git rebase -i --root
[detached HEAD b4de24e] chore: Create initial file
Date: Mon Mar 3 12:49:56 2025 +0200
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test1.md
create mode 100644 test2.md
Successfully rebased and updated refs/heads/master.

#----------------------4--------------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git reset HEAD~1

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git add test3.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git commit -m "chore: Create third file"
[master af9b769] chore: Create third file
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test3.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git add test4.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git commit -m "chore: Create fourth file"
[master b65b449] chore: Create fourth file
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test4.md

#-----------------5---------------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git rebase -i HEAD~2
[detached HEAD 787ba9b] This is a combination of 2 commits.
Date: Mon Mar 3 12:59:49 2025 +0200
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test3.md
create mode 100644 test4.md
Successfully rebased and updated refs/heads/master.

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git log --oneline
787ba9b (HEAD -> master) This is a combination of 2 commits.
b4de24e chore: Create initial file

# -----------------6------------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ touch unwanted.txt

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git add unwanted.txt

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git commit -m "Unwanted commit"
[master 427e823] Unwanted commit
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 unwanted.txt

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git rebase -i HEAD~1
Successfully rebased and updated refs/heads/master.

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git log --oneline
787ba9b (HEAD -> master) This is a combination of 2 commits.
b4de24e chore: Create initial file

#--------------------7---------------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master) 2,1 Top
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/master.

#-------------------------- 8---------------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (master)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (ft/branch)
$ touch test5.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (ft/branch)
$ echo "Hello, Test 5" > test5.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (ft/branch)
$ git add test5.md
warning: in the working copy of 'test5.md', LF will be replaced by CRLF the next time Git touches it

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (ft/branch)
$ git commit -m "Implemented test 5"
[ft/branch b2b6bf6] Implemented test 5
1 file changed, 1 insertion(+)
create mode 100644 test5.md

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (ft/branch)
$ git checkout main
Switched to branch 'main'

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (main)
$ git log --oneline ft/branch
b2b6bf6 (ft/branch) Implemented test 5
70c7fad (HEAD -> main) chore: Create fourth file
9e3468a chore: Create third file
b4de24e chore: Create initial file

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (main)
$ git cherry-pick b2b6bf6
[main e0d830d] Implemented test 5
Date: Tue Mar 4 11:57:42 2025 +0200
1 file changed, 1 insertion(+)
create mode 100644 test5.md

#---------------------------9----------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (main)
$ git log --graph --oneline --all

- e0d830d (HEAD -> main) Implemented test 5
  | \* b2b6bf6 (ft/branch) Implemented test 5
  |/
- 70c7fad chore: Create fourth file
- 9e3468a chore: Create third file
- b4de24e chore: Create initial file

#-----------------------10--------------------
HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (main)
$ git reflog
e0d830d (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
70c7fad HEAD@{1}: checkout: moving from main to main
70c7fad HEAD@{2}: checkout: moving from ft/branch to main
b2b6bf6 (ft/branch) HEAD@{3}: commit: Implemented test 5
70c7fad HEAD@{4}: checkout: moving from master to ft/branch
70c7fad HEAD@{5}: rebase (finish): returning to refs/heads/master
70c7fad HEAD@{6}: rebase (start): checkout HEAD~2
70c7fad HEAD@{7}: commit: chore: Create fourth file
9e3468a HEAD@{8}: commit: chore: Create third file
b4de24e HEAD@{9}: reset: moving to HEAD~1
a1a5077 HEAD@{10}: reset: moving to HEAD~1
430f0f0 HEAD@{11}: commit: chore: Create fourth file
a1a5077 HEAD@{12}: commit: chore: Create third file
b4de24e HEAD@{13}: reset: moving to HEAD~1
787ba9b HEAD@{14}: rebase (finish): returning to refs/heads/master
787ba9b HEAD@{15}: rebase (start): checkout HEAD~1
787ba9b HEAD@{16}: rebase (finish): returning to refs/heads/master
787ba9b HEAD@{17}: rebase (start): checkout HEAD~1
427e823 HEAD@{18}: commit: Unwanted commit
787ba9b HEAD@{19}: rebase (finish): returning to refs/heads/master
787ba9b HEAD@{20}: rebase (squash): This is a combination of 2 commits.
af9b769 HEAD@{21}: rebase (start): checkout HEAD~2
b65b449 HEAD@{22}: commit: chore: Create fourth file
af9b769 HEAD@{23}: commit: chore: Create third file
:

```
