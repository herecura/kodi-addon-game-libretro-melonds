# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-game-libretro-melonds
pkgver=0.8.2.4
_codename=Leia
pkgrel=1
pkgdesc="Libretro wrapper for Kodi's Game API"
arch=('x86_64')
url='https://github.com/kodi-game/game.libretro.melonds'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-game')
depends=('kodi-addon-game-libretro' 'libretro-melonds')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/kodi-game/game.libretro.melonds/archive/$pkgver-$_codename.tar.gz")
sha512sums=('67949da4ccffaf1557d6bf1835d5722fc61f81bde05d335a757673bc273e1610e978b85f56330e7da4f10c1135629c12890adacdf02fac0e67715f40a1978b3b')

build() {
    cd "game.libretro.melonds-$pkgver-$_codename"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1 \
        .
    make
}

package() {
    cd "game.libretro.melonds-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}

