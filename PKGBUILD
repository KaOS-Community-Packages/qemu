pkgname=qemu
pkgver=6.0.0
pkgrel=2
pkgdesc='QEMU is a generic and open source machine emulator and virtualizer.'
arch=('x86_64')
url='https://www.qemu.org/'
license=('GPLv2')
depends=()
makedepends=('ninja')
source=("https://download.qemu.org/qemu-${pkgver}.tar.xz")
sha512sums=('ee3ff00aebec4d8891d2ff6dabe4e667e510b2a4fe3f6190aa34673a91ea32dcd2db2e9bf94c2f1bf05aa79788f17cfbbedc6027c0988ea08a92587b79ee05e4')
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
