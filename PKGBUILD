# Maintainer: Stu Pickles <stu@pickles-linux.com>
pkgname=dill
pkgver=0.0.1
pkgrel=2
pkgdesc="A modular script suite for managing system updates on Arch Linux-based distributions"
arch=('any')
url="https://github.com/Pickles-Linux/pickles-update"
license=('Unlicense')
depends=('bash' 'pacman' 'git' 'curl')
_gitname=pickles-update
source=("git+https://github.com/Pickles-Linux/pickles-update.git")
sha256sums=('SKIP')

package() {
    # Install main files to /usr/lib/dill
    install -d "$pkgdir/usr/lib"
    cp -r "$_gitname/dill" "$pkgdir/usr/lib/"

    # Ensure executables are executable
    chmod +x "$pkgdir/usr/lib/dill/dill"
    chmod +x "$pkgdir/usr/lib/dill/scripts/"*

    # Install man page and compress it
    install -Dm644 "$_gitname/dill/man/dill.1" "$pkgdir/usr/share/man/man1/dill.1"
    gzip "$pkgdir/usr/share/man/man1/dill.1"

    # Install shell completions
    install -Dm644 "$_gitname/dill/dill-completions/dill-completion.bash" "$pkgdir/usr/share/bash-completion/completions/dill"
    install -Dm644 "$_gitname/dill/dill-completions/dill-completion.fish" "$pkgdir/usr/share/fish/vendor_completions.d/dill.fish"
    install -Dm644 "$_gitname/dill/dill-completions/dill-completion.zsh" "$pkgdir/usr/share/zsh/site-functions/_dill"

    # Create symlink
    install -d "$pkgdir/usr/bin"
    ln -s /usr/lib/dill/dill "$pkgdir/usr/bin/dill"
}
