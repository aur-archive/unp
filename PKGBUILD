# Maintainer: Michael Düll <mail@akurei.me> PGP-Key: AAAEE882
# Contributor:TDY <tdy@gmx.com>
# Contributor: Sergio Rubio <rubiojr.ml@gmail.com>
# Contributor: Hannes Rist <cowider@gmail.com>

pkgname=unp
pkgver=2.0~pre7+nmu1
pkgrel=1
pkgdesc="A perl script for unpacking a wide variety of archive formats"
arch=('any')
url="http://packages.qa.debian.org/u/unp.html"
license=('GPL')
depends=('perl')
install=unp.install
source=(http://ftp.debian.org/debian/pool/main/u/unp/unp_$pkgver.tar.bz2)

build() {
  cd "$srcdir/unp-$pkgver/po"
#  sed -i 's/rpm2cpio/&.pl/g; 39 i\else {\n   load_strings;\n}' unp
  make
}

package() {
  cd "$srcdir/unp-$pkgver/po"
  make DESTDIR="$pkgdir" install
  install -Dm755 ../unp "$pkgdir/usr/bin/unp"
  install -Dm755 ../ucat "$pkgdir/usr/bin/ucat"
  install -Dm644 ../debian/unp.1 "$pkgdir/usr/share/man/man1/unp.1"
  install -Dm755 ../bash_completion.d/unp "$pkgdir/etc/bash_completion.d/unp.sh"
}

sha512sums=('1b30f14c8d17e0a6b149ca4795f2219e9180f814347410e7ff7fa2b9720a9d308190f2ded8fcfd11bac9b5bb7a64ffd93f140bdaffcba1127f0e15e3d2737362')
