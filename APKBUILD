# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=glog
pkgver=0.3.4
pkgrel=0
pkgdesc="C++ implementation of the Google logging module"
url="https://github.com/google/glog"
arch="all"
license="Commercial"
depends=""
depends_dev=""
makedepends="$depends_dev"
install=""
subpackages="$pkgname-dev $pkgname-doc"
source="glog-$pkgver.tar.gz::https://github.com/google/glog/archive/v$pkgver.tar.gz"

_builddir="$srcdir"/glog-$pkgver
prepare() {
	local i
	cd "$_builddir"
	update_config_sub || return 1
	for i in $source; do
		case $i in
		*.patch) msg $i; patch -p1 -i "$srcdir"/$i || return 1;;
		esac
	done
}

build() {
	cd "$_builddir"
	./configure \
		--build=$CBUILD \
		--host=$CHOST \
		--prefix=/usr \
		--sysconfdir=/etc \
		--mandir=/usr/share/man \
		--localstatedir=/var \
		|| return 1
	make || return 1
}

package() {
	cd "$_builddir"
	make DESTDIR="$pkgdir" install || return 1
}

md5sums="df92e05c9d02504fb96674bc776a41cb  glog-0.3.4.tar.gz"
sha256sums="ce99d58dce74458f7656a68935d7a0c048fa7b4626566a71b7f4e545920ceb10  glog-0.3.4.tar.gz"
sha512sums="139525b546a9eccacc9bebf7cc3053ba52229e9488485ad45344c3d3134ca819d3b571250c0e3a6d84097009c8be89b0f4fa16ef5ec838ffcc237ae11c3a034c  glog-0.3.4.tar.gz"
