## Basic Keys

| Keys      | Description |
| :----:        |    :----:   |
|  Cmd + Shift + . | Show hidden files | 
|  Cmd + ` | Switch between same windows | 
|  Cmd + z | Revert Back | 
|  Cmd + Shift + z  | Revert Back Forward |

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
```
Then run `source ~/.zshenv`

## IntelliJ

### Debug

| Keys      | Description |
| :----:        |    :----:   | 
| Option+F8  | Evaluate expression | 
| Option + Ctrl + H  | See call hierarchy | 
| Cmd + F  | Find | 
| Cmd + R  | Replace | 
