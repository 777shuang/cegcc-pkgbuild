pkgname=gcc-arm-mingw32ce
pkgver=9.3.0
pkgrel=1
arch=('any')
makedepends=('git' 'gcc' 'make' 'bison' 'flex' 'm4' 'gmp' 'mpc' 'mpfr' 'texinfo' 'cmake')

prepare() {
    cd "$pkgname"
    git clone --recursive https://github.com/MaxKellermann/cegcc-build.git
}

package() {
    chown "$(whoami):$(whoami)" $pkgdir/usr
    cd $pkgdir/usr
    "$OLDPWD/build.sh" -j$(nproc) --prefix=$pkgdir/usr
}