# tmux

Notes and helper snippets whist learning tmux.

### Prefix Key

For the rest of this, `prefix` will be `Ctrl` + `b`.

### Sessions

- `tmux new` will create a new session and connect to it, you can provide a name with `-s <name>`
- `prefix d` will detach from the current session
- `tmux attach` will attach to the last connected session, you can provide a name with `-t <name>`

### Managing Windows

- `prefix c` creates a new window
- `prefix w` lists the windows
- `prefix f` finds a window
- `prefix ,` renames the current window
- `prefix &` kills the current window

### Changing between Windows

- `prefix *` where `*` is a number between `0` and `9`
- `prefix n` will move to the next window by number
- `prefix p` will move to the previous window by number
- `prefix l` will move to the last window you where on

### Managing Panes

A pane is created by splitting a window.

- `prefix %` splits the window vertically
- `prefix "` splits the window horizontaly

### Changing Panes

You can change between panes with:

- `prefix Up`, `prefix Left`, `prefix Right`, `prefix Down` will move between panes
- `prefix q` will show the numbers of each pane, you can then move to it with `prefix q *` where `*` is the number to move to
- `prefix o` will move to the next pane
- `prefix` `Ctrl + o` will swap the pane with the active pane

You can vertically and horizontally resize the panes with:

- `prefix Alt+1` to horizontally resize
- `prefix Alt+2` to vertically resize

### Custom Configuration

#### Reloading Configuration

Allow the configuration to be reloaded with `prefix r`.

```
bind r source-file ~/.config/tmux/tmux.conf
```

#### Vim Style Pane Movement

Use vim's `h`, `j`, `k`, `l` keys to control the pane movement.

```
bind h select-pane -L
bind j select-pane -D
bind k select-pane -U
bind l select-pane -R
```
