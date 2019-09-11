## GIT CHEAT SHEET

### CLEAN

- Git remove branches that are not on local:

```
git checkout master
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
 