# Maintainer : Riley Carpenter <riley.carpenter@protonmail.com>
# Contributor: Ben R <thebenj88 *AT* gmail *DOT* com>
# Contributor : Loïc Bidoux <loic.bidoux [at] owndata.org>
# Contributor : Riley Carpenter <riley.carpenter@protonmail.com>

pkgname=vrms-arch-funny
pkgver=0.1.0.r25.gbb5e07e
pkgrel=1
pkgdesc="vrms for ArchLinux but funny"
arch=('any')
url="https://github.com/rileyball/${pkgname}"
license=('custom:BSD3')
makedepends=('git')
depends=('python' 'pyalpm')
source=("git+https://github.com/rileyball/${pkgname}.git")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/${pkgname}"
  git describe --long --tags | sed -E 's/([^-]*-g)/r\1/;s/-/./g;s/v*//'
}

build() {
  cd "$srcdir/${pkgname}"
  python setup.py build
}

package() {
  cd "$srcdir/${pkgname}"
  python setup.py install --root=${pkgdir}
  install -Dm 644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
