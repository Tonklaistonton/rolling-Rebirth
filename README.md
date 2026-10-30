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

### 3. Example Output

```text
Rolling Rebirth 🔄
  [+] INFO: lsb_release detected.
  [+] INFO: Ubuntu detected.
  [+] INFO: Ubuntu 24.04 LTS (development branch) detected.
  [+] INFO: Detected ubuntu-desktop.
  [+] INFO: No PPAs detected, this is good.
  [+] INFO: All checks passed.
Are you sure want to start tracking the devel series? [y/N]
```

Once confirmed, `rebirth` updates your APT sources to point to `devel`, cleans up obsolete caches, and performs a full `dist-upgrade`.

---

## 🛠️ Roadmap & Future Enhancements

* [ ] **Modern APT Support (deb822):** Full compatibility with `/etc/apt/sources.list.d/ubuntu.sources` on Ubuntu 24.04 Noble Numbat and newer.
* [ ] **Server & Minimal Mode:** Option to run without requiring a desktop environment package installed (`--skip-desktop-check`).
* [ ] **Safety & Snapshot Integration:** Automatic Btrfs or Timeshift snapshot before triggering `dist-upgrade`.
* [ ] **Custom Packages & Dotfiles:** Easy hooks to auto-install preferred developer tools and configs.

---

## 🤝 Credits & Acknowledgments

* Originally conceived as **Rolling Rhino** by [Martin Wimpress](https://github.com/flexiondotorg) and inspired by discussions on the [Ubuntu Podcast](https://ubuntupodcast.org) with [Stuart Langridge](https://twitter.com/sil) and [Sergio Schvezov](https://twitter.com/sergiusens).
* Continued and maintained under the **Rebirth** project by [Tonklaistonton](https://github.com/Tonklaistonton/rolling-Rebirth).

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
