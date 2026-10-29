# Terminal Customization
## Setting
for bash:
```bash
nano ~/.bash_profile

# copy the configuration and add to shell startup file.

#reload file
source ~/.bash_profile
```
for zsh:
```zsh
nano ~/.zshrc
# copy the configuration and add to shell startup file.

#reload file
source ~/.zshrc
```

## configs
![config1](pics/config1.png)
```bash
export VIRTUAL_ENV_DISABLE_PROMPT=1
PS1='\[\e[38;5;183m\]${VIRTUAL_ENV:+(${VIRTUAL_ENV##*/})}\[\e[0m\]\[\e[38;5;211m\]\u\[\e[0m\]\[\e[38;5;211m\]@\[\e[0m\]\[\e[38;5;211m\]\h\[\e[0m\]\[\e[38;5;211m\]:\[\e[0m\]\[\e[38;5;141m\]\w\[\e[0m\]\[\e[38;5;141m\]\$\[\e[0m\] '
```
![config2](pics/config2.png)
```bash
export VIRTUAL_ENV_DISABLE_PROMPT=1
PS1='\[\e[38;5;218m\]${VIRTUAL_ENV:+(${VIRTUAL_ENV##*/})}\[\e[0m\]\[\e[38;5;141m\]\u\[\e[0m\]\[\e[38;5;141m\]@\[\e[0m\]\[\e[38;5;141m\]\h\[\e[0m\]\[\e[38;5;141m\]:\[\e[0m\]\[\e[38;5;211m\]\w\[\e[0m\]\[\e[38;5;211m\]\$\[\e[0m\] '
```
![config3](pics/config3.png)
```bash
export VIRTUAL_ENV_DISABLE_PROMPT=1
PS1='\[\e[38;5;211m\]${VIRTUAL_ENV:+(${VIRTUAL_ENV##*/})}\[\e[0m\]\[\e[38;5;141m\]\u\[\e[0m\]\[\e[38;5;141m\]@\[\e[0m\]\[\e[38;5;141m\]\h\[\e[0m\]\[\e[38;5;141m\]:\[\e[0m\]\[\e[38;5;218m\]\w\[\e[0m\]\[\e[38;5;218m\]\$\[\e[0m\] '
```