_pkgname=gcc-arm-mingw32ce
pkgname=$_pkgname-git
pkgver=9.3.0
pkgrel=1
arch=('any')
makedepends=('git' 'gcc' 'make' 'bison' 'flex' 'm4' 'gmp' 'mpc' 'mpfr' 'texinfo' 'cmake')
source=('git+https://github.com/MaxKellermann/cegcc-build')
md5sums=('SKIP')

package() {
    cd "$srcdir/$_pkgname"
    chown "$(whoami):$(whoami)" $pkgdir/usr
    cd $pkgdir/usr
    "$OLDPWD/build.sh" -j$(nproc) --prefix=$pkgdir/usr
}