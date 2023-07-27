# -*- mode: pkgbuild -*-
# Maintainer  : Jason Clark <mithereal@gmail.com>
#



pkgname=watermark-remover-git
_pkgname=${pkgname%-git}
_reponame=bin
pkgver=r1.1
pkgrel=1
pkgdesc="Remove Watermark from an Image"
arch=('any')
url="https://github.com/data-twister/Watermark-Removal-Pytorch"
license=('MIT')
depends=('python' 'python-torch' 'python-torchvision' 'python-numpy' 'python-matplotlib' 'python-tqdm' 'python-pygobject' 'python-pillow')
makedepends=(git)
provides=(watermark-remover-git)
conflicts=(watermark-remover)
source=("git+https://github.com/data-twister/Watermark-Removal-Pytorch")
md5sums=('SKIP')

install="${pkgname}.install"

pkgver() {
  cd "${srcdir}/${_pkgname}"

  # Get the version number.
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
    cd "$srcdir"

    install -D -m644 "$_reponame/LICENSE" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
    install -D -m755 "$_reponame/${_pkgname}" "$pkgdir/usr/lib/${_pkgname}"
    install -D -m755 "$_reponame/remove-watermark" "$pkgdir/usr/bin/remove-watermark"
}