<p align="center">
<br>
<a href="#linux"><img src="https://img.shields.io/badge/os-linux-90ee90"></a>
<a href="#macos"><img src="https://img.shields.io/badge/os-macOS-lightgrey"></a>
<br>
<h1 align="center">🎌 anisama-cli</h1>
<br>
<img src="https://img.shields.io/badge/version-1.3.5-blue">
<a href="https://github.com/can-oktay404"><img src="https://img.shields.io/badge/owner-can--oktay404-ff6344"></a>
<img src="https://img.shields.io/badge/python-3.6+-yellow">
</p>

<p align="center">
Also available in <a href="README_french.md"><img src="https://img.shields.io/badge/🇫🇷-Français-blue" alt="Français"></a>
</p>

<h3 align="center">
A CLI to browse and stream anime from <a href="https://anime-sama.to">anime-sama.to</a> — <strong>ani-cli</strong> style interface
</h3>

<p align="center">
<strong>✨ Fuzzy finder &nbsp;•&nbsp; 🚀 One-command search &nbsp;•&nbsp; 🇫🇷 VF/VOSTFR support &nbsp;•&nbsp; ▶ Auto next episode</strong>
</p>

---

## Table of Contents

- [📦 Install](#install)
- [🎯 Usage](#usage)
- [⚙️ Options](#options)
- [🗑️ Uninstall](#uninstall)
- [📚 Dependencies](#dependencies)
- [❓ FAQ](#faq)
- [🌐 Similar Projects](#similar-projects)

---

## Install

### Ubuntu / Debian

```bash
# 1. Install system dependencies
sudo apt install git python3 python3-bs4 python3-requests mpv fzf

# 2. Clone and install
git clone https://github.com/can-oktay404/anisama-cli.git
cd anisama-cli
chmod +x anisama-cli
sudo cp anisama-cli /usr/local/bin/
```

### Fedora

```bash
sudo dnf install git python3 python3-requests python3-beautifulsoup4 mpv fzf
git clone https://github.com/can-oktay404/anisama-cli.git
cd anisama-cli && chmod +x anisama-cli && sudo cp anisama-cli /usr/local/bin/
```

### Arch Linux

```bash
# Via AUR
yay -S anisama-cli
```

### macOS

```bash
brew install python mpv fzf git
pip3 install requests beautifulsoup4
git clone https://github.com/can-oktay404/anisama-cli.git
cd anisama-cli && chmod +x anisama-cli && sudo cp anisama-cli /usr/local/bin/
```

---

## Usage

```bash
# Interactive search (recommended)
anisama-cli

# Direct search
anisama-cli naruto
anisama-cli "attack on titan"

# French dub (VF)
anisama-cli --vf "one piece"

# Continue from history
anisama-cli -c

# Help
anisama-cli -h
```

### Flow

```
  Recherche › naruto
  ↓
  [fzf] Anime › Naruto / Naruto Shippuden / ...
  ↓
  [fzf] Saison › Saison 1 VOSTFR / Saison 1 VF / ...
  ↓
  [fzf] Épisode › Épisode 1 / Épisode 2 / ...
  ↓
  mpv launches fullscreen
  ↓
  Suivant › Épisode 2 ? [O/n]   ← auto next episode
```

---

## Options

| Option | Description |
|--------|-------------|
| `--vf` | French dub (VF) only |
| `-c, --continue` | Resume from history |
| `--debug` | Verbose debug output |
| `--check-services` | Show which streaming service each anime uses |
| `--available-only` | List animes that work without VPN (Sibnet) |
| `-h, --help` | Show help |

---

## Uninstall

```bash
sudo rm /usr/local/bin/anisama-cli
rm -rf ~/.local/share/animesama-cli
```

---

## Dependencies

| Dependency | Purpose | Install |
|-----------|---------|---------|
| `python3` | Runtime | built-in on most distros |
| `fzf` | Interactive fuzzy selection | `sudo apt install fzf` |
| `mpv` | Video playback | `sudo apt install mpv` |
| `python3-requests` | HTTP requests | `sudo apt install python3-requests` |
| `python3-bs4` | HTML parsing | `sudo apt install python3-bs4` |
| `yt-dlp` | Optional — episode titles | `sudo apt install yt-dlp` |

> **Note:** `sqlite3`, `re`, `os`, `sys` are part of Python's standard library — no extra install needed.

---

## FAQ

<details>
<summary><strong>Some anime don't play / Vidmoly errors</strong></summary>

Some anime (Naruto, Boruto...) use the Vidmoly streaming service which may be geo-blocked.

**Solutions:**
1. Try the VF version: `anisama-cli --vf naruto` (uses Sibnet, more reliable)
2. Use a VPN
3. Check which service an anime uses: `anisama-cli --check-services`

</details>

<details>
<summary><strong>Can I watch with French voice?</strong></summary>

Yes! Add `--vf` to your command:
```bash
anisama-cli --vf "one piece"
```

</details>

<details>
<summary><strong>Where is my watch history stored?</strong></summary>

In a local SQLite database: `~/.local/share/animesama-cli/history.db`

Resume where you left off with `anisama-cli -c`.

</details>

<details>
<summary><strong>Can I use VLC instead of mpv?</strong></summary>

No. mpv is required for its HLS streaming support and command-line playback options.

</details>

<details>
<summary><strong>Does it work on Windows?</strong></summary>

Not officially supported. It requires `fzf`, `mpv`, and Python 3 — all available on WSL (Windows Subsystem for Linux).

</details>

---

## Similar Projects

- **🇯🇵 [ani-cli](https://github.com/pystardust/ani-cli)** — Japanese/English subtitles
- **🇵🇹 [GoAnime](https://github.com/alvarorichard/GoAnime)** — Portuguese subtitles
- **🇩🇪 [aniworld-cli](https://github.com/Bog13/aniworld-cli)** — German streaming

---

<p align="center">
<strong>⭐ Star this project if you find it useful!</strong><br>
<em>Built by <a href="https://github.com/can-oktay404">can-oktay404</a> — inspired by <a href="https://github.com/pystardust/ani-cli">ani-cli</a></em>
</p>
