# lyricspot

basically, `lyricspot` is just a TUI lyric app that uses lrclib to fetch your currnetly played song's lyrics from lrclib

## install

### AUR

```bash
yay -S lyricspot
```

### dependency

```bash
# arch / arch-based
pacman -S playerctl

# nixos
nix-env -iA nixpkgs.playerctl

# debian / ubuntu
sudo apt install playerctl
```

### manual install (any distro works for this)

```bash
git clone https://github.com/vlensys/lyricspot
cd lyricspot
chmod +x lyricspot.py
mv lyricspot.py ~/.local/bin/
```

## running it

```bash
lyricspot
```

## commands

```bash
lyricspot --reset
lyricspot --clear
lyricspot --cache on
lyricspot --cache off
```

## controls

| key | action |
|---|---|
| `↑` / `↓` | shift lyrics by `0.25s` |
| `u` | toggle header |
| `c` | toggle centered lyrics |
| `b` | toggle bold current lyric |
| `U` | toggle uppercase on the current lyric |
| `Q` / `Esc` | quit |

## Cache

we store lyrics we fetch from lrclib in order to save time on loading them and have more offline support

```text
~/.config/lyricspot/cache.json
```

settings r stored here:

```text
~/.config/lyricspot/settings.json
```

color settings work w/ ANSI color indexes, basic color names, RGB arrays, or hex strings

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

