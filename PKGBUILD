# -*- mode: pkgbuild -*-
# Maintainer  : Jason Clark <mithereal@gmail.com>
#



pkgname=watermark-remover-git
_pkgname=${pkgname%-git}
pkgver=r69.3b7fdd1
pkgrel=1
pkgdesc="Remove Watermark from an Image"
arch=('any')
url="https://github.com/data-twister/Watermark-Removal-Pytorch"
license=('MIT')
depends=('python' 'python-pytorch' 'python-torchvision' 'python-numpy' 'python-matplotlib' 'python-tqdm'  'python-pillow' 'python-gobject')
makedepends=(git)
provides=(watermark-remover-git)
conflicts=(watermark-remover)
source=("git+https://github.com/data-twister/Watermark-Removal-Pytorch")
md5sums=('SKIP')


pkgver() {
  cd "${srcdir}"

  # Get the version number.
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "${srcdir}/Watermark-Removal-Pytorch"

    install -D -m644 "LICENSE" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"

    install -D -m755 "remove-watermark" "$pkgdir/usr/bin/remove-watermark"

    mkdir -p $pkgdir/usr/lib/$pkgname

    rsync -av  --no-o --no-g ${srcdir}/Watermark-Removal-Pytorch/library/ $pkgdir/usr/lib/$pkgname

}
