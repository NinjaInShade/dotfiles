# My dotfiles

This repo contains all the main dotfiles for my system that I would need if ever setting up again

## Requirements

Make sure to have the following installed:

### Git

```bash
sudo apt install git
```

### GNU stow (the magic)

```bash
sudo apt intall stow
```

## Installation

The setup process is very simple:

```bash
cd $HOME
git clone git@github.com:NinjaInShade/dotfiles.git
cd dotfiles
stow --adopt .
```

As most likely some dotfiles will already exist, this normally causes stow to terminate due to a conflict. To get around this, we pass the `--adopt` flag which tells stow to overwrite any conflicting files into our stow directory.

Due to this being a git repo however, you can just quickly check what changed with `git diff`. If the changes are important, you can just commit them and push, or if not, restore the repo back to it's original state.

Either way, the files have been correctly symlinked by stow and you're ready to go!

## Adding new configs

To add a new config file(s) to this repo:

1) Move the config file you want to add here but maintaining it's directory structure from your home directory. For example, adding `~/.config/kitty/kitty.conf` would require you to make `.config/kitty/kitty.conf` inside this directory.
2) Run `stow .` to create the new symlink
3) Commit and push to the repo! :D


