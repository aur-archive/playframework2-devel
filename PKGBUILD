# Maintainer: Michele Damiano Torelli <me_AT_mdtorelli_DOT_it>

pkgname=playframework2-devel
pkgver=2.2.3rc2
_pkgver=2.2.3
_develver=RC2
pkgrel=1
arch=('any')
url="http://www.playframework.org/"
license=('Apache')
pkgdesc="An open source web application framework in Java which follows the MVC pattern - Development version"
depends=('java-environment')
optdepends=('playframework2-devel-extras: to provide samples and other extras')
conflicts=('playframework' 'playframework2' 'playframework2-git')
replaces=('playframework2')
provides=('playframework2')
source=("http://downloads.typesafe.com/play/${_pkgver}-${_develver}/play-${_pkgver}-${_develver}.zip")
sha1sums=('0b1fa38fbcab0ae84ab96c9cbd8c4d0dd66e6fec')

package() {
  install -dm755 "${pkgdir}"/usr/share/playframework2 "${pkgdir}"/usr/bin
  cp -r play-${_pkgver}-${_develver}/* "${pkgdir}"/usr/share/playframework2

  chgrp -R users "${pkgdir}"/usr/share/playframework2/{framework,repository}
  chmod -R g+rwx "${pkgdir}"/usr/share/playframework2/{framework,repository}
  chmod 755 "${pkgdir}"/usr/share/playframework2/play

  rm "${pkgdir}"/usr/share/playframework2/{play.bat,framework/build.bat,README.md,CONTRIBUTING.md}
  rm -rf "${pkgdir}"/usr/share/playframework2/samples

  ln -s /usr/share/playframework2/play "${pkgdir}"/usr/bin/play
}
