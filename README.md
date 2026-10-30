# Rolling Rebirth 🔄

> **Convert Ubuntu into a *"rolling release"* that tracks the `devel` series.**  
> A modernized continuation inspired by the original [Rolling Rhino](https://github.com/wimpysworld/rolling-rhino) project.

---

## 📖 Introduction

**Rolling Rebirth** is a tool to convert an Ubuntu installation (Desktop or official desktop flavours) into a **rolling release** by tracking the `devel` series repositories.

It is designed for Ubuntu developers, enthusiasts, and power users who want to install Ubuntu once and continuously receive the latest packages and development updates across release cycles.

---

## ⚠️ Caveats & Warnings

* **Advanced Users Only:** Opting into the `devel` series means tracking the latest in-development packages. You are responsible for maintaining your system, managing PPAs, resolving orphaned packages, and troubleshooting issues.
* **Daily Image / Devel Branch Required:** If you are on an interim or older LTS release, you should start from a fresh daily build or upgrade to the current development release before switching.
* **APT Warnings:** You may see `W: Conflicting distribution:` warnings from `apt` because your configuration points to `devel`. These warnings are normal and expected.

---

## 🚀 Usage

### 1. Requirements
* Ubuntu Desktop (or official flavours like Kubuntu, Lubuntu, Xubuntu, Ubuntu Budgie, Ubuntu MATE, etc.) installed from a **daily build** or development branch.
* Root or sudo privileges.

### 2. Run Rebirth

Clone the repository and run the `rebirth` script:

```bash
git clone https://github.com/Tonklaistonton/rolling-Rebirth.git
cd rolling-Rebirth
sudo ./rebirth
```

#### Command Options:
* `-m, --menu`: Force interactive checklist menu (runs automatically when launched in terminal).
* `--no-menu`: Skip interactive menu and use CLI flags or default settings.
* `-p, --purge-snap`: Purge all snap packages, remove snapd, and block snapd via APT pinning.
* `--no-purge-snap`: Keep snapd and snap packages.
* `--flatpak`: Install Flatpak and configure Flathub repository (recommended alternative).
* `--dev-tools`: Install developer essentials (curl, git, build-essential, zsh, htop).
* `--no-devel`: Do NOT switch to devel series (run only selected tweaks like Snap removal).
* `-d, --dry-run`: Test pre-flight checks and view proposed changes without modifying files.
* `-f, --force`: Force tracking devel series even on stable LTS/interim releases.
* `-s, --skip-desktop-check`: Skip checking for desktop packages (ideal for Server or Minimal setups).
* `-y, --yes`: Automatic yes to prompts (unattended mode, skips interactive menu).
* `-h, --help`: Display usage help.

### 3. Interactive Menu Interface

When you run `sudo ./rebirth`, you get an interactive checklist menu. Use your keyboard to customize exactly what you want:

```text
  ==[ Configuration Checklist ]==
  Use [↑/↓] or [j/k] to navigate, [Space] to toggle, [Enter] to confirm:

  ➔ [✔] Track Ubuntu 'devel' series (Rolling Release)
    [✔] Purge Snap completely and block snapd (De-Snap)
    [ ] Install Flatpak with Flathub repository
    [ ] Disable active third-party PPAs & external repositories
    [ ] Install Dev Essentials (curl, git, build-essential, zsh, htop)
    [✔] Clean up obsolete packages & APT cache
```

* Navigate with **`↑` / `↓`** (or **`k` / `j`**)
* Toggle selections on/off with **`[Space]`**
* Press **`[Enter]`** to confirm and run!

Once confirmed, `rebirth` executes your chosen tasks in sequence, backs up your configurations, updates sources (supporting modern deb822 `ubuntu.sources`), and sets up your system cleanly.

---

## 🛠️ Roadmap & Enhancements

* [x] **Interactive Spacebar Checklist Menu:** Navigate with arrows and toggle choices with Spacebar before execution.
* [x] **Modern APT Support (deb822):** Full compatibility with `/etc/apt/sources.list.d/ubuntu.sources` on Ubuntu 24.04 Noble Numbat and newer.
* [x] **Complete Snap Purge (De-Snap):** Fully remove snap packages, services, directories, and block snapd from reinstalling (`-p, --purge-snap`).
* [x] **Flatpak & Flathub Integration:** Clean alternative application store support (`--flatpak`).
* [x] **Developer Essentials Pack:** Quick installation of curl, git, build-essential, zsh, and htop (`--dev-tools`).
* [x] **Modular Devel Toggle:** Ability to deselect tracking devel to use Rebirth purely as a system tweaker/de-snapper (`--no-devel`).
* [x] **Server & Minimal Mode:** Option to run without requiring a desktop environment package installed (`--skip-desktop-check`).
* [x] **Dry-run Mode:** Safe simulation before applying changes (`--dry-run`).
* [ ] **Safety & Snapshot Integration:** Automatic Btrfs or Timeshift snapshot before triggering `dist-upgrade`.

---

## 🤝 Credits & Acknowledgments

* Originally conceived as **Rolling Rhino** by [Martin Wimpress](https://github.com/flexiondotorg) and inspired by discussions on the [Ubuntu Podcast](https://ubuntupodcast.org) with [Stuart Langridge](https://twitter.com/sil) and [Sergio Schvezov](https://twitter.com/sergiusens).
* Continued and maintained under the **Rebirth** project by [Tonklaistonton](https://github.com/Tonklaistonton/rolling-Rebirth).

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
