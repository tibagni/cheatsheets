# tmux-cheatsheet

## Sessions
```bash
# Start a new session unnamed
$tmux
$tmux new
$tmux new-session

# Start a new session with a name
$tmux new -s session_name

# Kill sessions
$tmux kill-session -t session_name    # Kill a session by name
$tmux kill-session -a                 # Kill all sessions
$tmux kill-session -a -t session_name # Kill all sessions except session_name

# List sessions
$tmux ls

# Attach to the last session
$tmux a

# Attach to a specific session
$tmux a -t session_name

# Key Bindings
(Ctrl + b) d       # Detach from current session
```

## Windows
```bash
# These are key bindings for when you are in a session

(Ctrl + b) c       # Create a new window
(Ctrl + b) ,       # Rename current window
(Ctrl + b) &       # Close current window (you can also just exit)
(Ctrl + b) p       # Go to previous window
(Ctrl + b) n       # Go to next window
(Ctrl + b) [0...9] # Select window by number
```

## Panes
```bash
# These are key bindings for when you are in a session

(Ctrl + b) %             # Split pane vertically
(Ctrl + b) "             # Split pane horizontally
(Ctrl + b) {left-arrow}  # Switch to pane on the left
(Ctrl + b) {right-arrow} # Switch to pane on the right
(Ctrl + b) {up-arrow}    # Switch to pane above
(Ctrl + b) {down-arrow}  # Switch to pane below
(Ctrl + b) q             # Show pane numbers
(Ctrl + b) q [0...9]     # Select pane by number

# Resize current pane
(Ctrl + b) Ctrl + {up-arrow}
(Ctrl + b) Ctrl + {down-arrow}
(Ctrl + b) Ctrl + {left-arrow}
(Ctrl + b) Ctrl + {left-arrow}
```

## Copy mode
```bash
# These are key bindings for when you are in a session

(Ctrl + b) [             # Enter copy mode
# use VIM key bindings for movement and search while in copy mode
spacebar                 # Start selection
enter                    # Copy selection
(Ctrl + b) ]             # Paste contents of buffer_0
```

## Nested sessions
it’s ok to SSH to a remote host and start the tmux session there, while already being in a tmux environment locally.
This is called nested sessions, but how you can control inner sessions, since all keybindings are caught and handled by outer sessions?

Simple press prefix twice. The first prefix keystroke is caught by the outer session, whereas second is passed to the inner session.
For example, move to the next window from inner session is `(Ctrl + b) (Ctrl + b) n`

## Help
```bash
(Ctrl + b) ? # Show all shortcuts
```
