# Maintainer: Helwan Linux Team
pkgname="hel-Qogir-theme"
pkgver=1.0
pkgrel=1
pkgdesc="Qogir flat design theme for Helwan Linux"
arch=('any')
url="https://github.com/helwan-linux/hel-Qogir-theme"
license=('GPL3')
makedepends=('grep' 'sassc' 'git')
depends=('gtk-engines' 'gtk-engine-murrine')
options=('!strip')

# بنعتمد على المجلد المحلي اللي فيه الكود (المستودع بتاعك)
# مع ملفات الـ scss اللي إنت معدلها
source=("local_source::git+https://github.com/helwan-linux/hel-Qogir-theme.git"
        "_colors.scss"
        "_variables.scss")
sha256sums=('SKIP'
            'SKIP'
            'SKIP')

prepare() {
    # الدخول للمجلد اللي جابه الـ git
    cd "hel-Qogir-theme"
    
    # حقن ألوان حلوان في مسار الـ sass المظبوط
    cp "$srcdir/_colors.scss" src/_sass/_colors.scss
    cp "$srcdir/_variables.scss" src/_sass/_variables.scss
    
    # بناء الـ CSS بناءً على ألوانك
    ./parse-sass.sh
}

package() {
    cd "hel-Qogir-theme"
    
    # إنشاء المسار الأساسي
    install -dm755 "$pkgdir/usr/share/themes"

    # الخيارات دي (all و tweaks image) هي اللي بتخلي الحجم 12 ميجا
    # لأنها بتنسخ الصور (Assets) لكل إصدارات الثيم
    ./install.sh --name hel-Qogir \
                 --theme all \
                 --tweaks image square round \
                 --dest "$pkgdir/usr/share/themes"

    # مسح أي مجلدات فاضية لضمان نظافة الحزمة
    find "$pkgdir" -type d -empty -delete
}
