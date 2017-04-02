# Contributor: Tomoya Tanjo <ttanjo@gmail.com>
# Maintainer: Tomoya Tanjo <ttanjo@gmail.com>
pkgname=cmigemo
pkgver=1.2.r38
pkgrel=0
pkgdesc="An implementation of Migemo in C"
url="https://www.kaoriya.net/software/cmigemo/"
arch="x86_64"
license="MIT"
depends=""
makedepends="perl nkf"
install=""
subpackages="$pkgname-dev $pkgname-doc"
source="${pkgname}-master.zip::https://codeload.github.com/koron/cmigemo/zip/master"
builddir="$srcdir/$pkgname-master"

build() {
        cd "$builddir"
        ./configure --prefix="$pkgdir"/usr || return 1
        make gcc gcc-dict || return 1
}

package() {
        cd "$builddir"
        mkdir -p "$pkgdir"/usr/share/migemo/cp932
        mkdir -p "$pkgdir"/usr/share/migemo/euc-jp
        mkdir -p "$pkgdir"/usr/share/migemo/utf-8
        make docdir="$pkgdir"/usr/share/doc gcc-install || return 1
}

doc() {
        cd "$builddir"
        mkdir -p "$subpkgdir"/usr/share/doc/cmigemo
        mv "$pkgdir"/usr/share/doc/README_j.txt "$subpkgdir"/usr/share/doc/cmigemo
}

dev() {
        cd "$builddir"
        mkdir -p "$subpkgdir"/usr/include
        mv "$pkgdir"/usr/include/migemo.h "$subpkgdir"/usr/include
}
