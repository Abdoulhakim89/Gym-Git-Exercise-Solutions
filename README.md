# Git Basic exercises
## Bundle 1

### Exercise 1
```git
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises
$ git init
Initialized empty Git repository in C:/Users/User/OneDrive/Desktop/git-basic-exercises/.git/

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (master)
$ touch index.html

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (master)
$ git branch -m main

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git add .

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git commit -m 'initialized new local git repo'
[main (root-commit) 37068f1] initialized new local git repo
 2 files changed, 18 insertions(+)
 create mode 100644 README.md
 create mode 100644 index.html

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git remote add origin https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git push
fatal: The current branch main has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin main

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git push --set-upstream origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 493 bytes | 44.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git branch dev

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git switch dev
Switched to branch 'dev'

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git branch test

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git branch -d test
Deleted branch test (was 37068f1).
```
### Exercise 2
```git
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ touch home.html
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git stash
Saved working directory and index state WIP on dev: 37068f1 initialized new local git repo
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ touch about.html
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git stash
No local changes to save
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ touch team.html
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git add about.html
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git stash
Saved working directory and index state WIP on dev: 37068f1 initialized new local git repo
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git add home.html
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git stash
Saved working directory and index state WIP on dev: 37068f1 initialized new local git repo
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git add team.html
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git stash
Saved working directory and index state WIP on dev: 37068f1 initialized new local git repo
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git stash list
stash@{0}: WIP on dev: 37068f1 initialized new local git repo
stash@{1}: WIP on dev: 37068f1 initialized new local git repo
stash@{2}: WIP on dev: 37068f1 initialized new local git repo
stash@{3}: WIP on dev: 37068f1 initialized new local git repo
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git stash apply stash@{2}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git stash apply stash@{1}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   home.html
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git stash apply stash@{3}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   home.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git add .
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git commit -m 'stashed and popped about, home and restored the readme changes'
[dev 626df5e] stashed and popped about, home and restored the readme changes
 3 files changed, 85 insertions(+)
 create mode 100644 about.html
 create mode 100644 home.html
 User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git stash apply stash@{0}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git reset

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git reset --hard
HEAD is now at 626df5e stashed and popped about, home and restored the readme changes
```
## Bundle 2
### Exercise 1
```git
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git branch ft/bundle-2

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (dev)
$ git switch ft/bundle-2
Switched to branch 'ft/bundle-2'

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/bundle-2)
$ touch services.html

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/bundle-2)
$ git add .

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/bundle-2)
$ git commit -m 'Added a new feature in services.html'
[ft/bundle-2 a98094f] Added a new feature in services.html
 1 file changed, 17 insertions(+)
 create mode 100644 services.html

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/bundle-2)
$ git push
fatal: The current branch ft/bundle-2 has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/bundle-2

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/bundle-2)
$ git push --set-upstream origin ft/bundle-2
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 510 bytes | 127.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting:
remote:      https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions/pull/new/ft/bundle-2
remote:
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/bundle-2 -> ft/bundle-2
branch 'ft/bundle-2' set up to track 'origin/ft/bundle-2'.
```
### Exercise 2
```git

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git switch main
Already on 'main'
Your branch is up to date with 'origin/main'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git branch ft/services-redisign

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git switch ft/services-redisign
Switched to branch 'ft/services-redisign'

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redisign)
$ git branch -m ft/services-redesign

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redesign)
$ git add .

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redesign)
$ git commit -m 'Changes on services.html, new branch created'
[ft/services-redesign bba8ed2] Changes on services.html, new branch created
 1 file changed, 3 insertions(+), 2 deletions(-)

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redesign)
$ git push
fatal: The current branch ft/services-redesign has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/services-redesign

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redesign)
$  git push --set-upstream origin ft/services-redesign
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 374 bytes | 93.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/services-redesign' on GitHub by visiting:
remote:      https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions/pull/new/ft/services-redesign
remote:
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/services-redesign -> ft/services-redesign
branch 'ft/services-redesign' set up to track 'origin/ft/services-redesign'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redesign)
$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git add .

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ gi  commit -m 'Added changes on the main branch different to ft/services redesign'
bash: gi: command not found

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git  commit -m 'Added changes on the main branch different to ft/services redesign'
[main 1c160c3] Added changes on the main branch different to ft/services redesign
 1 file changed, 4 insertions(+), 2 deletions(-)

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 412 bytes | 103.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
   87c4952..1c160c3  main -> main

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git checkout ft/services-redesign
Switched to branch 'ft/services-redesign'
Your branch is up to date with 'origin/ft/services-redesign'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redesign)
$ git diff main
diff --git a/services.html b/services.html
index d54f4d9..dc01a6d 100644
--- a/services.html
+++ b/services.html
@@ -8,12 +8,11 @@
 <body>
     <h1>Our services</h1>
     <ul>
-        <li>Corporate monitoring</li>
+        <li>Civil Engeneering</li>
         <li>Business consultants</li>
-        <li>Employee training</li>
         <li>Car Rental</li>
-        <li>Auditing services</li>
-        <li>Online Degrees</li>
+        <li>Car wash</li>
+        <li>Barister training</li>
     </ul>
 </body>
 </html>
\ No newline at end of file

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redesign)
$ git merge main
Auto-merging services.html
CONFLICT (content): Merge conflict in services.html
Automatic merge failed; fix conflicts and then commit the result.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redesign|MERGING)
$ git add .

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redesign|MERGING)
$ git commit -m 'Resolved conflicts on ft/services-redesign; accepted incoming changes from main'
[ft/services-redesign ee9c563] Resolved conflicts on ft/services-redesign; accepted incoming changes from main

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/services-redesign)
$ git push
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 264 bytes | 132.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
   bba8ed2..ee9c563  ft/services-redesign -> ft/services-redesign

```