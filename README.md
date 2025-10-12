# Pickles Update

[![License: Unlicense](https://img.shields.io/badge/license-Unlicense-blue.svg)](http://unlicense.org/)
[![GitHub release](https://img.shields.io/github/release/Pickles-Linux/pickles-update.svg)](https://GitHub.com/Pickles-Linux/pickles-update/releases/)
[![GitHub issues](https://img.shields.io/github/issues/Pickles-Linux/pickles-update.svg)](https://GitHub.com/Pickles-Linux/pickles-update/issues/)

A user-friendly wrapper script for `paru` to manage system updates on Arch Linux-based distributions like Pickles Linux. This tool simplifies the update process, includes an optional mirror rating feature, and prompts for a reboot after a successful update.

## 🚀 Features

- **Automated Updates**: Runs `paru -Syu` to update all packages.
- **Mirror Rating**: Optionally finds and uses the fastest mirrors for your system using `rate-mirrors`.
- **Reboot Prompt**: Asks for a reboot after the update to ensure all changes, especially kernel updates, are applied correctly.

##  📦 Installation

To install `pickles-update`, you can use `paru` directly from this Git repository. This is the recommended method as it handles all dependencies automatically.

```bash
wget https://raw.githubusercontent.com/Pickles-Linux/pickles-update/main/download_latest.sh
chmod +x download_latest.sh
./download_latest.sh

```

## 🛠 Usage

Once installed, you can run the `update` command from your terminal.

- To run a standard system update:
  ```bash
  update
  ```

- To run a system update and rate mirrors first (recommended for faster downloads):
  ```bash
  update --mirrors
  # or using the shorthand
  update -m
  ```

## 📄 Man Page

A man page is included with the package. You can view it by running:

```bash
man update
```

## 📜 License

This project is licensed under the Unlicense.
