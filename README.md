# Pickles Update

A user-friendly wrapper script for `pacman` to manage system updates on Arch Linux-based distributions like Pickles Linux. This tool simplifies the update process,and aims to take the place of similiar wrappers

## 🚀 Features


## 📦 Installation

To install `pickles-update`, you can use `paru` directly from this Git repository. This is the recommended method as it handles all dependencies automatically.

```bash
wget https://raw.githubusercontent.com/Stu-Pickles3047/pickles-update/main/download_latest.sh
chmod +x download_latest.sh
./download_latest.sh

```
or add the Pickles Linux repo see: <website for repo instructions
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

