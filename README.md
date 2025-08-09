# 🛠 My Zsh Aliases

This is a curated collection of **Zsh aliases** to make command-line life faster, safer, and more fun.
They cover:

* 📂 Quick directory navigation
* 📄 Better file listing
* 🛠 Safer file management
* 🔄 Useful system utilities
* 🐙 Git shortcuts for speed
* 🧪 Conda & Python helpers
* ⚡ Fun extras to make the shell a little less boring

Drop these into your `~/.zshrc` and start enjoying fewer keystrokes and more productivity.

Alright — here’s your expanded **alias set fully commented** so it’s clear what each one does in your README or `.zshrc`.
This is drop-in ready, but the comments will also help future-you (or anyone reading your dotfiles) know exactly why each alias exists.

---

## 📂 Navigation & Directories

```sh
alias ..="cd .."                   # Go up one directory
alias ...="cd ../.."               # Go up two directories
alias ....="cd ../../.."           # Go up three directories
alias cd..="cd .."                 # For the typo-prone "cd.." instead of "cd .."
alias ~="cd ~"                     # Jump to home directory
alias home="cd ~"                  # Same as above, but with "home"
alias back="cd -"                  # Go back to previous directory
alias md="mkdir -pv"               # Create directory path recursively and print created dirs
alias rd="rmdir"                   # Remove an empty directory
alias tmp="cd /tmp"                # Jump to the system temporary directory
alias desk="cd ~/Desktop"          # Jump directly to Desktop
```

---

## 📄 Files & Listing

```sh
alias ls="ls --color=auto"          # Enable colored output for ls
alias ll="ls -lh"                   # Long list format, human-readable sizes
alias la="ls -A"                    # List all except . and ..
alias lla="ls -lAh"                 # Long list all including hidden files
alias lt="ls -ltrh"                 # Sort by modification time, newest last
alias lsize="ls -lhS"               # Sort by file size, largest first
alias df="df -h"                    # Show disk space in human-readable format
alias du="du -h -d 1"               # Show sizes of directories one level deep
alias tree="ls -R | grep ':$' | sed -e 's/:$//' -e 's/[^-][^\/]*\//--/g' -e 's/^/   /'"  # Simulate "tree" command without installing it
```

---

## 🛠 File Management

```sh
alias cp="cp -iv"                                   # Copy with confirmation before overwrite, verbose mode
alias mv="mv -iv"                                   # Move/rename with confirmation before overwrite, verbose
alias rm="rm -iv"                                   # Remove files with confirmation before delete, verbose
alias grep="grep --color=auto"                      # Highlight matches in grep output
alias egrep="egrep --color=auto"                    # Same for extended grep
alias fgrep="fgrep --color=auto"                    # Same for fixed-string grep
alias findd="find . -type d -name"                  # Search for directories by name
alias findf="find . -type f -name"                  # Search for files by name
alias cleanup="find . -type f -name '*~' -delete"   # Remove backup/temp files ending with ~
```

---

## 🔄 System & Utilities

```sh
alias path='echo $PATH | tr ":" "\n"'                  # Show $PATH entries line by line
alias reload="exec zsh"                                # Reload current shell session
alias hist="history"                                   # Show command history
alias histg="history | grep"                           # Search command history
alias please="sudo $(fc -ln -1)"                       # Rerun last command as sudo
alias update="sudo apt update && sudo apt upgrade -y"  # Update packages (Debian/Ubuntu)
alias serve="python3 -m http.server"                   # Start a simple HTTP server in current dir
alias untar="tar -xvf"                                 # Extract tar archives
alias targz="tar -czvf"                                # Create gzipped tar archives
alias ports="netstat -tulanp"                          # Show open ports and listening services
alias topmem="ps aux --sort=-%mem | head"              # Show top memory-consuming processes
alias topcpu="ps aux --sort=-%cpu | head"              # Show top CPU-consuming processes
```

---

## 🐙 Git

```sh
alias gs="git status"                           # Show current repo status
alias ga="git add"                              # Stage file(s)
alias gaa="git add --all"                       # Stage all changes
alias gb="git branch"                           # List branches
alias gc="git commit -v"                        # Commit with verbose message editing
alias gca="git commit -v --amend"               # Amend last commit
alias gco="git checkout"                        # Switch branches or restore files
alias gcm="git checkout main"                   # Switch to main branch
alias gp="git push"                             # Push to remote
alias gl="git log --oneline --graph --decorate" # Compact, visual git log
alias gd="git diff"                             # Show unstaged changes
alias gds="git diff --staged"                   # Show staged changes
alias gpl="git pull"                            # Pull latest changes
alias gundo="git reset --soft HEAD~1"           # Undo last commit but keep changes staged
```

---

## 🧪 Conda & Python

```sh
alias ca="conda activate"                  # Activate conda environment
alias cdect="conda deactivate"             # Deactivate conda environment
alias cls="conda list"                     # List packages in current env
alias ce="conda env list"                  # List all conda environments
alias crm="conda remove --name"            # Remove a conda environment (usage: crm envname --all)
alias py="python3"                         # Shortcut to Python 3
alias pipu="pip install --upgrade pip"     # Upgrade pip
alias pipi="pip install"                   # Install package
alias pipr="pip uninstall"                 # Remove package
```

---

## ⚡ Fun & Misc

```sh
alias please="sudo !!"                       # Re-run last command as sudo (bash-style)
alias weather="curl wttr.in"                 # Show local weather
alias weatherloc="curl wttr.in/London"       # Show weather for a specific location
alias myip="curl ifconfig.me"                # Show your public IP
alias clock="watch -n 1 date"                # Display real-time clock
alias joke="curl -s https://v2.jokeapi.dev/joke/Any?format=txt"  # Get a random joke
alias quote="curl -s https://api.quotable.io/random | jq -r '.content + \" — \" + .author'" # Get random quote
alias cowsay="cowsay hello"                  # ASCII cow says "hello" (needs cowsay)
alias matrix="cmatrix"                       # Matrix-style terminal animation (needs cmatrix)
```

---

## 🎁 Bonus

```sh
export EDITOR="code --wait"  # Set VS Code as default editor
export VISUAL="code --wait"  # Set VS Code as default visual editor
```

# 📝 Note
- `~/.zprofile` → Environment stuff that should load for all shells (PATH, exports).
- `~/.zshrc` → Your alias block, prompt config, shell options.
