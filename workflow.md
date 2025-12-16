# Dill Workflow

This document outlines the development and user workflow for `dill`, a package manager for Arch-based distributions.

## Development Workflow

1.  **Branching**: All new features or bug fixes should be developed in separate branches.
2.  **Scripting**:
    *   All core logic is contained within scripts in the `/usr/lib/dill/scripts/` directory. For development, this is the `dill/scripts/` directory.
    *   The main `dill` executable is a dispatcher, calling the appropriate script from the `scripts` directory based on user input. It should contain minimal logic beyond argument parsing and redirection.
    *   Each script must be self-contained and modular.
    *   Scripts must adhere to the header format specified in `dill.project.info`.
3.  **Configuration**:
    *   Default configuration is stored in `/usr/lib/dill/dill.config`.
    *   Scripts must first check for a user-specific configuration at `~/.config/dill/dill.config` and use it if it exists. Otherwise, fall back to the default config.
4.  **Language and Messages**:
    *   All user-facing messages (prompts, errors, humor) must be sourced from `/usr/lib/dill/dill.language`. This allows for easier translation and customization.
5.  **Testing**:
    *   Before merging, scripts must be tested by running the main `dill` executable from the project root (e.g., `./dill/dill -Syu`).
6.  **Committing**: Commit messages should be clear and descriptive.

## User Workflow

`dill` is designed to be intuitive for users familiar with `pacman` as well as `apt`.

### Update Workflow

*   `dill -Syu`: The classic Arch way. This will call the `dill-update` script to synchronize repositories, update official packages, and then update AUR packages.
*   `dill update`: A Debian-style alias for `dill -Syu`.

### Package Installation

*   `dill -S <package>`: Installs a package from the official repositories. If the package is not found, it will search the AUR. This is handled by the `dill-install` script.
*   `dill install <package>`: A Debian-style alias for `dill -S <package>`.

### Package Removal

*   `dill -R <package>`: Removes a package. This is handled by the `dill-remove` script.
*   `dill remove <package>`: A Debian-style alias for `dill -R <package>`.

### Package Query

*   `dill -Q <package>`: Queries installed packages. Handled by `dill-query`.
*   `dill search <package>`: Searches repositories and the AUR for a package. Also handled by `dill-query`.

## File Structure (Post-Installation)

```
/usr/bin/dill                     -> Symlink to /usr/lib/dill/dill
/usr/lib/dill/
├── dill                        # Main executable, argument parser, and dispatcher
├── dill.config                 # Default configuration
├── dill.language               # Language file for all messages
├── dill-gui                    # TUI placeholder
├── dill-tui                    # GUI placeholder
└── scripts/
    ├── dill-aur-library        # Functions for searching and building AUR packages
    ├── dill-install            # Handles package installation (repo and AUR)
    ├── dill-mirrorlist         # Manages mirror lists
    ├── dill-query              # Handles package searching and queries
    ├── dill-remove             # Handles package removal
    └── dill-update             # Handles system updates
```
