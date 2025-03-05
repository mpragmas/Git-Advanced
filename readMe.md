# Advanced Git Part1

```bash


#---------------------------1----------


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

#------------------------5-----------------------------------

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

# -----------------------6------------------

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

#--------------------------7---------------------

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

#--------------------------10--------------------

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

# Advanced Git Part2

```bash

#--------------------------1-------------------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git branch ft/new-feature
fatal: a branch named 'ft/new-feature' already exists

#--------------------------2---------------------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> echo "this new feature" > feature.txt
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git add feature.txt
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git commit -m "implemented core functionality for  new feature"
[ft/new-feature b8c0197] implemented core functionality for  new feature
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature.txt

 #--------------------------3----------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> echo "welcome to my project" > readme.txt
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git add readme.txt
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git commit -m "updated project  readme "
[main ab8482a] updated project  readme
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 readme.txt


#----------------------------4---------------------

 PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git push origin ft/new-feature
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 326 bytes | 163.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/mpragmas/Git-Advanced/pull/new/ft/new-feature
remote:
To https://github.com/mpragmas/Git-Advanced.git
 * [new branch]      ft/new-feature -> ft/new-feature
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git fetch origin
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git pull origin main
From https://github.com/mpragmas/Git-Advanced
 * branch            main       -> FETCH_HEAD
Already up to date.

#------------------------5-----------------------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git branch -d ft/new-feature
error: the branch 'ft/new-feature' is not fully merged
hint: If you are sure you want to delete it, run 'git branch -D ft/new-feature'
hint: Disable this message with "git config advice.forceDeleteBranch false"
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git branch -D ft/new-feature
Deleted branch ft/new-feature (was b8c0197).
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git push origin --delete ft/new-feature
To https://github.com/mpragmas/Git-Advanced.git
 - [deleted]         ft/new-feature


 #-------------------------6-------------------

 PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git log --oneline
ab8482a (HEAD -> main) updated project  readme
381d9af (origin/main) first commit
e0d830d Implemented test 5
70c7fad chore: Create fourth file
9e3468a chore: Create third file
b4de24e chore: Create initial file
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git checkout -b ft/new-branch-from-commit ab8482a
M       readMe.md
Switched to a new branch 'ft/new-branch-from-commit'

#-------------------------7-----------------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git checkout main
M       readMe.md
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git merge ft/new-branch-from-commit
Already up to date.


#---------------------------8-------------------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git checkout ft/new-branch-from-commit
M       readMe.md
Switched to branch 'ft/new-branch-from-commit'

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git rebase main
Current branch ft/new-branch-from-commit is up to date.
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced>

#---------------------------9---------------------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git branch -m ft/new-branch-from-commit ft/improved-branch-name

#---------------------------10--------------------


PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git log --oneline
e50c6e2 (HEAD -> ft/improved-branch-name) first commit
ab8482a (main) updated project  readme
381d9af (origin/main) first commit
e0d830d Implemented test 5
70c7fad chore: Create fourth file
9e3468a chore: Create third file
b4de24e chore: Create initial file


PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git checkout e0d830d
Note: switching to 'e0d830d'.
You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at e0d830d Implemented test 5
```

# Advanced Git Part3

```bash

#---------------------1------------------------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git stash
Saved working directory and index state WIP on main: 787c3ed updated

#---------------------2------------------------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git stash pop
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (d5bdc75d5e014ba21161ceb242b4dc97cd879a5a)

#---------------------3------------------------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git checkout  ft/improved-branch-name
Switched to branch 'ft/improved-branch-name'

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git add readme.txt
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git commit -m "resolving conflicts"
[main 0c96fba] resolving conflicts
 1 file changed, 0 insertions(+), 0 deletions(-)

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git merge main
Updating 1dec886..d4124c1
Fast-forward
 readMe.md  |  66 ++++++++++++++++++++++++++++++++++++++++++++++++++-----------
 readme.txt | Bin 96 -> 58 bytes
 2 files changed, 54 insertions(+), 12 deletions(-)
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced>

#---------------------4------------------------


PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git mergetool
This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
tortoisemerge emerge vimdiff nvimdiff
No files need merging
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git config --global merge.tool vscode
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git config --global mergetool.vscode.cmd "code --wait $MERGED"
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git mergetool
No files need merging

#---------------------5------------------------

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git checkout main
Previous HEAD position was 25b826e Merged ft/improved-branch-name and resolved conflict in readme.txt
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 13 commits.
  (use "git push" to publish your local commits)

PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced> git checkout  new-branch-from-detached
Switched to branch 'new-branch-from-detached'
PS C:\Users\HP\Documents\lesson\TheGym\Git Advanced>

#---------------------6------------------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (new-branch-from-detached)
$ touch .gitignore

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (new-branch-from-detached)
$ git status
On branch new-branch-from-detached
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

nothing added to commit but untracked files present (use "git add" to track)

#---------------------7------------------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (new-branch-from-detached)
$ git tag v1.0

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (new-branch-from-detached)
$ git log
commit e92dc1f3b16df6c441a7d5888fd398b4542576fd (HEAD -> new-branch-from-detached, tag: v1.0)
Author: mpragmas <mpragmas@gmail.com>
Date:   Tue Mar 4 15:34:33 2025 +0200

    updated

commit e0d830d8e110d33ccf6632c220cad9b5cea66e65
Author: mpragmas <mpragmas@gmail.com>
Date:   Tue Mar 4 11:57:42 2025 +0200

    Implemented test 5

commit 70c7fad8977977096fda399f6a14faea132f4d36
Author: mpragmas <mpragmas@gmail.com>
Date:   Tue Mar 4 11:48:32 2025 +0200


HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (new-branch-from-detached)
$ git tag v1.0 e92dc1f3b16df6c441a7d5888fd398b4542576fd
fatal: tag 'v1.0' already exists

#---------------------8------------------------

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (new-branch-from-detached)
$ git tag
v1.0

HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (new-branch-from-detached)
$ git tag -d v1.0
Deleted tag 'v1.0' (was e92dc1f)

#---------------------9------------------------


HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (new-branch-from-detached)
$ git push origin main
Enumerating objects: 40, done.
Counting objects: 100% (39/39), done.
Delta compression using up to 12 threads
Compressing objects: 100% (33/33), done.
Writing objects: 100% (34/34), 3.16 KiB | 202.00 KiB/s, done.
Total 34 (delta 19), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (19/19), completed with 2 local objects.
To https://github.com/mpragmas/Git-Advanced.git
   787c3ed..1026a7a  main -> main


#---------------------10------------------------


HP@DESKTOP-IPFMADI MINGW64 ~/Documents/lesson/TheGym/Git Advanced (new-branch-from-detached)
$ git pull origin main
From https://github.com/mpragmas/Git-Advanced
 * branch            main       -> FETCH_HEAD
Auto-merging readMe.md
CONFLICT (add/add): Merge conflict in readMe.md
Automatic merge failed; fix conflicts and then commit the result.

```
