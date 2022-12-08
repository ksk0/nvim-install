## nvim-install
Script for automated installation of nvim and accompanying packages and modules
on **Arch** and/or **debian** based system.

## Installation and usage
Clone this repo and run `./install` script. Following help will appear  on
screen:

```
usage:
   install SELECTION

selection:
   neovim     - install latest neovim
   clipboard  - install clipboard interface utility
   packages   - install packages/modules (nodejs, ruby,
                perl, pynvim, ruby nvim, rust, ...)

   all        - run all the above in single run

note:
   command names can be abbreviated: neo, cli, ...
```

Issue **install** with one of the given **"selections"**, and guided/automated
process will start.


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

**Rust** packages: **fd-find** and **ripgrep** are needed by
[**telescope.nvim**][2] plugin,
if you don't use this plugin, you should not install this packages.

## Issues 
If you have any issues or comments, please be free to open an issue.


[1]:https://github.com/ksk0/nvim-bricks
[2]: https://github.com/nvim-telescope/telescope.nvim
