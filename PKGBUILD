# Maintainer: Raphael Tannous <raphaeltannous at proton dot me>
pkgname=pyprpaper
pkgver=0.2.0
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
  'f8f24bbcc5b69742db4444a0f9e6cbf5befec236d496eb3c2e4ecda87b77a4d9'
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
