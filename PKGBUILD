pkgname=diffutils
pkgver=3.12
pkgrel=2
pkgdesc="Utility programs used for creating patch files"
arch=('x86_64')
url="https://www.gnu.org/software/diffutils/"
license=('GPL-3.0-or-later')
groups=('base')
depends=(
    'glibc'
)
makedepends=(
    'gperf'
    'help2man'
    'python'
)
source=(https://ftp.gnu.org/gnu/${pkgname}/${pkgname}-${pkgver}.tar.xz)
sha256sums=(7c8b7f9fc8609141fdea9cece85249d308624391ff61dedaf528fcb337727dfd)

build() {
    cd ${pkgname}-${pkgver}

    local configure_args=(
        ${configure_options}
    )

    ./configure "${configure_args[@]}"

    make
}

package() {
    cd ${pkgname}-${pkgver}

    make DESTDIR=${pkgdir} install
}
