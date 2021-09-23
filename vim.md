# vim-cheatsheet

## General
```bash
:help keyword # open help for keyword
:w            # write the buffer to the file (save)
:w file       # write buffer to specified file (save)
:o file       # open file
:q!           # quit the current window (force)
:wq           # write and quit
:qa           # quit all open tabs
:qa!          # quit all open tabs (force)
:wqa          # write and quit all open tabs
```

## Cursor movement
```bash
h        # move cursor left (left arrow)
j        # move cursor down (down arrow)
k        # move cursor up (up arrow)
l        # move cursor right (right arrow)
H        # move to top of screen
M        # move to middle of screen
L        # move to bottom of screen
w        # jump forwards to the start of a word
W        # jump forwards to the start of a word (words can contain punctuation)
e        # jump forwards to the end of a word
E        # jump forwards to the end of a word (words can contain punctuation)
b        # jump backwards to the start of a word
B        # jump backwards to the start of a word (words can contain punctuation)
0        # jump to the start of the line
^        # jump to the first non-blank character of the line
0w       # jump to the begining of the first word of indented lines
$        # jump to the end of the line
g_       # jump to the last non-blank character of the line
gg       # go to the first line of the document
G        # go to the last line of the document
5G       # go to line 5
fx       # jump to next occurrence of character x (use ; to find next)
tx       # jump to before next occurrence of character x (use ; to find next)
}        # jump to next paragraph (or function/block, when editing code)
{        # jump to previous paragraph (or function/block, when editing code)
)        # jump to next sentence
(        # jump to previous sentence
%        # jump to matching {[{
zz       # center cursor on screen
Ctrl + f # move forward one full screen
Ctrl + b # move back one full screen
Ctrl + d # move forward 1/2 a screen
Ctrl + u # move back 1/2 a screen
```

## Additional movement (motion) (to use in conjunction with comands)
```bash
iw      # inner word - applies the command to the word the cursor is on
is      # inner sentence - applies the command to the sentence the cursor is on
i"      # inner quotes - applies the command to the text inside the quotes
i[      # inner [] - applies the command to the text inside the [] the cursor is on
i{      # inner {} - applies the command to the text inside the {} the cursor is on
i(      # inner () - applies the command to the text inside the () the cursor is on
i<      # inner <> - applies the command to the text inside the <> the cursor is on
it      # inner tag - applies the command to the text inside the tags the cursor is on <tag>...</tag>
ip      # inner paragraph - applies the command to the text inside the paragraph

aw      # a word - same as iw
as      # a sentence - same as is
a"      # a quotes - same as i" including the quites
a[      # a [] - same as i[ including the []
a{      # a {} - same as i{ including the {}
a(      # a () - same as i( including the ()
a<      # a <> - same as i< including the <>
at      # a tag - same as it including the tags
ip      # inner paragraph - same as ip including the paragraph
```

## Insert mode - inserting/appending text
```bash
i        # insert before the cursor
I        # insert at the beginning of the line
a        # insert (append) after the cursor
A        # insert (append) at the end of the line
o        # append (open) a new line below the current line
O        # append (open) a new line above the current line
Esc      # exit insert mode
```

## Editing
```bash
r         # replace a single character
J         # join line below to the current one
cc        # change (replace) an entire line
c[motion] # change (replace) from the cursor to the move-to point.
dd        # delete an entire line
d[motion] # delete from the cursor to the move-to point.
s         # delete character and substitute text
S         # delete line and substitute text (same as cc)
xp        # transpose two letters (delete and paste)
.         # repeat last command
u         # undo
Ctrl + r  # redo
```

## Marking text (visual mode)
```bash
v        # start visual mode, mark lines, then do a command (like y-yank)
V        # start visual mode marking entire line
Ctrl + v # start visual block mode
o        # move to other end of marked area
O        # move to other corner of block
Esc      # exit visual mode
```

## Visual commands
```bash
y       # yank (copy) marked text
d       # delete marked text
c       # delete the marked text and go into insert mode (like c does above)
```

## Cut and paste
```bash
yy        # yank (copy) a line
y[motion] # yank (copy) from the cursor to the move-to point.
p         # put (paste) the clipboard after cursor
P         # put (paste) before cursor
dd        # delete (cut) a line
d[motion] # delete (cut) from the cursor to the move-to point.
D         # delete (cut) to the end of the line (same as d$)
x         # delete (cut) character
```

## Search and replace
```bash
/pattern       # search for pattern
?pattern       # search backward for pattern
\vpattern      # 'very magic' pattern: non-alphanumeric characters are interpreted as special regex symbols (no escaping needed)
n              # repeat search in same direction
N              # repeat search in opposite direction
:%s/old/new/g  # replace all old with new throughout file
:%s/old/new/gc # replace all old with new throughout file with confirmations
```

## Search in multiple files
```bash
:vimgrep /pattern/ {file} # search for pattern in multiple files
:vimgrep /pattern/ **/*   # example of recursive search
:cn                       # jump to the next match
:cp                       # jump to the previous match
:copen                    # open a window containing the list of matches
```

## Working with multiple files
```bash
:e file       # edit a file in a new buffer
:bnext or :bn # go to the next buffer
:bprev or :bp # go to the previous buffer
:bd           # delete a buffer (close a file)
:ls           # list all open buffers

:b <buffer name> # Display the first buffer matching the partial name (or press Tab for name completion).
```
**tip:** Enter `:ls` to list the buffers, then (while the list is still displayed), enter a command like `:b12` to display buffer 12 (no space is needed).

## Tabs
```bash
:tabnew or :tabnew file # open a file in a new tab
:tabe                   # same as tabnew
Ctrl + wT               # move the current split window into its own tab
gt or :tabnext or :tabn # move to the next tab
gT or :tabprev or :tabp # move to the previous tab
<number>gt              # move to tab <number>
:tabmove <number>       # move current tab to the <number>th position (indexed from 0)
:tabclose or :tabc      # close the current tab and all its windows
:tabonly or :tabo       # close all tabs except for the current one
:tabdo command          # run the command on all tabs (e.g. :tabdo q - closes all opened tabs)
```

## Windows
```bash
:sp file      # open a file in a new buffer and split window
:vsp file     # open a file in a new buffer and vertically split window
Ctrl + ws     # split window
Ctrl + ww     # switch windows
Ctrl + wq     # quit a window
Ctrl + wv     # split window vertically
Ctrl + wh     # move cursor to the left window (vertical split)
Ctrl + wl     # move cursor to the right window (vertical split)
Ctrl + wj     # move cursor to the window below (horizontal split)
Ctrl + wk     # move cursor to the window above (horizontal split)
Ctrl + wH     # move the current window to the left (vertical split)
Ctrl + wL     # move the current window to the right (vertical split)
Ctrl + wJ     # move the current window to the bottom (horizontal split)
Ctrl + wK     # move the current window to top (horizontal split)

{n}Ctrl + +    # Resize a slipt window (height) - {n} is the number of rows (1 by default)
{n}Ctrl + -    # Resize a slipt window (height) - {n} is the number of rows (1 by default)
{n}Ctrl + >    # Resize a slipt window (width) - {n} is the number of cols (1 by default)
{n}Ctrl + <    # Resize a slipt window (width) - {n} is the number of cols (1 by default)
```

## General tips
### Execute normal commands on the command line
_:normal [normal commands]_ allows to execute normal commands on command line
Example:
```bash
V6j                 # enter visual mode and select 6 lines down
:'<,'>normal 0i//   # execute the _0i_ normal mode command to insert '//' at the begining of all selected lines
```

### Auto completion
When in insert mode, while typing a word, press _Ctrl + p_ to autocomplete based on previous words and _Ctrl + n_ based on next words

_Ctrl + x Ctrl + f_ will help auto complete file names  
_Ctrl + x Ctrl + l_ will help auto complete based on lines

### Fuzzy Search
It is possible to fuzzy find your files using **/*, e.g.:
```bash
:vs **/*<partial file name><Tab>
```
This will search the current directory and all directories below it for filenames containing your partial search. This can be used with :e, :sp, :vsp.

### Highlight in substitution command
You can't: :s is a : command, not a search command, and highlighting can only be done on search commands.
But despair not!
/foo highlights stuff, then :s//bar replaces stuff using the last search string.
