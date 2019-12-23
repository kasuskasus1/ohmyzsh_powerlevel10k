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
12. Restart iTerm2 & enjoy! 