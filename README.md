## nvim-install
Script for automated installation of nvim and accompanying packages and modules
on **Arch** and/or **debian** based system.

## Installation
Clone this repo and run `./install` script. Following help will appear  on
screen:

```text
usage:
  install COMMAND

commands:
  neovim          - install latest neovim
  register        - register neovim in "alternatives""
  packages        - install other programs/modules (nodejs,
                    ruby, perl, pynvim, ruby nvim,  ...)

  all             - run all the above in single run

  clipboard       - install/select new clipboard tool 
                    even if one already installed
  node            - install/select new version of nodejs
                    even if one already installed


options:
  --select        - manualy select packages you want 
                    to install, for each group of
                    packages
  --node          - check for new versions of nodejs
                    online, even if one is installed
                    (does nothing on "arch" system)

  --clipbaoard    - offer selection of of clipboard
                    tool even if one is installed

note:
  command names can be abbrevated: neo, cli, pac, ...
```

Issue **install** with one of the given **"commands"**, and guided/automated
process will start.

### Note:
If run on existing installation, script will **update** already installed packages!


## Configuration
List of packages and modules to be installed, are given in file `packages`.
Content of the file can be freely edited, to include modules and packages
according to your needs.


## Prerequisites
This is **zsh** script, thus **zsh** shell must be present on the system. After
installation is done, **all** non system modules will be placed in following
directory:
```
$HOME/.local/share/neovim/bricks
```
To be able to use them, [**nvim-bricks**][1] plugin should be installed.


## Why and how
To speed up and automate installation of all necessary programs/modules this
script was created. Since **debian** based distros, have fairly old packages
(like **nodejs** and **nvim** itself), this script also allow download of latest
version from Internet. Latest version of **nvim** is automatically downloaded,
while **nodejs** version can be selected during installation process.
  

**Arch** on the other hand, already have fairly new versions of all packages,
thus there is no need to install external ones.

List of packages and modules to be installed, are given in file `packages`.
Content of the file can be freely edited, to include modules and packages
according to your needs. If not already on the system, some extra packages will
be also installed aside from listed ones, like ***gcc***, ***make***, ***cmake***
and similar.

System packages will be installed with system package manager into system
directories. On the other hand, **node**, **ruby**, **rust**, **python**,
**lua** and **perl** packages, will be installed into user directory:
```
$HOME/.local/share/neovim/bricks
```
with following structure:
```
bricks/
├── cargo
├── lua
├── node
├── perl5
├── python
└── ruby
```
To be able to use installed packages, [**nvim-bricks**][1] plugin should be used.
More about plugin can be found [**here**][1].


## Do I need these extra packages
To be able to use **LSP** and **DAP** language servers, some extra packages
have to be installed. Which one, depends on language/servers you are using.
If you don't use any, or the one you use do not depend on programs installed
with this script, you probably have no use from this script.

### Rust:
Packages: **fd-find** and **ripgrep** are needed by
[**telescope.nvim**][2] plugin,
if you don't use this plugin, you should not install this packages.

### Node:
On **Arch** system, **tree-sitter** installs  with **neovim**, thus you can
exclude **tree-sitter-cli** package


## Issues 
If you have any issues or comments, please be free to open an issue.


[1]:https://github.com/ksk0/nvim-bricks
[2]: https://github.com/nvim-telescope/telescope.nvim
