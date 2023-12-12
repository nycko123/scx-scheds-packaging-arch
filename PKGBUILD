# Maintainer: Tejun Heo <tj@kernel.org>

pkgname=scx-scheds
pkgver=0.1.2
pkgrel=3
pkgdesc='Sched_ext schedulers'
url='https://github.com/sched-ext/scx'
arch=('x86_64')
license=('GPL2.0')
depends=('libelf' 'zlib' 'libbpf')
makedepends=('meson' 'bpf' 'pahole' 'rust' 'cargo')
provides=()
options=(!lto)
source=(https://github.com/sched-ext/scx/archive/refs/tags/v${pkgver}.tar.gz)
sha512sums=('2353e7e0051959834dcb1b4ded6dc23742ed395a764b03ca58496208134f89e96e76dd16c0257d03c86f084dbd4c9544daab366370a2f86fa6c2978fe6df606c')

build() {
  cd scx-${pkgver}
  arch-meson . build
  meson compile -C build
}

package() {
  cd scx-${pkgver}
  meson install -C build --destdir "${pkgdir}"
}

# vim: ts=2 sw=2 et:
