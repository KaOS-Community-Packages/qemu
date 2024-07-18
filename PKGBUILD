pkgname=qemu
pkgver=9.0.2
pkgrel=1
pkgdesc='A generic and open source machine emulator and virtualizer.'
arch=('x86_64')
url='https://www.qemu.org/'
license=('GPL-2')
depends=('glib2' 'pixman' 'zlib' 'libaio' 'libnfs' 'libseccomp' 'libcap-ng' 'libxkbcommon' 'zstd' 'curl' 'ncurses' 'libssh' 'bzip2' 'libepoxy' 'gnutls' 'gmp' 'gtk3' 'libx11' 'libpng' 'libjpeg-turbo' 'libsasl' 'pam' 'lzo2' 'libusb' 'libtasn1' 'keyutils' 'fuse3' 'elfutils')
makedepends=('ninja')
source=("https://download.qemu.org/qemu-${pkgver}.tar.xz")
sha512sums=('58ed84f6fe6263d279356bc9193f96edf62cf3663fb151daa3f047d52329fe49cb91c2d45e09697e0469f4f5409be96403aec9572d4871ffa40848a786c21599')
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
    # not sure why this gets created but it messes with things
    rm -rf "${pkgdir}/var"
}
