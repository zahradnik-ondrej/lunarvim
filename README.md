<div align="center">

# 🌙 lunarvim

### 

*(The instructions below have been made to work on **Linux** operating systems, specifically on **Ubuntu 22.04** along with the prerequisite of having **curl** installed on your system.)*

</div>

***

### [Neovim](https://github.com/neovim/neovim/blob/master/INSTALL.md#pre-built-archives-2)

1. `curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim-linux64.tar.gz`
2. `sudo rm -rf /opt/nvim`
3. `sudo tar -C /opt -xzf nvim-linux64.tar.gz`
4. `echo 'export PATH="$PATH:/opt/nvim-linux64/bin"' >> ~/.bashrc`

### [Rust and Cargo](https://doc.rust-lang.org/cargo/getting-started/installation.html#install-rust-and-cargo)

1. `curl -sSf https://sh.rustup.rs | sh`
2. `source "$HOME/.bashrc"`

### [LunarVim](https://www.lunarvim.org/docs/installation#release)

1. `LV_BRANCH="master" bash <(curl -s https://raw.githubusercontent.com/LunarVim/LunarVim/master/utils/installer/install.sh) <<< $'n\ny'`

### [Hack Nerd Font](https://www.nerdfonts.com/font-downloads)

1. `mkdir -p ~/.local/share/fonts`
2. `curl -Lo ~/Hack.zip https://github.com/ryanoasis/nerd-fonts/releases/latest/download/Hack.zip`
3. `unzip -oq ~/Hack.zip -d ~/.local/share/fonts`
4. `rm -f ~/Hack.zip`
5. `fc-cache -f`
