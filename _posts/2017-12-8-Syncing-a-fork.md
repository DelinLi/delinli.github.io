## Syncing a fork

From [githb]("https://help.github.com/articles/syncing-a-fork/")

1. Fetch the branches and their respective commits from the upstream repository. Commits to master will be stored in a local branch, upstream/master.
<pre>
git fetch upstream
</pre>

2. Check out local master branch of your fork.
<pre>
git checkout master
</pre>

3. Merge the changes from upstream/master into your local master branch. This brings your fork's master branch into sync with the upstream repository, without losing your local changes.
<pre>
git merge upstream/master
</pre>
