pkgname=hel-Qogir-theme
pkgver=1.0
pkgrel=1
pkgdesc="Official Helwan Linux theme - Built from Qogir source"
arch=('any')
url="https://github.com/helwan-linux/hel-Qogir-theme"
license=('GPL3')
depends=('gtk-engine-murrine' 'gtk-engines')
makedepends=('sassc' 'git')
# استخدام المصادر المحلية + السورس الأصلي
source=("git+https://github.com/vinceliuice/Qogir-theme.git"
        "_colors.scss"
        "_variables.scss")
sha256sums=('SKIP' 'SKIP' 'SKIP')

prepare() {
  cd Qogir-theme
  # حقن التعديلات في مسار الساس الصحيح بناءً على الدياجرام
  cp "$srcdir/_colors.scss" src/_sass/_colors.scss
  cp "$srcdir/_variables.scss" src/_sass/_variables.scss
  # تحويل الساس إلى CSS
  ./parse-sass.sh
}

package() {
  cd Qogir-theme
  # بناء الحزمة وتوجيهها لمجلد الـ package
  ./install.sh -n Helwan-Linux -d "$pkgdir/usr/share/themes"
}
