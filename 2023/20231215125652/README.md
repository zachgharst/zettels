# tmux windows and vim splits

I'm finally getting comfy with these. Here's some of my most used commands/keybinds:

## tmux

All tmux commands are entered with a prefix - by default, this is `ctrl+b`. Many people, including myself, have rebound this to `ctrl+a`.

- `<prefix>c`: Create window.
- `<prefix>&`: Close window.
- `<prefix>w`: List windows and select.
- `<prefix>,`: Rename current window.
- `<prefix>.`: Move current window to a new index.
- `<prefix>0-9`: Focus window with that index.
- `<prefix>:`: Enter command mode.
  - `:movew -r`: Renumber all existing windows from 1-n -- this is helpful to get rid of gaps.

Some day I will explore tmux panes again. But until then...

## vim

### Commands

Start a split with `:sp` (horizontal split) or `:vsp` (vertical split).
Optionally, pass in a filename: `:sp filename`.

`ctrl+w` is the prefix for all split manipulation:

- `ctrl+w (v|s)`: Create a new vertical/horizontal split.
- `ctrl+w c`: Close the current split (or, `:q`).
- `ctrl+w o`: Close every split except the current one
- `ctrl+w w`: Focus the next split (also `ctrl+w ctrl+w`).
- `ctrl+w T`: Break split into a tab. 
- `ctrl+w (h|j|k|l)`: Focus a different pane in a certain direction.
- `ctrl+w (H|J|K|L)`: Move the focused split to the left/top/bottom/right.
- `ctrl+w R`: Swap the location of two splits.
- `ctrl+w [n](+|-|<|>)`: Increase/decrease the height/width - optionally use a number. 
- `ctrl+w =`: Make all splits equal in height/width.

### Config

- `splitbelow` and `splitright`: These make new splits happen to the bottom and
  to the right rather than the default (top or left).
