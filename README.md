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

```