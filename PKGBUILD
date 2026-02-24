pkgname=hel-Qogir-theme
pkgver=1.0
pkgrel=1
pkgdesc="Official Hel-Qogir theme for Helwan Linux"
arch=('any')
url="https://github.com/helwan-linux/hel-Qogir-theme"
license=('GPL3')
depends=('gtk-engine-murrine' 'gtk-engines')
makedepends=('sassc' 'git')
source=("git+https://github.com/vinceliuice/Qogir-theme.git"
        "_colors.scss"
        "_variables.scss")
sha256sums=('SKIP' 'SKIP' 'SKIP')

prepare() {
  cd Qogir-theme
  # حقن ملفاتك في مسار السورس
  cp "$srcdir/_colors.scss" src/_sass/_colors.scss
  cp "$srcdir/_variables.scss" src/_sass/_variables.scss
  ./parse-sass.sh
}

package() {
  cd Qogir-theme
  # التثبيت باسم hel-Qogir
  ./install.sh -n hel-Qogir -d "$pkgdir/usr/share/themes"
}
