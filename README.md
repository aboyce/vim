# Vim / Neovim

Notes and helper snippets whilst learning Vim/Neovim.

Additional helper for supporting tools:

- [tmux](./tmux.md)

## Normal Mode

### Movement

#### Basic

- `j`, `k`, `h`, `l` general movement

- `w` to hop forwards by a word
- `b` to hop backwards by a word
- `e` to hop forwards by a word, but to the end of the word
- `ge` to hop backward by a word, but to the end of the word

A word in vim only includes letters, numbers and digits. To consider special characters you need a WORD, to interact with these you use the capital version of the key:

- `W`
- `B`
- `E`
- `gE`

- `<relative line number> j` to jump down to that relative line number
- `<relative line number> k` to jump up to that relative line number

#### Jumping Horizontally

- `f` will enter 'find' mode, you can then type another letter to jump to it
  - `F` will do the same but backwards
- `t` will enter 'to' mode, you can then type another letter to jump to that letter
  - `T` will do the same but backwards

Rather than repeating the same `fa`, `fa` to keep jumping to the next one:

- `;` will jump to the next instance
- `,` will jump back to the previous instance

## Navigation

- `Ctrl` + `t` will go back when you have done something like gone to definition

## Windows

You can use `Ctrl` + `w` to access 'window mode'.

- `:new` will create a new horizontal window
- `:vnew` will create a new vertical window

## Yanking

- `y` will enter 'yank' mode
  - `y` will yank the current line
  - `j` will yank the current line plus one down
  - `w` will yank the word starting from the word and forward
  - `b` will yank the word starting from the word and backward
 
## Replacing

- `r` will allow you to replace a character, type `r` and then the new character you want to replace.

## Removing

- `x` will allow you to remove a single character.

## Pasting

- `p` will paste the line one line below
- `Shift` + `p` will paste the line one line above

## Yanking and Pasting with the Clipboard

To access the external clipboard you require a helper tool, you can see if it looks ok with:

```bash
:checkhealth
```

If the tooling is set up you can use:

- `"+y` to yank to the clipboard
- `"+p` to paste from the clipboard

## Deleting

- `d` will enter 'delete' mode
- `c` will enter 'delete' mode, but after the operation enter Insert mode

  - `d` will delete the current line, this is `c` if you have started deleting with `c`
  - `j` will delete the current line plus one down
  - `w` will delete the word starting from the word and forward (delete word)
  - `b` will delete the word starting from the word and backward (delete beginning)
  - `i` will start the 'delete inside' mode, waiting for input on what to delete around, e.g. `"`, `)`
  - `f` will start the 'delete find' mode, waiting for input on what to find to (look at _Jumping Horizontally_)
  - `t` will start the 'delete to' mode, waiting for input on what to delete to (look at _Jumping Horizontally_)

- `x` will delete a single character
- `s` will delete a single character and enter Insert mode

- `D` will delete the rest of the line
- `C` will delete the rest of the line and enter Insert mode
- `S` will delete the line and enter Insert mode

## Undo

- `u` will undo the last command
- `Ctrl` + `R` will redo
  - You can redo each undo
  - You can also undo n amount of changes with quantifiers, e.g. `4` + `Ctrl` + `r` will undo the last four changes.

## Insert Mode

- `i` will enter Insert Mode
- `a` will enter Insert Mode and also shift to the right
- `Shift` + `i` will enter Insert Mode at the beginning of the line
- `Shift` + `a` will enter Insert Mode at the end of the line
- `o` will enter Insert Mode and also add in an extra line
- `Shift` + `o` will enter Insert Mode and add in an extra line above

### In Insert Mode

- `Esc` will exit Insert Mode
- `Ctrl` + `c` will exit Insert Mode
- `Ctrl` + `[` will exit Insert Mode

## Visual (Line) Mode

- `v` will enter Visual Mode
- `Shift` + `v` will enter Visual Line Mode and highlight the whole line

### In Visual Mode

- `j` to move the highlight up
- `k` to move the highlight down
- `y` to yank the selection (add to register)
- `d` to delete the selection (add to register)
- `Esc` will exit Visual Mode

## Finding

- `*` will hop to the next instance of the word you are on
- `#` will hop to the previous instance of the word you are on

When you have used either `*` or `#`, you can then also use `n` and `Shift` + `n` to continue moving between them

Searching through the file, like a classic `Ctrl` + `f`:

- `/` will enter Command Mode, you can then type to search, press `Enter` to lock in the search
  - `n` will hop through the results
  - `Shift` + `n` will hop through the results in reverse

## Spelling

You can add words to you dictionary.

- `zg` will add the current word under the cursor to your dictionary.

## Help

- `:help` or `:h` will open the help guides
- `:help <topic>` will open the help guides for that `<topic>`
- `:helpgrep <term>` will open the help guides with a match on `<term>`
- `:options` will show every possible option, you can use `/` to then search

### Debugging Setup

Show health of everything:

```bash
:checkhealth
```

Or more specifically:

```bash
:checkhealth telescope
```

Show mappings:

- `:nmap`
- `:imap`
- `:vmap`

See the loaded scripts:

```bash
:scriptnames`
```

Reload the config:

```bash
:so %
```

## Plugins

### Coc

You can navigate auto-suggestions with:

- `Ctrl` + `n` to go to the next suggestion
- `Ctrl` + `p` to go to the previous suggestion
