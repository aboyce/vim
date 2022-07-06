# tmux

Notes and helper snippets whist learning tmux.

### Prefix Key

For the rest of this, `prefix` will be `Ctrl` + `b`.

### Sessions

- `tmux new` will create a new session and connect to it, you can provide a name with `-s<name>`
- `prefix d` will detach from the current session
- `tmux attach` will attach to the last connected session, you can provide a name with `-t<name>`

### Creating a new Window

- `Ctrl` + `b`

### Splitting the Window

A pane is created by splitting a window.

- `prefix %` splits the window vertically
- `prefix "` splits the window horizontaly

### Changing Windows

You can change between windows with:

- `prefix *` where `*` is a number between `0` and `9`
- `prefix n` will move to the next window by number
- `prefix p` will move to the previous window by number
- `prefix l` will move to the last window you where on

### Changing Panes

You can change between panes with:

- `prefix Up`, `prefix Up`, `prefix Up`, `prefix Up` will move between panes
- `prefix q` will show the numbers of each pane, you can then move to it with `prefix q *` where `*` is the number to move to
- `prefix o` will move to the next pane
- `prefix` `Ctrl + o` will swap the pane with the active pane
