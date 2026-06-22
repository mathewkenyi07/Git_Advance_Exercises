# Advance Git exercises

## Exercise 1 

### Part 1

```bash

MATHEW@Matt MINGW64 ~/Desktop/Git Advance
$ git init
Initialized empty Git repository in C:/Users/MATHEW/Desktop/Git Advance/.git/

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ touch test{1..4}.md

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[main (root-commit) 2ac1326] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
[main f0d6333] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[main bdbb03e] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log
commit bdbb03edee26e5231554d351ff928f149314d8ec (HEAD -> main)
Author: matt <mathewkenyi47@gmail.com>
Date:   Thu Jun 18 10:48:26 2026 +0200

    chore: Create third and fourth files

commit f0d633352555364e786fa9a1aab41b6902857983
Author: matt <mathewkenyi47@gmail.com>
Date:   Thu Jun 18 10:48:26 2026 +0200

    chore: Create another file

commit 2ac13261a36678c6821610e2761f081569dd1e43
Author: matt <mathewkenyi47@gmail.com>
Date:   Thu Jun 18 10:48:25 2026 +0200

    chore: Create initial file

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git add test4.md 

$ git commit --amend -m "chore: Create third and fourth files"
[main ac7b8fd] chore: Create third and fourth files
 Date: Thu Jun 18 10:48:26 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git status
On branch main
nothing to commit, working tree clean

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log
commit ac7b8fd85305493bde31ea93f473dd938ffb3f98 (HEAD -> main)
Author: matt <mathewkenyi47@gmail.com>
Date:   Thu Jun 18 10:48:26 2026 +0200

    chore: Create third and fourth files

commit f0d633352555364e786fa9a1aab41b6902857983
Author: matt <mathewkenyi47@gmail.com>
Date:   Thu Jun 18 10:48:26 2026 +0200

    chore: Create another file

commit 2ac13261a36678c6821610e2761f081569dd1e43
Author: matt <mathewkenyi47@gmail.com>
Date:   Thu Jun 18 10:48:25 2026 +0200

    chore: Create initial file
```

### Part 2

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git rebase -i --root
[detached HEAD 8fc3091] chore: Create initial file
 Date: Thu Jun 18 10:48:25 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
812e9bd (HEAD -> main) chore: Create third and fourth files
8fc3091 chore: Create initial file
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git rebase -i --root
hint: Waiting for your editor to close the 
Stopped at 812e9bd...  # chore: Create third and fourth files
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main|REBASE 2/2)
$ git status
interactive rebase in progress; onto 25e2225
Last commands done (2 commands done):
   pick 8fc3091 # chore: Create initial file
   edit 812e9bd # chore: Create third and fourth files
No commands remaining.
You are currently editing a commit while rebasing branch 'main' on '25e2225'.
  (use "git commit --amend" to amend the current commit)
  (use "git rebase --continue" once you are satisfied with your changes)

nothing to commit, working tree clean

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main|REBASE 2/2)
$ git reset HEAD^

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main|REBASE 2/2)
$ git add test3.md

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main|REBASE 2/2)
$ git commit -m "Create Third File"
[detached HEAD e211c72] Create Third File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 ```

### Part 3

```bash 
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git rebase -i --root
[detached HEAD 8fc3091] chore: Create initial file
 Date: Thu Jun 18 10:48:25 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
812e9bd (HEAD -> main) chore: Create third and fourth files
8fc3091 chore: Create initial file
```

### Part 4

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main|REBASE 2/2)
$ git status
interactive rebase in progress; onto 25e2225
Last commands done (2 commands done):
   pick 8fc3091 # chore: Create initial file
   edit 812e9bd # chore: Create third and fourth files
No commands remaining.
You are currently editing a commit while rebasing branch 'main' on '25e2225'.
  (use "git commit --amend" to amend the current commit)
  (use "git rebase --continue" once you are satisfied with your changes)

nothing to commit, working tree clean
```

### Part 5

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
04dc7d4 (HEAD -> main) Create fourth file
e211c72 Create Third File
8fc3091 chore: Create initial file
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git rebase -i --root
hint: Waiting for your editor to close the 
hint: Waiting for your editor to close the 
[detached HEAD 4f2faff] Create Third File
 Date: Thu Jun 18 11:47:12 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
4f2faff (HEAD -> main) Create Third File
8fc3091 chore: Create initial file
```

### Part 6

```bash 
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
04dc7d4 (HEAD -> main) Create fourth file
e211c72 Create Third File
8fc3091 chore: Create initial file
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git rebase -i --root
hint: Waiting for your editor to close the 
hint: Waiting for your editor to close the 
[detached HEAD 4f2faff] Create Third File
 Date: Thu Jun 18 11:47:12 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
4f2faff (HEAD -> main) Create Third File
8fc3091 chore: Create initial file
```

### Part 7

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git rebase -i --root
Successfully rebased and updated refs/heads/main.

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
4f2faff (HEAD -> main) Create Third File
8fc3091 chore: Create initial file
```

### Part 8

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git switch -c ft/branch
Switched to a new branch 'ft/branch'

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/branch)
$ touch test5.md

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/branch)
$ ech "This is test 5 content" > test5.md
bash: ech: command not found

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/branch)
$ echo "This is test 5 content" > test5.md

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/branch)
$ git add test5.md
warning: in the working copy of 'test5.md', LF will be replaced by CRLF the next time Git touches it

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/branch)
$ git commit -m "Implemented test 5"
[ft/branch 8d5d866] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/branch)
$ git log --oneline
8d5d866 (HEAD -> ft/branch) Implemented test 5
4f2faff (main) Create Third File
8fc3091 chore: Create initial file
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/branch)
$ git switch main
Switched to branch 'main'

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git cherry-pick 8d5d866
[main 61f4506] Implemented test 5
 Date: Thu Jun 18 12:19:01 2026 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
61f4506 (HEAD -> main) Implemented test 5
4f2faff Create Third File
8fc3091 chore: Create initial file

```

### Part 9

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
61f4506 (HEAD -> main) Implemented test 5
4f2faff Create Third File
8fc3091 chore: Create initial file

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --graph
* commit 61f45061233c46c99b935bff6aebf20ea24cea8f (HEAD -> main)
| Author: matt <mathewkenyi47@gmail.com>
| Date:   Thu Jun 18 12:19:01 2026 +0200
| 
|     Implemented test 5
| 
* commit 4f2faff01c861c8929c2d3765f18133a05b3fb10
| Author: matt <mathewkenyi47@gmail.com>
| Date:   Thu Jun 18 11:47:12 2026 +0200
| 
|     Create Third File
|     
|     Create fourth file
| 
* commit 8fc3091623f459b8d1146ac547655a60d04361d4
  Author: matt <mathewkenyi47@gmail.com>
  Date:   Thu Jun 18 10:48:25 2026 +0200
  
      chore: Create initial file

```

### Part 10

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git reflog
61f4506 (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
4f2faff HEAD@{1}: checkout: moving from ft/branch to main
8d5d866 (ft/branch) HEAD@{2}: commit: Implemented test 5
4f2faff HEAD@{3}: checkout: moving from main to ft/branch
4f2faff HEAD@{4}: rebase (finish): returning to refs/heads/main
4f2faff HEAD@{5}: rebase: fast-forward
8fc3091 HEAD@{6}: rebase: fast-forward
995bcc7 HEAD@{7}: rebase (start): checkout 995bcc75c942a80f678d5c4d8ca507fb9506dd29
4f2faff HEAD@{8}: rebase (abort): returning to refs/heads/main
4f2faff HEAD@{9}: rebase (abort): returning to refs/heads/main
```

## Exercise 2

### Part 1

```bash
$ git switch -c ft/new-feature
Switched to a new branch 'ft/new-feature'

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/new-feature)
$ git branch
  ft/branch
* ft/new-feature
  main
```

### Part 2

```bash 
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/new-feature)
$ touch feature.txt

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/new-feature)
$ echo "This the content of new-feature branch">feature.txt

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/new-feature)
$ git add feature.txt
warning: in the working copy of 'feature.txt', LF will be replaced by CRLF the next time Git touches it

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/new-feature)
$ git commit -m "Implemented core functionality for new feature"
[ft/new-feature e236d9d] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```

### Part 3

```bash 
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/new-feature)
$ git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ touch readme.txt

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ echo "Hello this is matt">readme.txt

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git add readme.txt
warning: in the working copy of 'readme.txt', LF will be replaced by CRLF the next time Git touches it

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git commit -m "Updated project readme"
[main f674d9f] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
```

### Part 4

```bash

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git push
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 16 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 483 bytes | 241.00 KiB/s, done.
Total 5 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/mathewkenyi07/Git_Advance_Exercises.git
   d3f4b83..f674d9f  main -> main

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git push -u origin ft/new-feature
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 331 bytes | 331.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/mathewkenyi07/Git_Advance_Exercises/pull/new/ft/new-feature
remote: 
To https://github.com/mathewkenyi07/Git_Advance_Exercises.git
 * [new branch]      ft/new-feature -> ft/new-feature
branch 'ft/new-feature' set up to track 'origin/ft/new-feature'.

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git merge ft/new-feature 
Merge made by the 'ort' strategy.
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 300 bytes | 300.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/mathewkenyi07/Git_Advance_Exercises.git
   f674d9f..b31b9b3  main -> main

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

### Part 5

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git branch
  ft/branch
  ft/new-feature
* main

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git branch -d ft/new-feature
Deleted branch ft/new-feature (was e236d9d).

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git branch
  ft/branch
* main
```

### Part 6

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
b31b9b3 (HEAD -> main, origin/main) Merge branch 'ft/new-feature'
f674d9f Updated project readme
e236d9d (origin/ft/new-feature) Implemented core functionality for new feature
06458ca deleted files
d3f4b83 deleted
1014fdf added a readme file with the commands that answers the questions
61f4506 Implemented test 5
4f2faff Create Third File
8fc3091 chore: Create initial file

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git switch -c new-branch-from-commit e236d9d
Switched to a new branch 'new-branch-from-commit'
```

### Part 7

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (new-branch-from-commit)
$ git log --oneline
e236d9d (HEAD -> new-branch-from-commit, origin/ft/new-feature) Implemented core functionality for new feature
06458ca deleted files
d3f4b83 deleted
1014fdf added a readme file with the commands that answers the questions
61f4506 Implemented test 5
4f2faff Create Third File
8fc3091 chore: Create initial file

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (new-branch-from-commit)
$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git merge new-branch-from-commit
Already up to date.
```

### Part 8

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git switch new-branch-from-commit
Switched to branch 'new-branch-from-commit'

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (new-branch-from-commit)
$ git rebase main
Successfully rebased and updated refs/heads/new-branch-from-commit.
```

### Part 9

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git switch ft/improved-branch-name
Switched to branch 'ft/improved-branch-name'

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/improved-branch-name)
$ git status
On branch ft/improved-branch-name
nothing to commit, working tree clean

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/improved-branch-name)
$ git push
fatal: The current branch ft/improved-branch-name has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/improved-branch-name

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/improved-branch-name)
$ git push -u origin ft/improved-branch-name
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'ft/improved-branch-name' on GitHub by visiting:
remote:      https://github.com/mathewkenyi07/Git_Advance_Exercises/pull/new/ft/improved-branch-name
remote: 
To https://github.com/mathewkenyi07/Git_Advance_Exercises.git
 * [new branch]      ft/improved-branch-name -> ft/improved-branch-name
branch 'ft/improved-branch-name' set up to track 'origin/ft/improved-branch-name'.

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (ft/improved-branch-name)
$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git push
Everything up-to-date
```

### Part 10

```bash
MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git log --oneline
b31b9b3 (HEAD -> main, origin/main, origin/ft/improved-branch-name, ft/improved-branch-name) Merge branch 'ft/new-feature'
f674d9f Updated project readme
e236d9d (origin/ft/new-feature) Implemented core functionality for new feature
06458ca deleted files
d3f4b83 deleted
1014fdf added a readme file with the commands that answers the questions
61f4506 Implemented test 5
4f2faff Create Third File
8fc3091 chore: Create initial file

MATHEW@Matt MINGW64 ~/Desktop/Git Advance (main)
$ git switch --detach 61f4506 
HEAD is now at 61f4506 Implemented test 5
```








