# ezsh
A simple script to setup an awesome shell environment.
Quickly install and setup zsh and oh-my-zsh (https://github.com/ohmyzsh/ohmyzsh/) with
* powerlevel10k theme (https://github.com/romkatv/powerlevel10k)
* Nerd-Fonts (https://github.com/ryanoasis/nerd-fonts)
* zsh-completions (https://github.com/zsh-users/zsh-completions)
* zsh-autosuggestions (https://github.com/zsh-users/zsh-autosuggestions)
* zsh-syntax-highlighting (https://github.com/zsh-users/zsh-syntax-highlighting)
* history-substring-search (https://github.com/zsh-users/zsh-history-substring-search)
* fzf (https://github.com/junegunn/fzf)
* k (https://github.com/supercrabtree/k)
* marker (https://github.com/pindexis/marker)
* todotxt (https://github.com/todotxt/todo.txt-cli)

Sets following useful aliases and ohmyzsh plugins. **You can add more or overwrite these in your personal zsh config files under `~/.config/ezsh/zshrc/`** 
* l="ls -lah"         - just type "l" instead of "ls -lah"
* alias k="k -h"	  - show human readable filesizes, in kb, mb etc
* e="exit"
* a='eza -la --git --colour-scale all -g --smart-group --icons always' - eza is the new ls
* myip - (wget -qO- https://wtfismyip.com/text)       - what's my ip: quickly find out external IP
* cheat - (https://github.com/chubin/cheat.sh)        - cheatsheets in the terminal!
* speedtest - (curl -s https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py | python3 -) run speedtest on the fly
* dadjoke - (curl https://icanhazdadjoke.com)         - terminally sick jokes
* ipgeo - (curl "http://api.db-ip.com/v2/free/$1")    - finds geo location from IP
* [x="extract"](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/extract)         - extract any compressed files
* [z](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/z)   - quickly jump to most visited directories
* [sudo](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/sudo)                - easily prefix your commands with sudo by pressing `esc` twice

## Demo

Command prompt looks like this (easily customize it by placing your configs in ~/.config/ezsh/zshrc/)
![prompt](https://github.com/user-attachments/assets/806e13b1-f22e-448c-be75-0df4b72352cf)
OS :  directory  :  git stats :           last command exit code & time taken : free RAM : time

Watch this to get an idea of what your Shell (life) could be like!

[![asciicast](https://asciinema.org/a/225226.svg)](https://asciinema.org/a/225226)


## Installation
Requirements:
* `git` to clone it.
* `python3` or `python` is required to run option '-c' which copies history from .bash_history

``` bash
git clone https://github.com/jotyGill/ezsh
cd ezsh
./install.sh -c        # only run with '-c' the first time, running multiple times will duplicate history entries
```
This will install the setup under `~/.config/ezsh/`
Change your terminal's fonts to either "RobotoMono Nerd Font" or "Hack Nerd Font" or "DejaVu Sans Mono Nerd Fonts".
You can also manually install Nerd Fonts of your choice.

## Notes
* Make sure to use any terminal besides QTerminal (default one in kali-xfce), here back space doesn't work for some reason (alt+back does). I recommend xfce4-terminal for Kali

* If you are already using zsh, your zsh config will be backed up to .zshrc-backup-date

* If the text/icons look broken, make sure your terminal is using one of the Nerd fonts. [discussion](https://github.com/powerline/fonts/issues/185). I recommend "RobotoMono Nerd Font"

* marker's shortcut "Ctr+t" clashed with fzf so I rebound it to "Ctr +b"

* All oh-my-zsh plugins are installed under ~/.config/ezsh/oh-my-zsh/plugin, Other tools (fzf,marker,todo) are installed in ~/.config/ezsh/

* If you use Marker, disable zsh-autosuggestions as it has a conflict with Marker (completion looks ugly). Add `plugins=(${plugins:#(zsh-autosuggestions)})` into your personal config file to remove it

* The look of the shell can be very easily customised[https://github.com/bhilburn/powerlevel9k#prompt-customization] by overwriting POWERLEVEL10K settings
in your personal config file under ~/.config/ezsh/zshrc/ . See example setup under example/personal_rc.zsh

Suggestions about more cool tools are always welcome :)

### To Uninstall
To uninstall simply delete ~/.zshrc and ~/.config/ezsh/. The script creates a backup of your original .zshrc in the home folder with the filename indicating it's a backup. Rename it back to .zshrc
