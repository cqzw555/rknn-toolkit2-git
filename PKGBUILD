# Maintainer: cqzw555<cqzw555 at 163 dot com>
pkgver=1.6.0
pkgbase=rknn-toolkit2-git
pkgname=(python-rknn-lite2 librknnapi rknn-server)
pkgrel=1
_py=cp311
pkgdesc='RKNN software stack can help users to quickly deploy AI models to Rockchip chips.'
url='https://github.com/airockchip/rknn-toolkit2'
makedepends=(python-installer git)
depends=(
    python-opencv
    python-ruamel-yaml
    python-psutil
    glibc
    gcc-libs
)

license=('BSD')
arch=('aarch64')
source=(git+${url})
sha256sums=('SKIP')

package_python-rknn-lite2(){
    _rknn_toolkit_lite2=rknn-toolkit2/rknn_toolkit_lite2
    python -m installer --destdir="${pkgdir}" ${srcdir}/${_rknn_toolkit_lite2}/packages/rknn_toolkit_lite2-${pkgver}-${_py}-${_py}-linux_aarch64.whl
    install -Dm644 ${srcdir}/rknn-toolkit2/LICENSE "${pkgdir}"/usr/share/licenses/${pkgname}/LICENSE
}
package_librknnapi(){
    _librknn_api=rknn-toolkit2/rknpu2/runtime/Linux/librknn_api
    install -Dm644 ${srcdir}/${_librknn_api}/aarch64/librknnrt.so ${pkgdir}/usr/lib/librknnrt.so
    install -Dm644 ${srcdir}/${_librknn_api}/include/rknn_api.h ${pkgdir}/usr/include/rknn_api.h
    install -Dm644 ${srcdir}/${_librknn_api}/include/rknn_custom_op.h ${pkgdir}/usr/include/rknn_custom_op.h
    install -Dm644 ${srcdir}/${_librknn_api}/include/rknn_matmul_api.h ${pkgdir}/usr/include/rknn_matmul_api.h
    install -Dm644 ${srcdir}/rknn-toolkit2/LICENSE "${pkgdir}"/usr/share/licenses/${pkgname}/LICENSE
}
package_rknn-server(){
    _rknn_server=rknn-toolkit2/rknpu2/runtime/Linux/rknn_server
    install -Dm644 ${srcdir}/${_rknn_server}/aarch64/usr/bin/restart_rknn.sh ${pkgdir}/usr/bin/restart_rknn.sh
    install -Dm644 ${srcdir}/${_rknn_server}/aarch64/usr/bin/start_rknn.sh ${pkgdir}/usr/bin/start_rknn.sh
    install -Dm644 ${srcdir}/${_rknn_server}/aarch64/usr/bin/rknn_server ${pkgdir}/usr/bin/rknn_server
    install -Dm644 ${srcdir}/rknn-toolkit2/LICENSE "${pkgdir}"/usr/share/licenses/${pkgname}/LICENSE
}
