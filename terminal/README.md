# Terminal Prompt Customization

Terminal prompts can be customized using ANSI escape sequences to control text colors, alongside shell-specific variables to display information such as the username, hostname, working directory, and active Python virtual environment.


## Themes

**[MI77 Terminal Studio](https://mirabelleding.github.io/MI77-Themes/terminal/studio/)**

An interactive tool for configuring Bash prompts with customizable colors, live previews, and ready-to-use shell configurations.


## Applying the Configuration

Add the configuration to the appropriate shell initialization file:
| Environment | Configuration file |
|---|---|
| macOS Bash | `~/.bash_profile` |
| Linux / WSL Bash | `~/.bashrc` |

```bash
nano <config_file>
```
Reload configuration file:

```bash
source <config_file>
```
**Place the custom prompt configuration after any existing prompt definitions to avoid having it overwritten.*

## Color Formats

Bash supports several ANSI color formats:

| Format | Syntax | Example |
|---|---|---|
| ANSI 16-color | `\e[35m` | Basic purple |
| ANSI 256-color | `\e[38;5;218m` | Pink |
| RGB / True Color | `\e[38;2;215;175;255m` | Custom lavender |

**ANSI 256-color** uses a fixed palette of 256 indexed colors, while **RGB (True Color)** supports approximately 16.7 million colors.

Actual color rendering depends on the terminal's palette and display settings.

## Bash Prompt Variables

Bash provides special escape sequences for displaying dynamic information within the shell prompt.

| Variable | Description |
|---|---|
| `\u` | Current username |
| `\h` | Short hostname |
| `\H` | Full hostname |
| `\w` | Working directory, abbreviated with `~` |
| `\W` | Current directory name |
| `\$` | `$` for regular users, `#` for root |
| `\n` | Newline |
| `\t` | Current time in 24-hour format |

These can be combined through the `PS1` variable:

```bash
PS1='\u@\h:\w\$ '
```

For example:

```text
username@hostname:~/projects/repository$
```

## Customizing Individual Colors

Each component of the prompt can have its own color. Use RGB escape sequences to set a foreground color and `\e[0m` to reset formatting.

The following configuration assigns separate colors to the virtual environment, username, `@` symbol, hostname, `:` separator, working directory, and `$` symbol.

```bash
export VIRTUAL_ENV_DISABLE_PROMPT=1

PS1='\[\e[38;2;215;175;255m\]${VIRTUAL_ENV:+(${VIRTUAL_ENV##*/})}\[\e[0m\]'
PS1+='\[\e[38;2;135;215;135m\]\u\[\e[0m\]'
PS1+='\[\e[38;2;238;238;238m\]@\[\e[0m\]'
PS1+='\[\e[38;2;135;215;255m\]\h\[\e[0m\]'
PS1+='\[\e[38;2;238;238;238m\]:\[\e[0m\]'
PS1+='\[\e[38;2;255;175;215m\]\w\[\e[0m\]'
PS1+='\[\e[38;2;238;238;238m\]\$\[\e[0m\] '
```
The virtual-environment prefix is displayed only when a Python virtual environment is active. Setting `VIRTUAL_ENV_DISABLE_PROMPT=1` before activation prevents Python's standard activation script from adding a duplicate prefix.

**ANSI escape components:**

| Expression | Purpose |
|---|---|
| `\e[38;2;R;G;Bm` | Set RGB foreground color |
| `\e[38;5;Nm` | Set indexed foreground color |
| `\e[0m` | Reset formatting |
| `\[` and `\]` | Mark non-printing sequences in Bash |

Non-printing ANSI sequences should be enclosed in `\[` and `\]` to preserve correct cursor positioning and line wrapping.

## Applying the Configuration

Add the configuration to the appropriate shell initialization file:

| Environment | Configuration file |
|---|---|
| macOS Bash | `~/.bash_profile` |
| Linux / WSL Bash | `~/.bashrc` |

```bash
nano <config_file>
```
Reload configuration file

```bash
source <config_file>
```
**Place the custom prompt configuration after any existing prompt definitions to avoid having it overwritten.*


## Terminal Compatibility

True Color is supported by modern terminal emulators, including macOS Terminal, iTerm2, VS Code's integrated terminal, and Windows Terminal.

For broader compatibility with older terminal environments, ANSI 256-color sequences can be used instead of RGB.
