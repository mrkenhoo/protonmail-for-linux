pkgname=protonmail-for-linux
pkgver=1.0.0
pkgrel=1
pkgdesc="An unofficial ProtonMail client for GNU/Linux"
url="https://github.com/mrkenhoo/${pkgname}"
license=('GPL')
arch=('x86_64')
makedepends=('npm')
source=("git+https://github.com/mrkenhoo/${pkgname}.git"
        protonmail-for-linux.desktop)
sha256sums=('SKIP')
options=(!strip)

build()
{
    cd ${srcdir}/${pkgname}
    npm install
    npm run package
}

package()
{
    [ ! -d "${pkgdir}/opt" ] && mkdir -pv ${pkgdir}/opt/${pkgname}
    [ ! -d "${pkgdir}/usr/bin/" ] && mkdir -pv ${pkgdir}/usr/bin

    for f in ${srcdir}/${pkgname}/out/protonmail-for-linux-linux-x64/*
    do
        install -Dm 644 ${f} ${pkgdir}/opt/${pkgname}
    done-

    install -Dm 644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
}
