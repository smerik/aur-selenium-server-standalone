# Maintainer: Erik van der Kolk <developer at smerik dot nl>
# Contributor: Tim Diels <limyreth at gmail dot com>
# Contributor: Sergej Pupykin <arch at sergej dot pp dot ru>
# Contributor: Nathaniel Harward <nharward at gmail dot com>
# Contributor: Martin Blumenstingl <martin.blumenstingl at googlemail dot com>
pkgname=selenium-server-standalone
pkgver=2.32.0
pkgrel=1
pkgdesc="Test automation server for web applications"
arch=('any')
url="http://seleniumhq.org/"
license=('APACHE')
depends=('java-runtime>=6')
backup=('etc/conf.d/selenium-server.conf')
source=("http://selenium.googlecode.com/files/selenium-server-standalone-$pkgver.jar"
        'selenium-server.conf.d'
        'selenium-server.rc'
        'selenium-server.service')
noextract=("selenium-server-standalone-$pkgver.jar")
md5sums=('a8eabb2d3d2aff63d8d794b0603a24c9'
         'e131aeac10172f338bba243652787a3f'
         '68f3c06be724919d8860da92053bdcb4'
         '77b72da5dc04ef9220923b83ad95d4a0')

build() {
  cd "$srcdir"
  install -D -m0644 selenium-server-standalone-$pkgver.jar \
    $pkgdir/usr/share/selenium-server/selenium-server-standalone.jar
  install -D -m0644 selenium-server.conf.d $pkgdir/etc/conf.d/selenium-server.conf
  install -D -m0755 selenium-server.rc $pkgdir/etc/rc.d/selenium-server
  install -D -m0644 selenium-server.service $pkgdir/usr/lib/systemd/system/selenium-server.service
  install -m755 -d $pkgdir/usr/bin/
  ln -s $JAVA_HOME/bin/java ${pkgdir}/usr/bin/selenium-server-java
}
