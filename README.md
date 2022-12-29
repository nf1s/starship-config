# Starship

My starship config

## Install

```
brew install starship
```

### Add config

```
git clone git@github.com:nf1s/starship-config.git $HOME/.config/starship/config.d
```

### Add config to zsh at the end

```
export STARSHIP_CONFIG="$HOME/.config/starship/config.d/starship.toml"
eval "$(starship init zsh)"
```

## Current config

```
format = """
$username\
$directory\
$git_branch\
$package\
$kubernetes\
$line_break\
$terraform\
$golang\
$python\
$character"""

add_newline = true

[username]
style_user = "green bold"
style_root = "black bold"
format = "[$user]($style) "
disabled = false
show_always = true

[directory]
truncate_to_repo = false
truncation_length = 2

[character]
success_symbol = "[➜](bold green) "
error_symbol = "[✗](bold red) "
vimcmd_symbol = "[ ](bold green)"

[kubernetes]
format = '[{$context}](bold white)'
disabled = false

[kubernetes.context_aliases]
"rancher-desktop" = "rancher"
"gke_.*_(?P<var_cluster>[\\w-]+)-cluster" = "$var_cluster"

[python]
symbol = "🐍 "
pyenv_version_name = true
format = '[${symbol}${pyenv_prefix}(${version} )(\($virtualenv\) )]($style)'
```
