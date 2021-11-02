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

### COMMITS
* Commit on a previous date
```
git commit -am "readme" --date=yesterday
git commit -am "readme" --date=format:relative:13.hours.ago
```
