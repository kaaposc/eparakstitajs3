# Maintainer: Māris Vilks <kaaposc@gmail.com>
pkgname=eparakstitajs3
pkgver=1.8.5
pkgrel=1
pkgdesc="Application software to sign and validate documents in EDOC and PDF formats."
arch=('x86_64')
url="https://www.eparaksts.lv"
license=('LicenseRef-E-PARAKSTĪTĀJS_3')
groups=('eparaksts')
depends=('gtk3' 'java-runtime' 'alsa-lib' 'libxtst')
optdepends=('python-nautilus: Nautilus context menu integration'
  'eparaksts-token-signing: eParaksts browser plugins'
  'latvia-eid-middleware: libraries for Latvia eID cards')
source=("https://www.eparaksts.lv/files/ep3updates/debian/pool/eparaksts/e/${pkgname}/${pkgname}_${pkgver}-jammy_amd64.deb"
  'dpkg'
  'eparakstitajs3.patch')
sha512sums=('04894349a56bf6581c3571338f5b2959a3d1ea4f7d78b071ce91502763f3f6e81949d22205aff7a780b2a7891177f28fb7ad2fcd76de60026bd0170241717e95'
            '2831607d41e6480620869264866711341917de093bdd0228c2b8efb041c9c9ae8861ca0564f1e9917dab888cad69eb81c97a7a5509b58adb2ce61eb7a95a3d4a'
            '67d4f8f231de49a78a7903c6a8990df035ad3e02a9247ccf87d92760a864095540831fb32030ad9a66ae6daf0200417c575d191aa43224b16516a88d1a69a2d9')

package() {

  tar -xf data.tar.zst -C "${pkgdir}"

  install -D "${pkgdir}/usr/share/doc/eparakstitajs3/copyright" "${pkgdir}/usr/share/licenses/$pkgname/LICENSE"

  install -D "${srcdir}/dpkg" "${pkgdir}/usr/lib/eparakstitajs3/bin/dpkg"

  cd "${pkgdir}"
  patch --forward --strip=0 <"${srcdir}/${pkgname}.patch"

}
