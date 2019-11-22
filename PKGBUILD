_pkgname=pactrak
pkgname=pactrak-git
pkgver=3.0.1.r2.g5ea55a7
pkgrel=1
pkgdesc="Keeps a list of installed packages in a Gist at your GitHub account"
url="https://github.com/JoshH100/$pkgname"
arch=('x86_64' 'i686')
license=('GPL')
makedepends=('git')
depends=('pacman>=5.0' 'gist>=4.5.0')
source=("$pkgname::git+https://github.com/JoshH100/$_pkgname.git")
md5sums=('SKIP')

pkgver() {
    cd $pkgname
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/; s/-/./g'
}

package() {
  cd $srcdir/$pkgname
  
  # Install scrip
  install -Dm755 $_pkgname $pkgdir/usr/bin/$_pkgname

  # Install Hook
  install -Dm755  $_pkgname.hook $pkgdir/usr/share/libalpm/hooks/99-$_pkgname.hook
}
