# Maintainer: Raphael Tannous <raphaeltannous at proton dot me>
pkgname=pyprpaper
pkgver=0.3.0
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
  '43cf7b7abe045e8a44eec97c2bbeb97e840e39f61dbfdf68afdf0ee163b54bdc'
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
