# shell-huds
This repo contains some shell/python3 scripts that can be used in a shell prompt
to display quick information.

## Installation
### Requirements:
- meson
- git
- python3
- fontawesome (see each hud for more info)

### How to install
In the root directory of the repository run:
```sh
meson build
ninja -C ./build install
```

# git-hud
Small python script that formats a quick summary about the current git repository
and prints it to standard output.

If the environment variable `GIT_HUD_GLYPH` is set, the script will use
unicode glyphs. The variable is always ignored if a tty is detected.

`git-hud` help dialog:
```
usage: git-hud [-h] [-v]

Format a quick summary about the current git repository and print it to
standard output.

optional arguments:
  -h, --help     show this help message and exit
  -v, --version  show info about version

If the environment variable GIT_HUD_GLYPH is set, the script will use unicode
glyphs. The variable is, however, ignored if a tty is used.
```

## Information shown
- branch
- short hash of latest commit
- number of commit ahead or behind remote (if present)
- symbols for:
	- deleted, modified, renamed files (\*)
	- untracked files (?)
	- merge conflicts (!)
	- stashed changes ($)

## Example
With `GIT_HUD_GLYPH` set: ` master (7146799); ↑9 ↓2; (?)`  
Without `GIT_HUD_GLYPH` set: `branch master (7146799); ahead 9 behind 0; (?)`

# bat-hud
Small python script that formats a quick summary about the charge of the
battery (if available) and ouptuts it to standard output.

If the environment variable `BAT_HUD_GLYPH` is set, the script will use
unicode glyphs. The variable is always ignored if a tty is detected.

`bat-hud` help dialog:
```
usage: bat-hud [-h] [-v]

Format a quick summary about the cnarge of the battery, if available.

optional arguments:
  -h, --help     show this help message and exit
  -v, --version  show info about version

If the environment variable BAT_HUD_GLYPH is set, the script will use unicode
glyphs. The variable is, however, ignored if a tty is used.
```

## Information shown
- Charge percent
- Battery status (charging or discharging)

## Example
With `BAT_HUD_GLYPH` set: ` 99%`  
Without `BAT_HUD_GLYPH` set: `Charging: 99%`
