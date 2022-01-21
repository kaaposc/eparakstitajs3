# Maintainer: Māris Vilks <kaaposc@gmail.com>
pkgname=eparakstitajs3
pkgver=1.6.1
pkgrel=1
pkgdesc="Application software to sign and validate documents in EDOC and PDF formats."
arch=('x86_64')
url="https://www.eparaksts.lv"
license=('custom:E-PARAKSTĪTĀJS 3')
groups=('eparaksts')
depends=('gtk2' 'gtk3' 'java-environment' 'libnet')
optdepends=('python-nautilus: Nautilus context menu integration'
            'eparaksts-token-signing: eParaksts browser plugins'
            'latvia-eid-middleware: libraries for Latvia eID cards')
source=("https://www.eparaksts.lv/files/ep3updates/debian/pool/eparaksts/e/${pkgname}/${pkgname}_${pkgver}_amd64.deb"
        'dpkg'
        'eparakstitajs3.patch')
sha512sums=('c383cfdc5e92b4c6c07a95e66a27516817df318cfa33a7957190039b19e5d52742182cb68d24255fb78a378c3a08931bc6a53a1bf19494c74e488c6ec1354bc7'
            '2831607d41e6480620869264866711341917de093bdd0228c2b8efb041c9c9ae8861ca0564f1e9917dab888cad69eb81c97a7a5509b58adb2ce61eb7a95a3d4a'
            '7f7a8884c72b291c9e83bb84d9d3ce74cf27e953acab6833d7c9a21341e9fe6f29ffcfc9022ff60cc8ecf8b07c2240ba0dca48b4e8ac05a82594129a8abd7387')

package() {

  tar -xJf data.tar.xz -C "${pkgdir}"

  install -D "${pkgdir}/usr/share/doc/eparakstitajs3/copyright" "${pkgdir}/usr/share/licenses/$pkgname/copyright"

  install -D "${srcdir}/dpkg" "${pkgdir}/opt/eparakstitajs3/dpkg"

  cd "${pkgdir}"
  patch --forward --strip=2 < "${srcdir}/${pkgname}.patch"
  
}

