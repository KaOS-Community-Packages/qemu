pkgname=qemu
pkgver=5.2.0
pkgrel=2
pkgdesc='QEMU is a generic and open source machine emulator and virtualizer.'
arch=('x86_64')
url='https://www.qemu.org/'
license=('GPLv2')
depends=()
makedepends=('ninja')
source=("https://download.qemu.org/qemu-${pkgver}.tar.xz")
md5sums=('179f86928835da857c237b42f4b2df73')

src_name="qemu-${pkgver}"

build() {
    cd "${src_name}"

    ./configure --target-list=x86_64-softmmu
    cd build
    make -j$(nproc)
}

package() {
    cd "${src_name}"
    make DESTDIR=${pkgdir} install
}

