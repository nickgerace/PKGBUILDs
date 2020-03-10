# Maintainer: orhun <orhunparmaksiz@gmail.com>
pkgname=kmon-bin
pkgver=v0.3.0
pkgrel=1
pkgdesc="Linux kernel manager and activity monitor"
arch=('x86_64')
url="https://github.com/orhun/kmon"
license=('GPL3')
depends=('libxcb')
makedepends=('cargo' 'git')
provides=("${pkgname%-bin}")
conflicts=("$pkgname" "${pkgname}-git" "${pkgname}-bin")
source=("https://github.com/orhun/${pkgname%-bin}/releases/download/$pkgver/${pkgname%-bin}-${pkgver#v}.tar.gz")
sha256sums=('3a3dc6b357a4a3e28e60d3d90aa49bf9add23bec61dffff5f6c060c8cbaecc8e')

package() {
  install -Dt "$pkgdir/usr/bin/" "$srcdir/kmon"
  install -Dm 644 README.md -t "$pkgdir/usr/share/doc/${pkgname%-bin}"
  install -Dm 644 LICENSE -t "$pkgdir/usr/share/licenses/${pkgname%-bin}"
  install -Dm 644 "man/${pkgname%-bin}.8" -t "$pkgdir/usr/local/man/man8"
  gzip "$pkgdir/usr/local/man/man8/${pkgname%-bin}.8"
}