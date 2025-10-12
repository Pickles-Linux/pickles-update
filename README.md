# Pickles Update

[![License: Unlicense](https://img.shields.io/badge/license-Unlicense-blue.svg)](http://unlicense.org/)
[![GitHub release](https://img.shields.io/github/release/Pickles-Linux/pickles-update.svg)](https://GitHub.com/Pickles-Linux/pickles-update/releases/)
[![GitHub issues](https://img.shields.io/github/issues/Pickles-Linux/pickles-update.svg)](https://GitHub.com/Pickles-Linux/pickles-update/issues/)

A modular script suite for managing system updates on Arch Linux-based distributions like Pickles Linux. This tool automates the update process, includes mirror rating, package querying, and separate handling for pacman and AUR updates, with a reboot prompt after successful updates.
## ⚠️ IMPORTANT NOTE
  **This version is a total re-write and is not fully functioning** 

## 🚀 Features

- **Modular Design**: Separate scripts for different operations (`pickles-update.sh`, `pacman-update.sh`, `aur-update.sh`, `query-updates.sh`, `rate-mirrors.sh`).
- **Automated Updates**: Updates packages from official repositories and AUR.
- **Mirror Rating**: Finds and uses the fastest mirrors for improved download speeds.
- **Configuration**: Customizable settings via `pupdate.conf`.
- **Reboot Prompt**: Asks for a reboot after updates to apply changes.

## 🛠 Built With

* ![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)

## 📦 Installation

**⚠️ Development Version - Not for Production Use**

To install the development version of `pickles-update`, you'll need development tools:

**Prerequisites:** `base-devel` package group, `git`

```bash
git clone https://github.com/Pickles-Linux/pickles-update.git -b dev
cd pickles-update
makepkg -si
```

This will install the scripts to `/etc/pickles-linux/pickles-update/` and create symlinks in `/usr/bin`.

**Note:** This is a development version with modular design and may not be fully stable.

## 🛠 Usage

Once installed, use the `pickles-update` or `pupdate` commands.

- To run a standard system update:
  ```bash
  pickles-update
  # or
  pupdate
  ```

- To update and rate mirrors first:
  ```bash
  pickles-update -m
  # or
  pupdate --mirrors
  ```

- To install specific packages:
  ```bash
  pickles-update -S package1 package2
  ```

- Other options: See `pickles-update --help` for full usage.

## 📄 Man Page

A man page is included. View it with:

```bash
man pickles-update
```

## 🤝 Contributing

We welcome contributions to the development version! Here's how you can help:

### Development Setup

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes
4. Test thoroughly (especially the modular scripts)
5. Commit your changes: `git commit -m 'Add amazing feature'`
6. Push to the branch: `git push origin feature/amazing-feature`
7. Open a Pull Request

### Testing

Since this is a development version, please test:
- All modular scripts individually
- Integration between scripts
- Error handling and edge cases
- Configuration file parsing

### Reporting Issues

- Use the GitHub issue tracker for bugs
- Include system information and steps to reproduce
- Check existing issues before creating new ones

## 📜 License

This project is licensed under the Unlicense.

<!-- MARKDOWN LINKS & IMAGES -->
[contributors-shield]: https://img.shields.io/github/contributors/Pickles-Linux/pickles-update.svg?style=for-the-badge
[contributors-url]: https://github.com/Pickles-Linux/pickles-update/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Pickles-Linux/pickles-update.svg?style=for-the-badge
[forks-url]: https://github.com/Pickles-Linux/pickles-update/network/members
[stars-shield]: https://img.shields.io/github/stars/Pickles-Linux/pickles-update.svg?style=for-the-badge
[stars-url]: https://github.com/Pickles-Linux/pickles-update/stargazers
[issues-shield]: https://img.shields.io/github/issues/Pickles-Linux/pickles-update.svg?style=for-the-badge
[issues-url]: https://github.com/Pickles-Linux/pickles-update/issues
[license-shield]: https://img.shields.io/github/license/Pickles-Linux/pickles-update.svg?style=for-the-badge
[license-url]: https://github.com/Pickles-Linux/pickles-update/blob/main/LICENSE
