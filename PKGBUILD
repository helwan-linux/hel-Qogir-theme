pkgname=hel-Qogir-theme
pkgver=1.0
pkgrel=1
pkgdesc="Official Hel-Qogir theme for Helwan Linux"
arch=('any')
url="https://github.com/helwan-linux/hel-Qogir-theme"
license=('GPL3')
# دول hpm هيثبتهم للمستخدم تلقائياً من مستودعاتك
depends=('gtk-engine-murrine' 'gtk-engines') 
# دول السيرفر هيستخدمهم للبناء بس
makedepends=('sassc' 'git')
source=("git+https://github.com/vinceliuice/Qogir-theme.git"
        "_colors.scss"
        "_variables.scss")
sha256sums=('SKIP' 'SKIP' 'SKIP')

prepare() {
  cd Qogir-theme
  cp "$srcdir/_colors.scss" src/_sass/_colors.scss
  cp "$srcdir/_variables.scss" src/_sass/_variables.scss
  ./parse-sass.sh
}

package() {
  cd Qogir-theme
  # إنشاء المجلد يدوياً لضمان وجوده قبل تشغيل سكريبت التثبيت
  install -d "${pkgdir}/usr/share/themes"
  
  # التثبيت مع تحديد المسار الكامل والاسم
  ./install.sh -n hel-Qogir -d "${pkgdir}/usr/share/themes"
}
