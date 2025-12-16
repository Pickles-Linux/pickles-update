# Dill Project TODO

This file tracks the development tasks for the `dill` package manager.

## Phase 1: Core Functionality & Scaffolding

-   [x] Create `workflow.md` to define development and user flow.
-   [x] Create initial `STATUS.md` to track progress.
-   [x] Create initial `todo.md` to list tasks.
-   [x] Add standard header to all existing files in the `dill/` directory.
-   [x] **dill (main executable):**
    -   [x] Implement basic argument parsing to handle `pacman` and `apt`-style commands (placeholder).
    -   [x] Implement basic dispatcher logic to call the correct script from `dill/scripts/` (placeholder).
    -   [x] Implement logic to source `dill.config` and `dill.language`.
-   [x] **dill.language:**
    -   [x] Populate with initial humorous and sarcastic messages (simplified and updated).
-   [x] **dill.config:**
    -   [x] Finalize the set of user-configurable options (initial set defined).
-   [x] **pickles-update.sh:**
    -   [x] Create a simple script to inform users about the transition to `dill` and display help.

## Phase 2: Script Implementation

-   [ ] **dill-update:**
    -   [ ] Implement logic to sync pacman repositories (`pacman -Syy`).
    -   [ ] Implement logic to upgrade official packages (`pacman -Su`).
    -   [ ] Implement logic to check for AUR package updates.
    -   [ ] Integrate `dill-aur-library` for AUR package building and installation.
-   [x] **dill-mirrorlist:**
    -   [x] Implement logic to fetch and rank mirrors (self-contained with rate-mirrors).
-   [ ] **dill-install:**
    -   [ ] Implement logic to check official repositories for a package.
    -   [ ] If not in official repos, search the AUR.
    -   [ ] Integrate `dill-aur-library` to build and install the AUR package.
-   [ ] **dill-remove:**
    -   [ ] Implement `pacman -Rns` equivalent.
-   [ ] **dill-query:**
    -   [ ] Implement `pacman -Qs` and `pacman -Ss` equivalents.
    -   [ ] Add functionality to search the AUR.
-   [ ] **dill-aur-library:**
    -   [ ] **This is a major task.**
    -   [ ] Implement function to search AUR (e.g., parse RPC).
    -   [ ] Implement function to download `PKGBUILD` and related files.
    -   [ ] Implement dependency checking.
    -   [ ] Implement `makepkg` wrapper.
    -   [ ] Implement conflict resolution.
    -   [ ] Implement PGP key handling.

## Phase 3: Packaging & Release

-   [ ] Create `PKGBUILD` file.
-   [ ] Write man pages.
-   [ ] Test installation and uninstallation.
-   [ ] Announce first stable release.