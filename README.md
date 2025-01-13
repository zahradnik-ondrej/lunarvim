<div align="center">

# 🌙 lunarvim

### 

*(The instructions below have been made to work on **Linux** operating systems, specifically on **Ubuntu 22.04** along with the prerequisite of having **pip3** installed on your system.)*

</div>

***

### [Cheatsheet](https://github.com/zahradnik-ondrej/dotfiles/blob/main/.config/lvim/lunarvim_cheatsheet.md)

***

### [Neovim](https://github.com/neovim/neovim/blob/master/INSTALL.md#pre-built-archives-2)

1. `wget https://github.com/neovim/neovim/releases/latest/download/nvim-linux64.tar.gz`
2. `sudo rm -rf /opt/nvim`
3. `sudo tar -C /opt -xzf nvim-linux64.tar.gz`
4. `echo 'export PATH="$PATH:/opt/nvim-linux64/bin"' >> ~/.bashrc`
``` bash
export PATH=$PATH:/opt/nvim-linux64/bin
```

### [Rust and Cargo](https://doc.rust-lang.org/cargo/getting-started/installation.html#install-rust-and-cargo)

1. `wget -qO- https://sh.rustup.rs | sh`
2. `source "$HOME/.bashrc"`

### [LunarVim](https://www.lunarvim.org/docs/installation#release)

1. `LV_BRANCH="master" bash <(wget -qO- https://raw.githubusercontent.com/LunarVim/LunarVim/master/utils/installer/install.sh) <<< $'n\ny'`

### [neovim-remote](https://github.com/mhinz/neovim-remote?tab=readme-ov-file#installation)

1. `pip3 install neovim-remote`
2. `echo -e "\nif [ -f ~/.bash_aliases ]; then\n\t. ~/.bash_aliases\nfi" >> ~/.bashrc`  
``` bash
if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi
```
3. `echo 'export NVIM_LISTEN_ADDRESS="/tmp/lvim_server"' >> ~/.bashrc`  
``` bash
export NVIM_LISTEN_ADDRESS="/tmp/lvim_server"
```
4. `echo -e "\n# lunarvim\nlvim_open() {\n  if command -v nvr >/dev/null 2>&1 && [[ -n \"$NVIM_LISTEN_ADDRESS\" ]]; then\n    nvr -s --nostart --remote-tab \"$@\" || lvim \"$@\"\n  else\n    lvim \"$@\"\n  fi\n}" >> ~/.bash_aliases`
``` bash
# lunarvim
lvim_open() {
  if command -v nvr >/dev/null 2>&1 && [[ -n "$NVIM_LISTEN_ADDRESS" ]]; then
    nvr -s --nostart --remote-tab "$@" || lvim "$@"
  else
    lvim "$@"
  fi
}
```
5. `echo -e "\nalias nvim=\"/opt/nvim-linux64/bin/nvim\"\nalias lvim=\"lvim\"\nalias lv=\"lvim_open\"" >> ~/.bash_aliases`
``` bash
alias nvim='/opt/nvim-linux64/bin/nvim'
alias lvim='lvim'
alias lv='lvim_open'
```

### [Hack Nerd Font](https://www.nerdfonts.com/font-downloads)

1. `mkdir -p ~/.local/share/fonts`
2. `wget -qO ~/Hack.zip https://github.com/ryanoasis/nerd-fonts/releases/latest/download/Hack.zip`
3. `unzip -oq ~/Hack.zip -d ~/.local/share/fonts`
4. `rm -f ~/Hack.zip`
5. `fc-cache -f`
