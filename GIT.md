## GIT CHEAT SHEET

### CLEAN

* Git remove branches that are not in remote:

```
git checkout master
git branch --merged master | grep -v '^[ *]*master$' | xargs git branch -d
```
  or
```
git fetch -p && git branch -vv | awk '/: gone]/{print $1}' | xargs git branch -d
```
 
 * Remove untracked files
 ```
 git clean -df
 ```
 
 * Clean files that are in `.gitignore`
    * First perform a dry run and see what will be removed.
      ```
      git clean -xdn
      ```
    * Execute it
      ```
      git clean -xdf
      ```

### TAGS

* Delete tag

Delete local tag 'abcd'
```
git tag -d abcd
``` 

Delete remote tag 'abcd' 
```
git push origin :refs/tags/abcd
```

* Add tag
```
git tag mytag
git push --tags
```

* Checkout on a Tag 
```
git fetch --tags

git checkout tags/mytag
```

* Create a branch out of tag
```
git checkout -b <branch-name> v1.0
```

### COMMITS
* Commit on a previous date
```
git commit -am "readme" --date=yesterday
git commit -am "readme" --date=format:relative:13.hours.ago
```

### Cherry Pick
If you want a commit something your branch from another commit (because you cannot merge another branch to yours. Also, doesnt matter when it was made, past/future wr.t your branch).

To your branch run
```
git cherry-pick <commit-id>
```
If there are no conflicts it will merge it, else you have to resolve the conflicts. Also, note that it will do nothing if the commit is already in your branch, so double check which branch you are cherry picking to.



