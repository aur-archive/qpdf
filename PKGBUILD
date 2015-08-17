# Maintainer: Miguel Revilla <yo at miguelrevilla.com>
# Contributor: David Sotelo <dvsotelo at gmail.com>
# Contributor: Nuno Araujo <nuno.araujo@russo79.com>

pkgname=qpdf
pkgver=3.0.1
pkgrel=1
pkgdesc="QPDF: A Content-Preserving PDF Transformation System"
arch=('i686' 'x86_64')
url="http://qpdf.sourceforge.net/"
license=('custom:Artistic-2.0')
depends=('pcre' 'perl')
makedepends=('make')
options=('!libtool')
source=(http://downloads.sourceforge.net/${pkgname}/${pkgname}-${pkgver}.tar.gz)
md5sums=('48767e2519029d0214cd0fcafa3a8f8c')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr
  make || return 1
  make DESTDIR="${pkgdir}/" install

  mkdir -m755 -p ${pkgdir}/usr/share/licenses/${pkgname}
  install -m644 Artistic-2.0 ${pkgdir}/usr/share/licenses/${pkgname}/
}
