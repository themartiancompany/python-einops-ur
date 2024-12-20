# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: Butui Hu <hot123tea123@gmail.com>

_py="python"
_pkg=einops
pkgname="${_py}-${_pkg}"
pkgver=0.8.0
pkgrel=1
pkgdesc=(
  'Deep learning operations reinvented'
  '(for pytorch, tensorflow, jax and others)'
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'any'
)
_http="https://github.com"
_ns="arogozhnikov"
url="${_http}/${_ns}/${_pkg}"
license=(
  'MIT'
)
depends=(
  "${_py}"
)
makedepends=(
  "${_py}-build"
  "${_py}-hatchling"
  "${_py}-installer"
  "${_py}-wheel"
)

source=(
  "${_pkg}-${pkgver}.tar.gz::${url}/archive/refs/tags/v${pkgver}.tar.gz"
)
sha512sums=(
  '0805f5b11b97925090f92cde3f0b4e36c6109300658e15c0c4271a5ae30dfcd85fe18f4faca1acee2eaadab07cac05e81ae3b88c6a7b8970bfd297b539725d67'
)

build() {
  cd \
    "${_pkg}-${pkgver}"
  "${_py}" \
    -m \
      build \
    --wheel \
    --no-isolation
}

package() {
  cd \
    "${_pkg}-${pkgver}"
  "${_py}" \
    -m \
      installer \
    --destdir="${pkgdir}" \
    "dist/"*".whl"
  install \
    -Dm644 \
    "LICENSE" \
    -t \
    "${pkgdir}/usr/share/licenses/${pkgname}"
}
# vim:set ts=2 sw=2 et:
