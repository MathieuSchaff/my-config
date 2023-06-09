# My Linux Configuration

This readme contains instructions on setting up my preferred Linux configuration, including the tools and packages I use.

## Neovim

Neovim is a highly configurable text editor that I use for programming and editing text files. I prefer installing it from source, following the steps outlined on these GitHub repositories:

- [Installing Neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim#install-from-source)
- [Building Neovim](https://github.com/neovim/neovim/wiki/Building-Neovim)

### Build Prerequisites

1. General Requirements

- Clang or GCC version 4.9+ (test clang --version or gcc --version)
- CMake version 3.10+, built with TLS/SSL support
  - Optional: Get the latest CMake from an installer or the Python package (`pip install cmake`)

2. Ubuntu / Debian / Tuxedo

```sh
sudo apt-get install ninja-build gettext cmake unzip curl
```

Or

```sh
cd ~ && \
sudo apt install -y ninja-build gettext libtool libtool-bin autoconf python3-dev \
automake cmake g++ pkg-config doxygen libicu-dev libboost-all-dev libssl-dev \
ripgrep fd-find silversearcher-ag mlocate zoxide python3-pip libsqlite3-dev bat
```

### Clone Neovim repository

```sh
git clone -b release-0.8 https://github.com/neovim/neovim ~/Documents/Mathieu/Apps/Neovim
```

make CMAKE_BUILD_TYPE=RelWithDebInfo CMAKE_EXTRA_FLAGS="-DCMAKE_INSTALL_PREFIX=$HOME/Documents/Mathieu/Apps/neovim"

```sh
make CMAKE_BUILD_TYPE=RelWithDebInfo CMAKE_EXTRA_FLAGS="-DCMAKE_INSTALL_PREFIX=$HOME/Mathieu/Apps/neovim"
```

When you provide a custom installation prefix using the CMAKE_INSTALL_PREFIX variable, Neovim will be installed in the specified directory instead of the default system location, which is /usr/local for Unix-like systems.

For example, when you use this command above Neovim will be installed in $HOME/Documents/Mathieu/Apps/neovim, rather than /usr/local.

This can help you keep your system organized and simplify the uninstallation process. However, you will need to add the custom installation location to your PATH environment variable to use Neovim from the command line:

```sh
export PATH="$HOME//Mathieu/Apps/neovim/bin:$PATH"

```

---

#### NEOVIM - config

1. PYNVIM - install

https://github.com/neovim/pynvim
We need it for some Neovim's plugins.

```sh
cd ~ && \
pip3 install pynvim
```

#### HACK FONT - install

Go to https://www.nerdfonts.com/font-downloads to check if link is the lastest release version !
https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/Hack

```sh
wget -P ~/Mathieu/Downloads https://github.com/ryanoasis/nerd-fonts/releases/download/v2.2.2/Hack.zip && \
cd ~/.local/share && \
mkdir fonts && \
cd fonts && \
mv ~/Mathieu/Downloads/Hack.zip . && \
unzip Hack.zip && \
rm -rf Hack.zip
```
