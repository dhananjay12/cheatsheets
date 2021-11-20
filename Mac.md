## Basic Keys

| Keys      | Description |
| :----:        |    :----:   |
|  Cmd + Shift + . | Show hidden files | 
|  Cmd + ` | Switch between same windows | 
|  Cmd + z | Revert Back | 
|  Cmd + Shift + z  | Revert Back Forward |
|  Cmd + Ctrl + F  | Full Screen or Revert full screen |

## Terminal

| Keys      | Description |
| :----:        |    :----:   |
|  Cmd + k | Clear the terminal fully. (`clear` just brings the terminal down) |

### Terminal commands

`history -c` Cleard the Current Session’s History

`/usr/libexec/java_home` returns the location of the default JDK.

`/usr/libexec/java_home -V` finds all installed JDKs.

`/usr/libexec/java_home -v17` to use below

Set Java_home

Check - `echo $JAVA_HOME`

Open the ~/.zshenv or ~/.zshrc. Add the following content:
```
export JAVA_HOME=$(/usr/libexec/java_home)

alias j8="export JAVA_HOME=`/usr/libexec/java_home -v 1.8`; java -version"
alias j11="export JAVA_HOME=`/usr/libexec/java_home -v 11`; java -version"
alias j17="export JAVA_HOME=`/usr/libexec/java_home -v 17`; java -version"
```
Then run `source ~/.zshenv`

Now you can use these alias to change your java version.

## IntelliJ

### Debug

https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings

