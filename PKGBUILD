# Maintainer: Simon Gomizelj <simongmzlj@gmail.com>

pkgname=envoy
pkgver=5
pkgrel=1
pkgdesc="A ssh-agent/gpg-agent keychain and process monitor"
arch=('i686' 'x86_64')
url="http://github.com/vodik/envoy"
license=('GPL')
depends=('openssh' 'systemd')
optdepends=('gnupg: gpg-agent support')
makedepends=('ragel')
source=("$pkgname-$pkgver.tar.gz::https://github.com/vodik/$pkgname/archive/v$pkgver.tar.gz"
        "clique.tar.gz::https://github.com/vodik/clique/archive/v0.1.tar.gz")
md5sums=('feee9b1a0eed31360324ea868d081801'
         '8c4f3fd488fc8f92196a8aa42ac9567e')

prepare() {
  cd "$pkgname-$pkgver"
  rm -fr clique
  ln -s ../clique-0.1 clique
}

build() {
  make -C "$pkgname-$pkgver"
}

package() {
  make -C "$pkgname-$pkgver" DESTDIR="$pkgdir" install
}

# vim: ft=sh syn=sh et
