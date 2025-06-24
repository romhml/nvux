# nvux

Open files in existing neovim instance within tmux. This script is primarily made to be set as your `EDITOR` or `LAUNCH_EDITOR` environment variable to integrate with tools that spawn editors.

## Installation
```bash
curl -o nvux https://raw.githubusercontent.com/romhml/nvux/main/nvux
chmod +x nvux
sudo mv nvux /usr/local/bin/
```

## Usage

```
USAGE:
    nvux [OPTIONS] [FILE] [+LINE]

OPTIONS:
    -h, --help        Show this help message and exit

ARGUMENTS:
    FILE              Path to file to open (optional)
    +LINE             Line number to jump to after opening file (optional)
                      Must be preceded by '+' (e.g., +42)

DESCRIPTION:
    nvux opens files in an existing Neovim instance running
    within a tmux session. It searches for active Neovim processes in the
    current tmux session and opens the specified file in that instance.

    If no existing Neovim instance is found, nvux will create one in a new pane.
    When not running within a tmux session, nvux falls back to launching
    regular Neovim.

EXAMPLES:
    nvux                          # Open nvim in existing tmux instance
    nvux file.txt                 # Open file.txt
    nvux file.txt +25             # Open file.txt and jump to line 25
    nvux /path/to/script.sh +1    # Open script.sh and jump to first line
```

