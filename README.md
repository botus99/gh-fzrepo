# 🚀 gh-fzrepo

<div align="right">
    <img src="https://img.shields.io/static/v1?label=Language&message=Shell&color=blue&style=flat-square"/>
    <img src="https://img.shields.io/static/v1?label=License&message=MIT&color=blue&style=flat-square"/>
</div>

An extension for [GitHub CLI](https://github.com/cli/cli) to browse repositories with fzf

## Demo on asciinema.org

> [https://asciinema.org/a/435075](https://asciinema.org/a/435075)

[![asciicast](https://asciinema.org/a/435075.svg)](https://asciinema.org/a/435075)

## Features

- [x] Quickly browse the README of each repository
- [x] Open URL of the repository in your default browser immediately

## Usage

```
gh-fzrepo -- An extension for GitHub CLI to browse repositories with fzf

USAGE
    gh-fzrepo KEYWORDS...
    gh-fzrepo -h|--help
    gh-fzrepo -v|--version
```

### Keybindings

| key | function |
|-----|----------|
| `Ctrl+J`, `Ctrl+N` | move focus down |
| `Ctrl+K`, `Ctrl+P` | move focus up |
| `Enter` | view README with `gh repo view` |
| `Ctrl+O` | open URL of the repository in your default browser | 
| `Esc`, `q` | quit fzf | 

## Installation

Dependences:

- [GitHub CLI](https://github.com/cli/cli) v2.0.0+
- [junegunn/fzf](https://github.com/junegunn/fzf)
- [charmbracelet/glow](https://github.com/charmbracelet/glow)

```bash
gh extension install botus99/gh-fzrepo
```

## One Liner Edition

```bash
query="..."; gh api "search/repositories?q=${query}" --jq ".items[].full_name" | fzf --preview "gh repo view {}" --bind "enter:execute(gh repo view {})" --bind "ctrl-o:execute(gh repo view -w {})"
```

## Contribution

Welcome!

