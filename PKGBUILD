pkgname=hel-Qogir-theme
pkgver=1.0
pkgrel=1
pkgdesc="Official Helwan Linux theme based on Qogir"
arch=('any')
url="https://github.com/helwan-linux/hel-Qogir-theme"
license=('GPL3')
depends=('gtk-engine-murrine' 'gtk-engines')
makedepends=('sassc' 'git')
# هنا خلينا المصادر أسماء الملفات مباشرة
source=("git+https://github.com/vinceliuice/Qogir-theme.git"
        "_colors.scss"
        "_variables.scss")
sha256sums=('SKIP' 'SKIP' 'SKIP')

prepare() {
  cd Qogir-theme
  # الملفات بتكون موجودة في المجلد الرئيسي (srcdir)
  cp "$srcdir/_colors.scss" src/_sass/_colors.scss
  cp "$srcdir/_variables.scss" src/_sass/_variables.scss
  ./parse-sass.sh
}

package() {
  cd Qogir-theme
  ./install.sh -n Helwan-Linux -d "$pkgdir/usr/share/themes"
}
