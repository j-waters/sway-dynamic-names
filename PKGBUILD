_pkgname=sway-dynamic-names
pkgname=$_pkgname-git
pkgrel=1
pkgver=0.0.1
pkgdesc="Dynamically update the name of each Sway WM workspace using font-awesome icons"
url="https://github.com/j-waters/sway-dynamic-workspace-names"
depends=('python-click'
         'python-yaml'
         'python-i3ipc'
         'python-fontawesome'
         'python-xdg')
makedepends=('git' 'python-setuptools')
conflicts=()
provides=()
license=('MIT')
arch=('any')
source=("${_pkgname}::git+${url}.git")
md5sums=("SKIP")


pkgver() {
    cd "$srcdir/$_pkgname"
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
    cd "${srcdir}/${_pkgname}"
    python setup.py build
}

package() {
    cd "${srcdir}/${_pkgname}"
    python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
}
