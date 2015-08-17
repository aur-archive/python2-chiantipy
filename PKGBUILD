# Maintainer:  <clu>

pkgname=python2-chiantipy  
pkgver=0.5.2
pkgrel=1 
pkgdesc="The Python interface to the CHIANTI atomic database for astrophysical spectroscopy"
url="http://chiantipy.sourceforge.net/index.html"
arch=('any')
license=('GPL3')
depends=('python2' 'python2-numpy>=1.3.0' 'python2-scipy>=0.7.1' 'python2-matplotlib' 'chianti')
makedepends=('python2' 'python2-distribute')
optdepends=('pyqt: chiantipy gui' 'wxpython: chiantipy gui')
conflicts=()
replaces=()
backup=()
source=(http://sourceforge.net/projects/chiantipy/files/ChiantiPy-${pkgver}.tar.gz
  'chianti.profile'
  'chianti.profile.csh')
md5sums=('e395d597ef4416d551d013b57bbdee13'
         '19bcf9d69dba7d58c2d140b864a10a48'
         'd996680e598ce015a0d40db375595208')

build() {
  #profiles for XUVTOP setting...
  #database is assumed to be in /opt/chianti (as packaged in AUR)
  #Edit these files if you place the chianti database elsewhere.
  install -D ${srcdir}/chianti.profile $pkgdir/etc/profile.d/chianti.sh
  install -D ${srcdir}/chianti.profile.csh $pkgdir/etc/profile.d/chianti.csh

  cd $srcdir/ChiantiPy-$pkgver
  python2 setup.py install --root=$pkgdir/ --optimize=1
}
