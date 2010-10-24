# Contributor: Charles Clement <caratorn@gmail.com>
# Contributor: Corrado Primier <bardo@aur.archlinux.org>
# Maintainer: Laszlo Papp <djszapi2@gmail.com>
pkgname=bitbake
pkgver=1.10.0
pkgrel=1
pkgdesc="A simple tool for task execution derived from Gentoo's portage"
arch=('i686' 'x86_64')
url="http://developer.berlios.de/projects/bitbake/"
license=('GPL' 'custom:MIT')
depends=('python')
source=(http://download.berlios.de/bitbake/${pkgname}-${pkgver}.tar.gz)
md5sums=('be3b330255e9d863ef5f018a1f6c7086')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
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
