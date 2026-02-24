pkgname=hel-Qogir-theme
pkgver=1.0
pkgrel=1
pkgdesc="helwan Qogir"
arch=('any')
url="https://github.com/helwan-linux/hel-Qogir-theme"
license=('GPL3')
depends=('gtk-engine-murrine' 'gtk-engines')
makedepends=('sassc' 'git')
source=("git+https://github.com/vinceliuice/Qogir-theme.git"
        "https://raw.githubusercontent.com/helwan-linux/theme/main/_colors.scss"
        "https://raw.githubusercontent.com/helwan-linux/theme/main/_variables.scss")
sha256sums=('SKIP' 'SKIP' 'SKIP')

prepare() {
  cd Qogir-theme
  # حقن ألوان وزوايا حلوان
  cp "$srcdir/_colors.scss" src/_sass/_colors.scss
  cp "$srcdir/_variables.scss" src/_sass/_variables.scss
  ./parse-sass.sh
}

package() {
  cd Qogir-theme
  # تثبيت السمة داخل الحزمة
  ./install.sh -n Helwan-Linux -d "$pkgdir/usr/share/themes"
}
