_pkgname=gcc-arm-mingw32ce
pkgname=$_pkgname-git
pkgver=9.3.0
pkgrel=1
arch=('any')
makedepends=('git' 'gcc' 'make' 'bison' 'flex' 'm4' 'gmp' 'mpc' 'mpfr' 'texinfo' 'cmake')
source=('git+https://github.com/MaxKellermann/cegcc-build'
    'git+https://github.com/MaxKellermann/binutils-gdb'
    'git+https://github.com/MaxKellermann/gcc'
    'git+https://github.com/MaxKellermann/mingwrt'
    'git+https://github.com/MaxKellermann/w32api')
md5sums=(
    'SKIP'
    'SKIP'
    'SKIP'
    'SKIP'
    'SKIP'
    )

prepare() {
    cd cegcc-build
    git submodule init
    git config submodule.libs/binutils.url "$srcdir/binutils-gdb"
    git config submodule.libs/gcc.url "$srcdir/gcc"
    git config submodule.libs/mingw.url "$srcdir/mingwrt"
    git config submodule.libs/w32api.url "$srcdir/w32api"
    git -c protocol.file.allow=always submodule update
}

package() {
    cd cegcc-build
    mkdir $pkgdir/usr
    chown "$(whoami):$(whoami)" $pkgdir/usr
    cd $pkgdir/usr
    "$OLDPWD/build.sh" -j$(nproc) --prefix=$pkgdir/usr
}