# Maintainer: tlm <13thSlayer@gmail.com>
# Contributor: Hilnus <itahilinus@hotmail.it>
pkgname=teamviewer-stable
pkgver=7.0.9350
pkgrel=3
pkgdesc="All-in-one solution for accessing PC's using the internet"
arch=('i686' 'x86_64')
url="http://www.teamviewer.com"
license="nonfree"
makedepends=('binutils')


if [ $CARCH == 'i686' ]; then
  source=("teamviewer_linux-${pkgver}.deb::http://www.teamviewer.com/download/version_7x/teamviewer_linux.deb" "teamviewer.desktop") 
  md5sums=('0af22c7d12f1559c9def98d2a572334f' 'b282ecbb72ff3cf82979defd8fc5a0c5')
  depends=('libsm' 'libxext' 'freetype2' 'libxtst')
elif [ $CARCH == 'x86_64' ]; then
  source=("teamviewer_linux_x64-${pkgver}.deb::http://www.teamviewer.com/download/version_7x/teamviewer_linux_x64.deb" "teamviewer.desktop")
  md5sums=('fea5988830dfadeffdf5e8aaa6548bbc' 'b282ecbb72ff3cf82979defd8fc5a0c5')
  depends=('lib32-libsm' 'lib32-libxext' 'lib32-glibc' 'lib32-freetype2' 'lib32-gcc-libs' \
  'lib32-alsa-lib' 'lib32-libx11' 'lib32-libxtst' 'lib32-libxdamage' 'lib32-libxfixes' \
  'lib32-libxcb' 'lib32-libxi' 'lib32-libxau' 'lib32-libxdmcp')
fi


package() {
	cd $srcdir
	[ $CARCH == "i686" ] && ar x teamviewer_linux-${pkgver}*
  [ $CARCH == "x86_64" ] && ar x teamviewer_linux_x64-${pkgver}*
	tar xvf data.tar.gz
	cp -R opt $pkgdir
	cp -R usr $pkgdir
	mkdir -p $pkgdir/usr/share/applications
	install -Dm644 $startdir/teamviewer.desktop $pkgdir/usr/share/applications/teamviewer.desktop
}
