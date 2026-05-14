# lyricspot

`lyricspot` is a lightweight terminal lyric viewer that syncs with the active MPRIS player and fetches lyrics from `lrclib.net`.

## Install

### Arch / AUR

```bash
yay -S lyricspot
```

### Dependencies

```bash
# arch / arch-based
pacman -S playerctl

# nixos
nix-env -iA nixpkgs.playerctl

# debian / ubuntu
sudo apt install playerctl
```

### Manual

```bash
git clone https://github.com/vlensys/lyricspot
cd lyricspot
ln -sf "$(pwd)/lyricspot.py" ~/.local/bin/lyricspot
chmod +x lyricspot.py
```

## Run

```bash
lyricspot
```

## CLI

```bash
lyricspot --reset
lyricspot --clear
lyricspot --cache on
lyricspot --cache off
```

## Controls

| key | action |
|---|---|
| `↑` / `↓` | shift lyrics by `0.25s` |
| `u` | toggle header |
| `c` | toggle centered lyrics |
| `b` | toggle bold current lyric |
| `U` | toggle uppercase on the current lyric |
| `Q` / `Esc` | quit |

## Cache

Lyrics cache:

```text
~/.config/lyricspot/cache.json
```

Settings file:

```text
~/.config/lyricspot/settings.json
```

Color settings accept ANSI color indexes, basic color names, RGB arrays, or hex strings:

```json
{
  "colors": {
    "header_title": 231,
    "header_artist": 244,
    "header_offset": 244,
    "current_lyric": "#ffffff",
    "lyric_gradient": [250, 245, 240, 236],
    "progress_filled": "white",
    "progress_empty": 240,
    "status": 8,
    "muted": "gray"
  }
}
```

Use `--clear` to wipe the lyrics cache without touching settings. Use `--cache off` to disable cache reads and writes for that run.

## Notes

- Works with any MPRIS-compatible player, including `mpv`, `vlc`, `cmus`, and `rhythmbox`.
- The API base can be overridden with `LRCLIB_API`.
- If lyrics feel off, adjust the offset with `↑` and `↓`.
