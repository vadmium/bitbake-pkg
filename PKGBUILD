pkgname=bitbake
pkgver=1.8.4
pkgrel=1
pkgdesc="A simple tool for task execution derived from Gentoo's portage"
url="http://developer.berlios.de/projects/bitbake/"
arch=('i686')
license=('GPL' 'custom')
depends=('python')
source=(http://download.berlios.de/bitbake/${pkgname}-${pkgver}.tar.gz)
md5sums=('508d9a61c635d469be8facc95151158b')

build() {
  cd ${startdir}/src/${pkgname}-${pkgver}
  python setup.py install --root=${startdir}/pkg

  # Install vim extensions
  install -D -m644 ${startdir}/src/${pkgname}-${pkgver}/contrib/vim/ftdetect/bitbake.vim \
                ${startdir}/pkg/usr/share/vim/ftplugin/bitbake.vim
  install -D -m644 ${startdir}/src/${pkgname}-${pkgver}/contrib/vim/syntax/bitbake.vim \
                ${startdir}/pkg/usr/share/vim/syntax/bitbake.vim

  # Handle MIT license
  install -D -m644 ${startdir}/src/${pkgname}-${pkgver}/doc/COPYING.MIT \
                ${startdir}/pkg/usr/share/licenses/${pkgname}/COPYING.MIT
}
