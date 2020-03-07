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

## Dependencies
- meson
- python3
- git
- fontawesome (if used with `GIT_HUD_GLYPH`)

## Use and Features
Designed to be used inside a prompt (like a shell prompt). It shows only essential
information in a very short and compact format

Information shown:
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

## Dependencies
- meson
- python3
- fontawesome (if used with `BAT_HUD_GLYPH`)

## Use and Features
Designed to be used inside a prompt (like a shell prompt). It shows only essential
information in a very short and compact format

Information shown:
- Charge percent
- Battery status (charging or discharging)

## Example
With `BAT_HUD_GLYPH` set: ` 99%`  
Without `BAT_HUD_GLYPH` set: `Charging: 99%`
