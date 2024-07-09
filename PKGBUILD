pkgname=python-chibi
_pyname=chibi
pkgver=1.0.1
pkgrel=1
pkgdesc="library for proccess the format double undescore"
arch=('any')
url="https://pypi.org/project/chibi_donkey/"
license=('WTFPL')
groups=()
depends=("python")
makedepends=("python-setuptools")
source=("https://files.pythonhosted.org/packages/source/${_name::1}/${_name//-/_}/${_name//-/_}-$pkgver.tar.gz")
sha256sums=('218a1a707a9687df51480a720eb2d3db7730924e50320b0e77ad3f2899bf56e5')

build() {
  cd "$_pyname-$pkgver"
  python setup.py build
}

package() {
  cd $_pyname-${pkgver}
  python setup.py install --root="$pkgdir" --optimize=1
}
