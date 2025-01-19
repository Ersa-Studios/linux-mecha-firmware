# Maintainer: The Mecha Team and Gagan Malvi <malvi@ersa.dev>

_pkgname=linux-mecha-firmware
pkgname=$_pkgname-master
pkgver=0.1.00.r0
pkgrel=1
pkgdesc="Proprietary firmware for Mecha Comet"
arch=(any)
url="https://github.com/Ersa-Studios/linux-mecha-firmware/"
license=('custom')
groups=()
depends=()
makedepends=('git') # 'bzr', 'git', 'mercurial' or 'subversion'
provides=("${pkgname%-master}")
conflicts=("${pkgname%-master}" linux-firmware)
replaces=()
backup=()
options=()
install=
source=("$_pkgname::git+https://github.com/Ersa-Studios/linux-mecha-firmware.git")
noextract=()
md5sums=('SKIP')

# Please refer to the 'USING VCS SOURCES' section of the PKGBUILD man page for
# a description of each element in the source array.

pkgver() {
	cd "$srcdir/${_pkgname}"

# The examples below are not absolute and need to be adapted to each repo. The
# primary goal is to generate version numbers that will increase according to
# pacman's version comparisons with later commits to the repo. The format
# VERSION='VER_NUM.rREV_NUM.HASH', or a relevant subset in case VER_NUM or HASH
# are not available, is recommended.

# Git, tags available
	printf "%s" "$(git describe --tags --long | sed 's/\([^-]*-\)g/r\1/;s/-/./g')"
}

package() {
	mkdir -p "${pkgdir}/usr/lib/"

	cp -dr "$srcdir/${_pkgname}/firmware/" "${pkgdir}/usr/lib/"
}
