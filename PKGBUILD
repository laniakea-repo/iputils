# Maintainer: Stéphane Gaudreault <stephane@archlinux.org>
# Maintainer: Tobias Powalowski <tpowa@archlinux.org>
# Contributor: Aaron Griffin <aaron@archlinux.org>

pkgname=iputils
# Commit date + git rev-parse --short origin/master
_rev=23c3782a
pkgver=20211215
pkgrel=1
pkgdesc="Network monitoring tools, including ping"
arch=('x86_64')
license=('GPL')
url="http://www.skbuff.net/iputils/"
depends=('libcap' 'libidn2')
makedepends=('perl-sgmls' 'git' 'docbook-xsl' 'meson' 'systemd' 'iproute')
conflicts=('netkit-base' 'arping')
replaces=('netkit-base')
source=("git+https://github.com/iputils/iputils.git#tag=${pkgver}?signed")
validpgpkeys=('2016FEA4858B1C36B32E833AC0DEC2EE72F33A5F') # Petr Vorel
sha1sums=('SKIP')

build() {
  mkdir -p build
  cd build

  arch-meson ../$pkgname -DBUILD_RARPD=true 
  ninja
}

package() {
  cd build

  DESTDIR="$pkgdir" ninja install
}
