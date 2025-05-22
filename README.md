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
## Bundle 3

### Exercise 1
```git
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git branch ft/team-page

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main)
$ git switch ft/team-page
Switched to branch 'ft/team-page'

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/team-page)
$ touch team.html

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/team-page)
$ git add .

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/team-page)
$ git commit -m 'Created new branch & made changes to the team.html file'     
[ft/team-page 19555ea] Created new branch & made changes to the team.html file 1 file changed, 23 insertions(+), 15 deletions(-)

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/team-page)
$ git push
fatal: The current branch ft/team-page has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/team-page

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/team-page)
$ git push --set-upstream origin ft/team-page
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 537 bytes | 107.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/team-page' on GitHub by visiting:       
remote:      https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions/pull/new/ft/team-page
remote:
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/team-page -> ft/team-page
branch 'ft/team-page' set up to track 'origin/ft/team-page'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/team-page)
$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main) 
$ git branch ft/contact-page

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main) 
$ git switch ft/team-page
Switched to branch 'ft/team-page'
Your branch is up to date with 'origin/ft/team-page'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/team-page)
$ git log
commit 19555ea21df4207a35e9dacab3ed0cba82586e2c (HEAD -> ft/team-page, origin/ft/team-page)
Author: Abdulhakim <abdoulbeast89@gmail.com>
Date:   Wed May 21 10:47:18 2025 +0200

    Created new branch & made changes to the team.html file

commit 1a2893486da4b0c06dbd8ec55cbf64698892f78d (origin/main, main, ft/contact-page)
Author: Abdulhakim <abdoulbeast89@gmail.com>
Date:   Wed May 21 10:26:30 2025 +0200

    Added exercise 2 commands to the Readme file

commit 1c160c386048d1c9551008356f45d7aa225ff5b3
Author: Abdulhakim <abdoulbeast89@gmail.com>
Date:   Wed May 21 10:09:22 2025 +0200

    Added changes on the main branch different to ft/services redesign        

commit 87c495206848b905e49ed5b55392305aae8fbbce
Merge: 37068f1 6bb8921
Author: Abdoulhakim89 <abdoulbeast89@gmail.com>
Date:   Wed May 21 09:55:37 2025 +0200

    Merge pull request #2 from Abdoulhakim89/ft/bundle-2

    Ft/bundle 2

commit 6bb8921066a8da039daa71456c8842cdcbe3e2e4 (origin/ft/bundle-2)
Author: Abdulhakim <abdoulbeast89@gmail.com>
Date:   Mon May 19 15:20:42 2025 +0200

    added the terminal commands to the README file

commit a98094ffe23bbd4e0d2930d38ca4039dc2b17c83
Author: Abdulhakim <abdoulbeast89@gmail.com>
Date:   Mon May 19 15:11:33 2025 +0200

    Added a new feature in services.html

commit 612bb3ff485a2c06999e0183edbe2f7d973e6c42 (origin/dev, dev)
Author: Abdulhakim <abdoulbeast89@gmail.com>
Date:   Sat May 17 11:56:41 2025 +0200

    Wrapping up with the first bundle of exercises

commit 626df5efdffa4cded35fd708a3b74d6134543d5d
Author: Abdulhakim <abdoulbeast89@gmail.com>
Date:   Sat May 17 11:36:33 2025 +0200

    stashed and popped about, home and restored the readme changes

commit 37068f1f4c94da338b35f6e0689e6251516186fb
Author: Abdulhakim <abdoulbeast89@gmail.com>
Date:   Sat May 17 11:08:44 2025 +0200

    initialized new local git repo

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/team-page)
$ git checkout ft/contact-page
Switched to branch 'ft/contact-page'

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/contact-page)
$ git cherry-pick 19555ea21df4207a35e9dacab3ed0cba82586e2c
[ft/contact-page 9673f67] Created new branch & made changes to the team.html file
 Date: Wed May 21 10:47:18 2025 +0200
 1 file changed, 23 insertions(+), 15 deletions(-)

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/contact-page)
$ git add .

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/contact-page)
$ git commit -m 'Created the contact page and added some data after cherry pick'
[ft/contact-page 3bb7a1d] Created the contact page and added some data after cherry pick
 1 file changed, 5 insertions(+)

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/contact-page)
$ git push
fatal: The current branch ft/contact-page has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/contact-page

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/contact-page)
$ git push --set-upstream origin ft/contact-page
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 868 bytes | 144.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/contact-page' on GitHub by visiting:    
remote:      https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions/pull/new/ft/contact-page
remote:
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/contact-page -> ft/contact-page
branch 'ft/contact-page' set up to track 'origin/ft/contact-page'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/contact-page)
$ git branch ft/faq-page

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/contact-page)
$ git switch ft/faq-page
Switched to branch 'ft/faq-page'

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/faq-page)
$ touch faq.html

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/faq-page)
$ start faq.html

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/faq-page)
$ git add .

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/faq-page)
$ git commit -m 'Created the FAQ page and added some content'
[ft/faq-page 933358c] Created the FAQ page and added some content
 1 file changed, 14 insertions(+)
 create mode 100644 faq.html

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/faq-page)
$ git push
fatal: The current branch ft/faq-page has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/faq-page

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/faq-page)
$ git push --set-upstream origin ft/faq-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 521 bytes | 10.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:        
remote:      https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions/pull/new/ft/faq-page
remote:
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/faq-page -> ft/faq-page
branch 'ft/faq-page' set up to track 'origin/ft/faq-page'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/faq-page)
$ git revert 19555ea21df4207a35e9dacab3ed0cba82586e2c
Auto-merging team.html
CONFLICT (content): Merge conflict in team.html
error: could not revert 19555ea... Created new branch & made changes to the team.html file
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git revert --continue".
hint: You can instead skip this commit with "git revert --skip".
User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Deskt"git revert",op/git-basic-exercises (ft/faq-page|REVERTING)  
$ git commit -m 'reverted the changes on hash: 1ce.mergeConflict false"9555ea21df4207a35e9dacab3ed0cba82586e2c'        
[ft/faq-page cf78649] reverted the changes on haop/git-basic-exercises (ft/faq-page|REVERTING)sh: 19555ea21df4207a35e9dacab3ed0cba82586e2c    9555ea21df4207a35e9dacab3ed0cba82586e2c'
 1 file changed, 1 insertion(+), 1 deletion(-)  sh: 19555ea21df4207a35e9dacab3ed0cba82586e2c

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/faq-page)            op/git-basic-exercises (ft/faq-page)
$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 318 bytes | 63.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
   933358c..cf78649  ft/faq-page -> ft/faq-page
```
### Exercise 2
```git

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/f-page)
$ git branch ft/home-page-redesign

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/f-page)
$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main
$ git add .

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main
$ git commit -m 'Made changes to the team.html in main branch'
[main 71f2466] Made changes to the team.html in main branch
 1 file changed, 2 insertions(+), 1 deletion(-)

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main
$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 325 bytes | 108.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
   1d7c073..71f2466  main -> main

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (main
$ git switch ft/home-page-redesign
Switched to branch 'ft/home-page-redesign'

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/he-page-redesign)
$ git rebase main
Auto-merging team.html
CONFLICT (content): Merge conflict in team.html
error: could not apply 9673f67... Created new branch & made changes to the tm.html file
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebas
hint: Disable this message with "git config advice.mergeConflict false"
Could not apply 9673f67... Created new branch & made changes to the team.htm

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/h
$ git rebase --continue
fatal: no rebase in progress
page'
[ft/home-page-redesign 37de76c] added navigation to the home page
 1 file changed, 10 insertions(+)

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/home-page-redesign)
$ git
$ git push
fatal: The current branch ft/home-page-redesign has no upstream branch.     
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/home-page-redesign

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/home-page-redesign)
$ git push --set-upstream origin ft/home-page-redesign
Enumerating objects: 22, done.
Counting objects: 100% (22/22), done.
Delta compression using up to 4 threads
Compressing objects: 100% (18/18), done.
Writing objects: 100% (18/18), 4.20 KiB | 478.00 KiB/s, done.
Total 18 (delta 8), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (8/8), completed with 2 local objects.       
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions/pull/new/ft/home-page-redesign
remote:
To https://github.com/Abdoulhakim89/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/home-page-redesign -> ft/home-page-redesign
branch 'ft/home-page-redesign' set up to track 'origin/ft/home-page-redesign'.

User@ABDUL-HAKIM-MUHOZI MINGW64 ~/OneDrive/Desktop/git-basic-exercises (ft/home-page-redesign)
```