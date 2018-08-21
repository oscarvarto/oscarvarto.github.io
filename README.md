# Instructions for blogging

## Useful aliases

Add these to your `~/.zshrc` or equivalent:

```zsh
alias blog='make devserver'
alias blog-stop='./develop_server.sh stop'
alias blog-update='ghp-import -b master output'

alias gpush='git push origin master'
```

## Install dependencies (assuming Python 3.X)

### Texlive

`apt get install texlive-full`
(TODO: figure out a way to avoid the installation of `texlive-lang-*` packages)

### Zotero

From https://github.com/smathot/zotero_installer:

```zsh
sudo add-apt-repository ppa:smathot/cogscinl
sudo apt-get update
sudo apt-get install zotero-standalone
```

## Repositories and dependencies needed

1. Clone pelican-themes from `git@github.com:getpelican/pelican-themes.git` in a folder at the same (folder) level than this repo.
2. `danielfrg/pelican-ipynb.git` is cloned at commit `292d29a` inside `plugins/ipynb`.

oscarvarto.github.io should be cloned with the `--recursive` flag:
`git clone git@github.com:oscarvarto/oscarvarto.github.io.git --recursive`

or in three steps:

```zsh
git clone git@github.com:oscarvarto/oscarvarto.github.io.git
cd oscarvarto.github.io
git submodule update --init --recursive
```

## Blog development environment with `conda`

```zsh
conda env create -f environment.yml
conda activate blog
blog &
jupyter-notebook content &
```

Just to make sure I have an exact copy of the environment available if necessary, I also exported my current conda environment with `conda env export > environment-2018-08-21.yml` and included it in the blog repository.