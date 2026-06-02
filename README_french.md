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
Aussi disponible en <a href="README.md"><img src="https://img.shields.io/badge/🇬🇧-English-red" alt="English"></a>
</p>

<h3 align="center">
Un CLI pour parcourir et regarder des animés depuis <a href="https://anime-sama.to">anime-sama.to</a> — interface style <strong>ani-cli</strong>
</h3>

<p align="center">
<strong>✨ Fuzzy finder &nbsp;•&nbsp; 🚀 Recherche en une commande &nbsp;•&nbsp; 🇫🇷 Support VF/VOSTFR &nbsp;•&nbsp; ▶ Épisode suivant auto</strong>
</p>

---

## Table des Matières

- [📦 Installation](#installation)
- [🎯 Utilisation](#utilisation)
- [⚙️ Options](#options)
- [🗑️ Désinstallation](#désinstallation)
- [📚 Dépendances](#dépendances)
- [❓ FAQ](#faq)
- [🌐 Projets Similaires](#projets-similaires)

---

## Installation

### Ubuntu / Debian

```bash
# 1. Installer les dépendances système
sudo apt install git python3 python3-bs4 python3-requests mpv fzf

# 2. Cloner et installer
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

## Utilisation

```bash
# Recherche interactive (recommandé)
anisama-cli

# Recherche directe
anisama-cli naruto
anisama-cli "attack on titan"

# Doublage français (VF)
anisama-cli --vf "one piece"

# Reprendre depuis l'historique
anisama-cli -c

# Aide
anisama-cli -h
```

### Déroulement

```
  Recherche › naruto
  ↓
  [fzf] Anime › Naruto / Naruto Shippuden / ...
  ↓
  [fzf] Saison › Saison 1 VOSTFR / Saison 1 VF / ...
  ↓
  [fzf] Épisode › Épisode 1 / Épisode 2 / ...
  ↓
  mpv se lance en plein écran
  ↓
  Suivant › Épisode 2 ? [O/n]   ← épisode suivant automatique
```

---

## Options

| Option | Description |
|--------|-------------|
| `--vf` | Doublage français (VF) uniquement |
| `-c, --continue` | Reprendre depuis l'historique |
| `--debug` | Afficher les informations de débogage |
| `--check-services` | Afficher quel service de streaming utilise chaque animé |
| `--available-only` | Lister les animés qui fonctionnent sans VPN (Sibnet) |
| `-h, --help` | Afficher l'aide |

---

## Désinstallation

```bash
sudo rm /usr/local/bin/anisama-cli
rm -rf ~/.local/share/animesama-cli
```

---

## Dépendances

| Dépendance | Rôle | Installation |
|-----------|------|--------------|
| `python3` | Runtime | intégré sur la plupart des distros |
| `fzf` | Sélection interactive fuzzy | `sudo apt install fzf` |
| `mpv` | Lecture vidéo | `sudo apt install mpv` |
| `python3-requests` | Requêtes HTTP | `sudo apt install python3-requests` |
| `python3-bs4` | Parsing HTML | `sudo apt install python3-bs4` |
| `yt-dlp` | Optionnel — titres d'épisodes | `sudo apt install yt-dlp` |

> **Note :** `sqlite3`, `re`, `os`, `sys` font partie de la bibliothèque standard Python — pas d'installation supplémentaire.

---

## FAQ

<details>
<summary><strong>Certains animés ne se lisent pas / erreurs Vidmoly</strong></summary>

Certains animés (Naruto, Boruto...) utilisent le service Vidmoly qui peut être bloqué géographiquement.

**Solutions :**
1. Essayez la version VF : `anisama-cli --vf naruto` (utilise Sibnet, plus fiable)
2. Utilisez un VPN
3. Vérifiez quel service utilise un animé : `anisama-cli --check-services`

</details>

<details>
<summary><strong>Comment regarder en doublage français ?</strong></summary>

Ajoutez `--vf` à votre commande :
```bash
anisama-cli --vf "one piece"
```

</details>

<details>
<summary><strong>Où est sauvegardé mon historique ?</strong></summary>

Dans une base SQLite locale : `~/.local/share/animesama-cli/history.db`

Reprenez où vous vous êtes arrêté avec `anisama-cli -c`.

</details>

<details>
<summary><strong>Puis-je utiliser VLC à la place de mpv ?</strong></summary>

Non. mpv est requis pour le support HLS et les options de lecture en ligne de commande.

</details>

<details>
<summary><strong>Fonctionne-t-il sous Windows ?</strong></summary>

Pas officiellement. Il nécessite `fzf`, `mpv` et Python 3 — tous disponibles via WSL (Windows Subsystem for Linux).

</details>

---

## Projets Similaires

- **🇯🇵 [ani-cli](https://github.com/pystardust/ani-cli)** — sous-titres japonais/anglais
- **🇵🇹 [GoAnime](https://github.com/alvarorichard/GoAnime)** — sous-titres portugais
- **🇩🇪 [aniworld-cli](https://github.com/Bog13/aniworld-cli)** — streaming allemand

---

<p align="center">
<strong>⭐ Étoilez le projet si vous le trouvez utile !</strong><br>
<em>Développé par <a href="https://github.com/can-oktay404">can-oktay404</a> — inspiré d'<a href="https://github.com/pystardust/ani-cli">ani-cli</a></em>
</p>
