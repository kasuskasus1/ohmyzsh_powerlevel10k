# oh_my_zsh + powerlevel10k installation script

This script is used to install ohmyzsh along with powerlevel10k in MacOS.

Make sure you have `curl` or `wget` and `git`.

1. Download and install [iTerm2](https://iterm2.com/downloads.html).
2. Install `homebrew`:
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
3. Install `zsh`:
```
brew install zsh
```
4. Make zsh a default shell:
```
chsh -s $(which zsh)
```
5. Install ohmyzsh:
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
6. Install `powerlevel10k` theme:
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```
7. Install `zsh-autosuggestions`:
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
8. Install `zsh-syntax-highlighting`:
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
9. Change `~/.zshrc` file using the following commands:
    - Changing enabled plugins:
        ```
        sed -i 's/^plugins=(.*/plugins=(git zsh-autosuggestions zsh-syntax-highlighting web-search golang sudo)/g' ~/.zshrc
        ```
    - Enabling `powerlevel10k` theme:
        ```
        sed -i 's/^ZSH_THEME.*/ZSH_THEME=powerlevel10k\/powerlevel10k//g' ~/.zshrc
        ```
10. Download and install a [Hack Nerd Font](https://github.com/ryanoasis/nerd-fonts/blob/master/patched-fonts/Hack/Regular/complete/Hack%20Regular%20Nerd%20Font%20Complete.ttf).
11. Set up profile in `iTerm2` settings in order to use `Hack Nerd Font`.
12. If you'd like to display some technical info on the right of the prompt line append the following lines to your `~/.zshrc' config file:
```
# General Settings
POWERLEVEL9K_MODE='nerdfont-complete'

# Battery
POWERLEVEL9K_BATTERY_LOW_BACKGROUND="clear"
POWERLEVEL9K_BATTERY_CHARGING_BACKGROUND="clear"
POWERLEVEL9K_BATTERY_CHARGED_BACKGROUND="clear"
POWERLEVEL9K_BATTERY_DISCONNECTED_BACKGROUND="black"
POWERLEVEL9K_BATTERY_LOW_FOREGROUND="249"
POWERLEVEL9K_BATTERY_CHARGING_FOREGROUND="249"
POWERLEVEL9K_BATTERY_CHARGED_FOREGROUND="249"
POWERLEVEL9K_BATTERY_DISCONNECTED_FOREGROUND="249"
POWERLEVEL9K_BATTERY_LOW_VISUAL_IDENTIFIER_COLOR="red"
POWERLEVEL9K_BATTERY_CHARGING_VISUAL_IDENTIFIER_COLOR="yellow"
POWERLEVEL9K_BATTERY_CHARGED_VISUAL_IDENTIFIER_COLOR="green"
POWERLEVEL9K_BATTERY_DISCONNECTED_VISUAL_IDENTIFIER_COLOR="249"

# Context
POWERLEVEL9K_CONTEXT_DEFAULT_BACKGROUND='028'
POWERLEVEL9K_STATUS_VERBOSE=false

# Dir
POWERLEVEL9K_SHORTEN_DIR_LENGTH=4
POWERLEVEL9K_SHORTEN_STRATEGY="truncate_middle"
POWERLEVEL9K_DIR_HOME_BACKGROUND="black"
POWERLEVEL9K_DIR_HOME_FOREGROUND="249"
POWERLEVEL9K_DIR_HOME_SUBFOLDER_BACKGROUND="055"
POWERLEVEL9K_DIR_HOME_SUBFOLDER_FOREGROUND="249"
POWERLEVEL9K_DIR_DEFAULT_BACKGROUND="black"
POWERLEVEL9K_DIR_DEFAULT_FOREGROUND="249"
POWERLEVEL9K_DIR_SHOW_WRITABLE="true"

#Load
POWERLEVEL9K_LOAD_CRITICAL_BACKGROUND="clear"
POWERLEVEL9K_LOAD_WARNING_BACKGROUND="clear"
POWERLEVEL9K_LOAD_NORMAL_BACKGROUND="clear"
POWERLEVEL9K_LOAD_CRITICAL_FOREGROUND="249"
POWERLEVEL9K_LOAD_WARNING_FOREGROUND="249"
POWERLEVEL9K_LOAD_NORMAL_FOREGROUND="249"
POWERLEVEL9K_LOAD_CRITICAL_VISUAL_IDENTIFIER_COLOR="red"
POWERLEVEL9K_LOAD_WARNING_VISUAL_IDENTIFIER_COLOR="yellow"
POWERLEVEL9K_LOAD_NORMAL_VISUAL_IDENTIFIER_COLOR="green"

# OS Icon
# POWERLEVEL9K_OS_ICON_BACKGROUND="028"
# POWERLEVEL9K_OS_ICON_FOREGROUND="255"

# RAM
POWERLEVEL9K_RAM_BACKGROUND="clear"
POWERLEVEL9K_RAM_FOREGROUND="249"
POWERLEVEL9K_RAM_ELEMENTS=(ram_free)

# Status
POWERLEVEL9K_STATUS_OK_BACKGROUND="black"
POWERLEVEL9K_STATUS_OK_FOREGROUND="green"
POWERLEVEL9K_STATUS_ERROR_BACKGROUND="black"
POWERLEVEL9K_STATUS_ERROR_FOREGROUND="red"

# Time
POWERLEVEL9K_TIME_FORMAT="%D{\uF017 %H:%M:%S" # \UF073 %m/%d/%Y}"
POWERLEVEL9K_TIME_BACKGROUND="clear"
POWERLEVEL9K_TIME_FOREGROUND="249"

# VCS
POWERLEVEL9K_SHOW_CHANGESET="true"
POWERLEVEL9K_VCS_GIT_HOOKS=(vcs-detect-changes git-untracked)

# Prompts Elements
# Visual customisation of the second prompt line
local user_symbol="$"
if [[ $(print -P "%#") =~ "#" ]]; then
    user_symbol = "#"
fi

#POWERLEVEL9K_PROMPT_ON_NEWLINE=true
#POWERLEVEL9K_PROMPT_ADD_NEWLINE=true
# POWERLEVEL9K_MULTILINE_FIRST_PROMPT_PREFIX="%{%F{249}%}\u250f"
POWERLEVEL9K_MULTILINE_FIRST_PROMPT_PREFIX="%F"
# POWERLEVEL9K_MULTILINE_LAST_PROMPT_PREFIX="%{%F{249}%}\u2517%{%F{default}%}❯ "
# POWERLEVEL9K_MULTILINE_LAST_PROMPT_PREFIX="%{%B%F{255}%K{245}%} $user_symbol%{%b%f%k%F{245}%} %{%f%}"
POWERLEVEL9K_MULTILINE_LAST_PROMPT_PREFIX="%{%B%F{255}%K{245}%} $user_symbol%{%b%f%k%F{245}%} %{%f%}"
POWERLEVEL9K_RPROMPT_ON_NEWLINE=true
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=('status' 'dir' 'vcs')
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=('command_execution_time' 'load' 'ram_joined' 'battery' 'time')
```
12. Restart iTerm2 & enjoy! 