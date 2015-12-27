# Configuring a remote for a fork

1. List the current configured remote repository for your fork.
```
$git remote -v
origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
```
1. Specify a new remote upstream repository that will be synced with the fork.
```
$git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git
```
1. Verify the new upstream repository you've specified for your fork.
```
$git remote -v
origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
upstream  https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (fetch)
upstream  https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (push)
```


# Syncing a fork
1. Change the current working directory to your local project.
1. Fetch the branches and their respective commits from the `upstream` repository. Commits to master will be stored in a local branch, `upstream/master`.
```
$git fetch upstream
remote: Counting objects: 75, done.
remote: Compressing objects: 100% (53/53), done.
remote: Total 62 (delta 27), reused 44 (delta 9)
Unpacking objects: 100% (62/62), done.
From https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY
 * [new branch]      master     -> upstream/master
```
1. Check out your fork's local `master` branch.
```
$git checkout master
Switched to branch 'master'
```
1. Merge the changes from `upstream/master` into your local `master` branch. This brings your fork's master branch into sync with the `upstream` repository, without losing your local changes.
```
$git merge upstream/master
```
