# Maintainer: Simone Cimarelli <aquilairreale@ymail.com>

pkgname=urlencode
pkgver=1.4.0
pkgrel=1
pkgdesc='base64-like encoder/decoder for URL percent-encoding'
arch=('x86_64' 'i686' 'pentium4')
url='https://github.com/AquilaIrreale/urlencode'
license=('GPL3')
source=("https://github.com/AquilaIrreale/${pkgname}/archive/refs/tags/v${pkgver}.tar.gz"
        "0001-getchar-must-be-assigned-to-an-int-to-handle-EOF-pro.patch")
sha512sums=('685131bf72e23568c770bfbb573d14950aa9aa0b4198f6d842067a7777dc1b72a968d645d82e942dab9cae662a63721149b78667f986c94e09b2ae0ffd67828d'
            'b3455f546ff519faf4410fef634de2a8ee31e77e3d3250c2f5746e26d73bfbf2389d135b25068e3fc39e780b42332b512768304badf6299e57e079a19f97910b')

prepare() {
    cd "${pkgname}-${pkgver}"
    patch -Np1 -i "${srcdir}/0001-getchar-must-be-assigned-to-an-int-to-handle-EOF-pro.patch"
    ./autogen.sh
}

build() {
    cd "${pkgname}-${pkgver}"
    ./configure --prefix="$pkgdir/usr"
    make
}

package() {
    cd "${pkgname}-${pkgver}"
    make install
}
