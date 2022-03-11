pkgname=pydio-cells
pkgver=3.0.5
pkgrel=1
pkgdesc="Pydio Cells Document Sharing & Collaboration"
arch=('i686' 'x86_64')
url="https://pydio.com"
license=('GNU Affero GPL')
depends=('mariadb')
optdepends=()
provides=('pydio-cells')
backup=()
source=(https://download.pydio.com/pub/cells/release/${pkgver}/linux-amd64/pydio-cells-${pkgver}-linux-amd64.zip
        cells.service
        cells.conf)
#install=enlightenment.install
sha1sums=('e20e4a124d0aa51070d6c1c8432d8561a39ba646'
          '8e06d9527bf89ce369dd4241dfc6050c6d44735f'
          'f5a4108d56fd95b0f21491095a0e329cfc85fbf3')

build() {
  mkdir -p "${srcdir}/${pkgname}-${pkgver}"
  cd "${srcdir}/${pkgname}-${pkgver}"

  mv ../cells .
  mv ../LICENSE .
#
#  export CFLAGS="$CFLAGS -fvisibility=hidden"
#
#  ./configure --prefix=/usr --sysconfdir=/etc
#  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  # install LICENSE
  install -Dm755 cells "$pkgdir/usr/bin/cells"
  install -Dm644 ../cells.service "$pkgdir/usr/lib/systemd/system/cells.service"
  install -Dm644 ../cells.conf "$pkgdir/usr/lib/sysusers.d/cells.conf"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
