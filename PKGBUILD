# Maintainer: AndreasBWagner <AndreasBWagner@gmail.com>
# $Id: PKGBUILD 26441 2010-09-15 14:39:42Z foutrelis $
# Contributor: nesl247 <nesl247@gmail.com>

pkgname=hal-cups-utils
pkgver=0.6.19
pkgrel=3
pkgdesc="Cups management via HAL UDIs"
url="https://fedorahosted.org/hal-cups-utils/"
arch=('i686' 'x86_64')
license=('GPLv2' 'LGPLv2')
depends=('hal' 'dbus-core' 'system-config-printer-common' 'glib2')
source=(http://fedorahosted.org/releases/h/a/hal-cups-utils/$pkgname-$pkgver.tar.gz)
md5sums=('58e1c8f5597dd39e57dcf3c4aabe60f8')

build() {
  cd ${srcdir}/$pkgname-$pkgver

  # Point Python scripts to the python2 binary
  sed -i 's/env python/env python2/' systemv/hal_lpadmin

  ./configure --prefix=/usr --libexecdir=/usr/lib/hal/scripts/

  make
}

package() {
  cd ${srcdir}/$pkgname-$pkgver

  make DESTDIR="$pkgdir" install
}
