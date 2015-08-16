# custom variables
_hkgname=json-tools
_licensefile=LICENSE

# PKGBUILD options/directives
pkgname=json-tools
pkgver=0.3.1
pkgrel=27
pkgdesc="A collection of JSON tools"
url="http://hackage.haskell.org/package/${_hkgname}"
license=("BSD3")
arch=('i686' 'x86_64')
makedepends=("ghc=7.0.3-2"
             "haskell-attojson=0.5.10-21"
             "haskell-convertible-text=0.3.0.10-1"
             "haskell-data-object=0.3.1.7-1"
             "haskell-data-object-json=0.3.1.6-24"
             "haskell-tar=0.3.1.0-5")
depends=()
options=('strip')
source=("http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz")

sha256sums=("c32fa96a41e2a6a0f8db867568286b78665398596005707bd037879dbbea4daf")

# PKGBUILD functions
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    
    runhaskell Setup configure -O --prefix=/usr --docdir=/usr/share/doc/${pkgname}
    runhaskell Setup build
}

package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
}
