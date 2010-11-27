# Contributor: Charles Clement <caratorn@gmail.com>
# Contributor: Corrado Primier <bardo@aur.archlinux.org>
# Maintainer: Laszlo Papp <djszapi2@gmail.com>
pkgname=bitbake
pkgver=1.10.1
pkgrel=1
pkgdesc="A simple tool for task execution derived from Gentoo's portage"
arch=('any')
url="http://developer.berlios.de/projects/bitbake/"
license=('GPL' 'custom:MIT')
depends=('python2' 'setuptools')
source=(
  http://download.berlios.de/bitbake/${pkgname}-${pkgver}.tar.gz
  cooker-unbound.diff
)
md5sums=(
  '3cb6f8483ea975a12a91a1894ed7a6e9'
  'edd4574b781c958fd73d5e7b010a5b3e'
)

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  patch -p 1 < ../cooker-unbound.diff
  python2 setup.py install --root=${pkgdir} || return 1

  # Install vim extensions
  install -D -m644 ${srcdir}/${pkgname}-${pkgver}/contrib/vim/ftdetect/bitbake.vim \
  ${pkgdir}/usr/share/vim/ftplugin/bitbake.vim || return 1
  install -D -m644 ${srcdir}/${pkgname}-${pkgver}/contrib/vim/syntax/bitbake.vim \
  ${pkgdir}/usr/share/vim/syntax/bitbake.vim || return 1
  install -D -m644 ${srcdir}/${pkgname}-${pkgver}/contrib/bbdev.sh \
  ${pkgdir}/usr/share/bitbake/bbdev.sh || return 1

  # Handle MIT license
  install -D -m644 ${srcdir}/${pkgname}-${pkgver}/doc/COPYING.MIT \
  ${pkgdir}/usr/share/licenses/${pkgname}/COPYING
}
