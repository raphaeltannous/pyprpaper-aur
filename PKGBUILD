# Maintainer: Raphael Tannous <raphaeltannous at proton dot me>
pkgname=pyprpaper
pkgver=0.2.1
pkgrel=1
pkgdesc="Randomly change wallpaper for given monitor(s) in hyprpaper."
arch=('x86_64')
url="https://github.com/rofe33/pyprpaper"
license=('GPL-3.0-only')
depends=(
  'python'
  'hyprpaper'
)
makedepends=(
  'python-build'
  'python-installer'
  'python-hatchling'
  'python-wheel'
)

source=(
  "${pkgname}-${pkgver}.tar.gz::https://github.com/rofe33/pyprpaper/archive/refs/tags/v${pkgver}.tar.gz"
)

sha256sums=(
  '487e06f2a850313440974f2aa41af7e8a86328883d102bb86e20a13343c0e6c3'
)

prepare() {
	cd "${pkgname}-${pkgver}"
}

build() {
	cd "${pkgname}-${pkgver}"
  python -m build --wheel --no-isolation
}

package() {
	cd "$pkgname-$pkgver"
  python -I -m installer --destdir="${pkgdir}" dist/*.whl
  install -D -m 644 -t "${pkgdir}/usr/share/licenses/${pkgname}" \
    "${srcdir}/${pkgname}-${pkgver}/LICENSE"
}
