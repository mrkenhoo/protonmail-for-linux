pkgname=protonmail-for-linux
pkgver=1.0.0_beta1
pkgrel=1
pkgdesc="An unofficial ProtonMail client for GNU/Linux"
url="https://github.com/mrkenhoo/${pkgname}"
license=('GPL')
arch=('x86_64')
makedepends=('npm')
source=("git+https://github.com/mrkenhoo/${pkgname}.git"
        protonmail-for-linux.desktop)
sha256sums=('SKIP'
            'SKIP')
options=(!strip)

build()
{
    cd ${srcdir}/${pkgname}
    npm install
    npm run package
}

package()
{
    [ ! -d "${pkgdir}/opt" ] && mkdir -pv "${pkgdir}/opt/${pkgname}"
    [ ! -d "${pkgdir}/usr/bin/" ] && mkdir -pv "${pkgdir}/usr/bin"
    [ ! -d "${pkgdir}/usr/share/applications" ] && mkdir -pv "${pkgdir}/usr/share/applications"

    find ${srcdir}/${pkgname}/out/protonmail-for-linux-linux-x64 -type d -exec install -v -d -Dm 755 {} "${pkgdir}/opt/${pkgname}" \;
    find ${srcdir}/${pkgname}/out/protonmail-for-linux-linux-x64 -type f -exec install -v -Dm 644 {} "${pkgdir}/opt/${pkgname}" \;

    install -Dm 644 -v "${srcdir}/${pkgname}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
}

