# Maintainer: Sven-Hendrik Haase <svenstaro@gmail.com>
# Contributor: Tércio Martins <echo dGVyY2lvd2VuZGVsQGdtYWlsLmNvbQo= | base64 -d>
# Contributor: Alexey Pavlov <alexpux@gmail.com>

pkgname=pystring
pkgver=1.1.3.git1
_commit=281419de2f91f9e0f2df6acddfea3b06a43436be
pkgrel=1
arch=('loongarch64')
pkgdesc="C++ functions matching the interface and behavior of python string methods with std::string"
url="https://github.com/imageworks/pystring"
license=('BSD')
depends=('gcc-libs')
source=("https://github.com/imageworks/pystring/archive/$_commit.tar.gz"
        "makefile.patch")
sha512sums=('e7ee1bf8a37c7f453a2dd324524a0fede9ab4448dea4ad7b2774ce44c14605dc106fea9a629344db5d5da86be9ef923e8ddf904bf8b5fffabc36b4140f1cb433'
            'dc5f94cc062023d138ab9cab92081323c576b9e03d853b615981f2bc89dd5de96bd9a19c420bbd23eac5248b7949b337fe858622aae0751fbc0b16f59db77fdd')

prepare() {
  cd $pkgname-$_commit
  patch -p1 -i "$srcdir/makefile.patch"
}

build() {
  cd $pkgname-$_commit
  make
}

package() {
  cd $pkgname-$_commit
  make DESTDIR="$pkgdir" install

  install -Dm644 "$srcdir/$pkgname-$_commit/LICENSE" "$pkgdir/usr/share/licenses/$pkgname"/LICENSE
}
