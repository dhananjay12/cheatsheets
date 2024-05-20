# Tmux

- `tmux` - start new
- `tmux new -s myname` - start new with session name
- `tmux a` - atach to the last session
- `tmux a -t myname` - attach to named session
- `tmux ls` - list sessions
- `tmux kill-session -t myname` - kill session
- `tmux ls | grep : | cut -d. -f1 | awk '{print substr($1, 0, length($1)-1)}' | xargs kill` - Kill all the tmux sessions
## Window management
- `ctrl+a c` - Create new window
- `ctrl+a ,` - rename current window
- `ctrl+a &` - close current window
- `ctrl+a n` - Move to next window
- `ctrl+a p` - Move to previous window
- `ctrl+a l` - Move to last window
- `ctrl+a 0-9` - Move to window by index number

## Session management
- `ctrl+a $` Rename session
- `ctrl+a s` from a tmux session and choose the session you want to jump in 
- `ctrl+a )` - Create new window
- `ctrl+a (` - Move to next window

## Split window into panes
- `ctrl+a |` - Vertical split (panes side by side)
- `ctrl+a -` - Horizontal split (one pane below the other)
- `ctrl+a arrow` - To move between panes
