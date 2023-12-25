pkgname=qemu
pkgver=8.2.0
pkgrel=1
pkgdesc='QEMU is a generic and open source machine emulator and virtualizer.'
arch=('x86_64')
url='https://www.qemu.org/'
license=('GPLv2')
depends=('glib2' 'pixman' 'zlib' 'libaio' 'libnfs' 'libseccomp' 'libcap-ng' 'libxkbcommon' 'zstd' 'curl' 'ncurses' 'libssh' 'bzip2' 'libepoxy' 'gnutls' 'gmp' 'gtk3' 'libx11' 'libpng' 'libjpeg-turbo' 'libsasl' 'pam' 'lzo2' 'libusb' 'libtasn1' 'keyutils' 'fuse3' 'elfutils')
makedepends=('ninja')
source=("https://download.qemu.org/qemu-${pkgver}.tar.xz")
sha512sums=('92ec41196ff145cdbb98948f6b6e43214fa4b4419554a8a1927fb4527080c8212ccb703e184baf8ee0bdfa50ad7a84689e8f5a69eba1bd7bbbdfd69e3b91256c')
src_name="qemu-${pkgver}"

build() {
    cd "${src_name}"

    ./configure --target-list=x86_64-softmmu --prefix=/usr
    cd build
    make -j$(nproc)
}

package() {
    cd "${src_name}"
    make DESTDIR=${pkgdir} install
}
