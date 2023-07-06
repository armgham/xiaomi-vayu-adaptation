# Maintainer: Arman Ghamgosar <armgham92@gmail.com>

pkgname=xiaomi-vayu-adaptation
provides=(halium11-post-install)
conflicts=(halium11-post-install)
pkgver=1$(date +%y%m%d)
pkgrel=1
pkgdesc="Manjaro libhybris adaptation for xiaomi vayu"
arch=('any')
url="https://github.com/armgham/xiaomi-vayu-adaptation"
license=('GPL')
depends=('gzip' 'glibc-locales' 'wget' 'systemd')
makedepends=('git')
source=("xiaomi-vayu-adaptation::git+https://github.com/armgham/xiaomi-vayu-adaptation.git")
install=$pkgname.install
md5sums=('SKIP')

package() {
    mv "${srcdir}/xiaomi-vayu-adaptation/xiaomi-vayu-adaptation.sh" "${srcdir}/xiaomi-vayu-adaptation/xiaomi-vayu-adaptation"

    mkdir -p "${pkgdir}/usr/bin/"
    install -Dm755 "${srcdir}/xiaomi-vayu-adaptation/xiaomi-vayu-adaptation" -t "${pkgdir}/usr/bin/"

    mkdir -p "${pkgdir}/usr/lib/systemd/system/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/xiaomi-vayu-adaptation.service" -t "${pkgdir}/usr/lib/systemd/system/"

    mkdir -p "${pkgdir}/usr/lib/sysusers.d/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/android.conf" -t "${pkgdir}/usr/lib/sysusers.d/"

    cp -r "${srcdir}/xiaomi-vayu-adaptation/droid-vendor-overlay" -t "${pkgdir}/usr/lib/"

    #mkdir -p "${pkgdir}/usr/lib/modules/"
    #cp -r "${srcdir}/xiaomi-vayu-adaptation/vendor" -t "${pkgdir}/usr/lib/modules"

    mkdir -p ${pkgdir}/etc/phosh/
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/phoc.ini" -t "${pkgdir}/etc/phosh/"

    mkdir -p "${pkgdir}/etc/udev/rules.d/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/70-vayu.rules" -t "${pkgdir}/etc/udev/rules.d/"

    #mkdir -p "${pkgdir}/etc/systemd/user/pulseaudio.d/"
    #install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/10-env.conf" -t "${pkgdir}/etc/systemd/user/pulseaudio.service.d/"

    #mkdir -p "${pkgdir}/etc/pulse/"
    #install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/arm_droid_card_custom.pa" -t "${pkgdir}/etc/pulse/"

    #mkdir -p "${pkgdir}/etc/modules-load.d/"
    #install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/performance.conf" -t "${pkgdir}/etc/modules-load.d/"
    #install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/connectivity.conf" -t "${pkgdir}/etc/modules-load.d/"

    mkdir -p "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/boot.img" -t "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/dtbo.img" -t "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/vbmeta.img" -t "${pkgdir}/boot/"

    #mkdir -p "${pkgdir}/usr/lib/systemd/system/"
    #install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/brightness.service" "${pkgdir}/usr/lib/systemd/system/"
    #install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/pbhelper.service" "${pkgdir}/usr/lib/systemd/system/"
    #install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/ssh-fix.service" "${pkgdir}/usr/lib/systemd/system/"

    mkdir -p "${pkgdir}/usr/lib/systemd/system/bluebinder.service.d/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/10-after.conf" "${pkgdir}/usr/lib/systemd/system/bluebinder.service.d"

    mkdir -p "${pkgdir}/var/lib/bluetooth/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/board-address" -t "${pkgdir}/var/lib/bluetooth/"

    #mkdir -p "${pkgdir}/usr/bin/"
    #install -Dm755 "${srcdir}/xiaomi-vayu-adaptation/pbhelper" "${pkgdir}/usr/bin/pbhelper"
}

