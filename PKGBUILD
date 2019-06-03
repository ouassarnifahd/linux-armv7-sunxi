# ARMv7 sun8i-h3-h2plus

buildarch=4

pkgbase=linux-armv7-sunxi
_srcname=linux-5.1
_kernelname=${pkgbase#linux}
_desc="ARMv7 Allwinner H3/H2+ mainline kernel (Armbian sunxi-next patches + xradio_wlan driver)"
pkgver=5.1
pkgrel=1
arch=('armv7h')
url="http://www.kernel.org/"
license=('GPL2')
makedepends=('xmlto' 'docbook-xsl' 'kmod' 'inetutils' 'bc' 'git' 'uboot-tools' 'dtc')
options=('!strip' '!distcc')
source=("http://www.kernel.org/pub/linux/kernel/v5.x/${_srcname}.tar.xz"
        'config'
        
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0009-dt-bindings-update-the-Allwinner-GPADC-device-tree-b.patch'
        
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0011-iio-adc-sun4i-gpadc-iio-rename-A33-specified-registe.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0012-iio-adc-sun4i-gpadc-iio-rework-sampling-start-end-co.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0013-iio-adc-sun4i-gpadc-iio-rework-support-clocks-and-re.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0014-iio-adc-sun4i-gpadc-iio-rework-support-multible-sens.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0015-iio-adc-sun4i-gpadc-iio-rework-support-nvmem-calibra.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0016-iio-adc-sun4i-gpadc-iio-rework-add-interrupt-support.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0017-iio-adc-sun4i-gpadc-iio-add-support-for-H3-thermal-s.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0018-iio-adc-sun4i-gpadc-iio-add-support-for-A83T-thermal.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0019-arm-dts-sunxi-h3-h5-add-support-for-the-thermal-sens.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0020-arm-dts-sun8i-h3-add-support-for-the-thermal-sensor-.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/0021-arm-dts-sun8i-h3-add-thermal-zone-to-H3.patch'

        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/wifi-add-xradio.patch'
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/wifi-orangepi-zero-fix-xradio-interrupt.patch'
        'https://raw.githubusercontent.com/armbian/firmware/master/xr819/boot_xr819.bin'
        'https://raw.githubusercontent.com/armbian/firmware/master/xr819/fw_xr819.bin'
        'https://raw.githubusercontent.com/armbian/firmware/master/xr819/sdd_xr819.bin'
        
        'https://raw.githubusercontent.com/armbian/build/master/patch/kernel/sunxi-next/general-enable-allwinner-SoCs-SID-support.patch'

        'linux.preset'
        '60-linux.hook'
        '90-linux.hook')
md5sums=('15fbdff95ff98483069ac6e215b9f4f9'
         '313ab5455a480482e9125172e76d7c0d'
         
         '5ecc8ac84d8f3eaada152766dce06a8e'

         '8f84e273f8927587db12e1c8b62469e5'
         '7669e027afcaed15199c60b5317660b1'
         '6b89fa76f7beb209a699610abc22a8b5'
         '6d8af46ba8798af3288de3f6a2d72b80'
         'ae8f1d99753494e03dd5a6457ca01842'
         'cd90716c2b2d3c2d5d77cc300877935c'
         'acf91ed3db990fb7b1e28f6dfe70e1fd'
         'd965ea8f6ffc9c2dd09d92f4dea29569'
         '74c132e49953348df0ca7624b7bbbe7f'
         'e162fa063cb948662ee681a364dd094f'
         'e6741243f6298e629e3131ed5369baf5'

         '7169fdf75ba0ef4fbe8eddebb162b4f1'
         '91c6368be514b624e1ae2f8c73d3936c'
         '049abcb4768e92490f9fcafff114d1eb'
         '7a313e6957e635d9c1cd0d6902739d14'
         'e5d4afaf1a8c24f79f6764c289f1102f'
        
         '9a86e6d5b167c2dc2977db2c655e9083'

         '86d4a35722b5410e3b29fc92dae15d4b'
         'ce6c81ad1ad1f8b333fd6077d47abdaf'
         '3e2a512f8da5db5fe9f17875405e56a3')

# CROSS_COMPILING FLAGS
_toolchain=arm-linux-gnueabihf-
_arch=arm

prepare() {
  cd "${srcdir}/${_srcname}"
    
  # set the kernel build config
  cp ../config .config

  # apply patches
  patch -p1 < ../0009-dt-bindings-update-the-Allwinner-GPADC-device-tree-b.patch
  
  patch -p1 < ../0011-iio-adc-sun4i-gpadc-iio-rename-A33-specified-registe.patch
  patch -p1 < ../0012-iio-adc-sun4i-gpadc-iio-rework-sampling-start-end-co.patch
  patch -p1 < ../0013-iio-adc-sun4i-gpadc-iio-rework-support-clocks-and-re.patch
  patch -p1 < ../0014-iio-adc-sun4i-gpadc-iio-rework-support-multible-sens.patch
  patch -p1 < ../0015-iio-adc-sun4i-gpadc-iio-rework-support-nvmem-calibra.patch
  patch -p1 < ../0016-iio-adc-sun4i-gpadc-iio-rework-add-interrupt-support.patch
  patch -p1 < ../0017-iio-adc-sun4i-gpadc-iio-add-support-for-H3-thermal-s.patch
  patch -p1 < ../0018-iio-adc-sun4i-gpadc-iio-add-support-for-A83T-thermal.patch
  patch -p1 < ../0019-arm-dts-sunxi-h3-h5-add-support-for-the-thermal-sens.patch
  patch -p1 < ../0020-arm-dts-sun8i-h3-add-support-for-the-thermal-sensor-.patch
  patch -p1 < ../0021-arm-dts-sun8i-h3-add-thermal-zone-to-H3.patch

  patch -p1 < ../wifi-add-xradio.patch
  patch -p1 < ../wifi-orangepi-zero-fix-xradio-interrupt.patch

  patch -p1 < ../general-enable-allwinner-SoCs-SID-support.patch

  ####################
  # stop here
  # this is useful to patch the kernel
  #msg "stopping prepare"
  #return 1
  ####################

  # add pkgrel to extraversion
  sed -ri "s|^(extraversion =)(.*)|\1 \2-${pkgrel}|" Makefile

  # don't run depmod on 'make install'. we'll do this ourselves in packaging
  sed -i '2iexit 0' scripts/depmod.sh
}

build() {
  cd "${srcdir}/${_srcname}"

  # get kernel version
  make "ARCH=${_arch}" "CROSS_COMPILE=${_toolchain}" prepare

  # load configuration
  # configure the kernel. replace the line below with one of your choice.
  #make menuconfig # cli menu for configuration
  #make nconfig # new cli menu for configuration
  #make xconfig # x-based configuration
  #make oldconfig # using old config from previous kernel version
  # ... or manually edit .config

  # copy back our configuration (use with new kernel version)
  #cp ./.config ../${pkgbase}.config

  ####################
  # stop here
  # this is useful to configure the kernel
  #msg "stopping build"
  #return 1
  ####################

  #yes "" | make config

  # build!
  make "ARCH=${_arch}" "CROSS_COMPILE=${_toolchain}" ${makeflags} dtbs #zImage modules dtbs
}

_package() {
  pkgdesc="the linux kernel and modules - ${_desc}"
  depends=('coreutils' 'linux-firmware' 'kmod' 'mkinitcpio>=0.7')
  optdepends=('crda: to set the correct wireless channels of your country')
  backup=("etc/mkinitcpio.d/${pkgbase}.preset")
  provides=('kernel26' "linux=${pkgver}")
  conflicts=('linux')
  replaces=('linux-mvebu' 'linux-udoo' 'linux-sun4i' 'linux-sun5i' 'linux-sun7i' 'linux-usbarmory' 'linux-wandboard' 'linux-clearfog')
  install=${pkgname}.install

  cd "${srcdir}/${_srcname}"

  # get kernel version
  _kernver="$(make kernelrelease)"
  _basekernel=${_kernver%%-*}
  _basekernel=${_basekernel%.*}

  mkdir -p "${pkgdir}"/{boot,usr/lib/{modules,firmware/xr819}}
  make "ARCH=${_arch}" "CROSS_COMPILE=${_toolchain}" "INSTALL_MOD_PATH=${pkgdir}/usr" modules_install
  make "ARCH=${_arch}" "CROSS_COMPILE=${_toolchain}" "INSTALL_DTBS_PATH=${pkgdir}/boot/dtbs" dtbs_install
  cp arch/$_arch/boot/zImage "${pkgdir}/boot/zImage"
  cp ../boot_xr819.bin ../fw_xr819.bin ../sdd_xr819.bin "${pkgdir}/usr/lib/firmware/xr819"

  # make room for external modules
  local _extramodules="extramodules-${_basekernel}${_kernelname}"
  ln -s "../${_extramodules}" "${pkgdir}/usr/lib/modules/${_kernver}/extramodules"

  # add real version for building modules and running depmod from hook
  echo "${_kernver}" |
    install -Dm644 /dev/stdin "${pkgdir}/usr/lib/modules/${_extramodules}/version"

  # remove build and source links
  rm "${pkgdir}"/usr/lib/modules/${_kernver}/{source,build}

  # now we call depmod...
  depmod -b "${pkgdir}/usr" -F System.map "${_kernver}"

  # sed expression for following substitutions
  local _subst="
    s|%PKGBASE%|${pkgbase}|g
    s|%KERNVER%|${_kernver}|g
    s|%EXTRAMODULES%|${_extramodules}|g
  "

  # install mkinitcpio preset file
  sed "${_subst}" ../linux.preset |
    install -Dm644 /dev/stdin "${pkgdir}/etc/mkinitcpio.d/${pkgbase}.preset"

  # install pacman hooks
  sed "${_subst}" ../60-linux.hook |
    install -Dm644 /dev/stdin "${pkgdir}/usr/share/libalpm/hooks/60-${pkgbase}.hook"
  sed "${_subst}" ../90-linux.hook |
    install -Dm644 /dev/stdin "${pkgdir}/usr/share/libalpm/hooks/90-${pkgbase}.hook"
}

_package-headers() {
  pkgdesc="header files and scripts for building modules for linux kernel - ${_desc}"
  provides=("linux-headers=${pkgver}")
  conflicts=('linux-headers')
  replaces=('linux-mvebu-headers' 'linux-sun4i-headers' 'linux-sun5i-headers' 'linux-sun7i-headers' 'linux-usbarmory-headers' 'linux-wandboard-headers' 'linux-clearfog-headers')

  install -dm755 "${pkgdir}/usr/lib/modules/${_kernver}"

  cd "${srcdir}/${_srcname}"
  install -D -m644 Makefile \
    "${pkgdir}/usr/lib/modules/${_kernver}/build/Makefile"
  install -D -m644 kernel/Makefile \
    "${pkgdir}/usr/lib/modules/${_kernver}/build/kernel/Makefile"
  install -D -m644 .config \
    "${pkgdir}/usr/lib/modules/${_kernver}/build/.config"

  mkdir -p "${pkgdir}/usr/lib/modules/${_kernver}/build/include"

  for i in acpi asm-generic config crypto drm generated keys linux math-emu \
    media net pcmcia scsi soc sound trace uapi video xen; do
    cp -a include/${i} "${pkgdir}/usr/lib/modules/${_kernver}/build/include/"
  done

  # copy arch includes for external modules
  mkdir -p ${pkgdir}/usr/lib/modules/${_kernver}/build/arch/$_arch
  cp -a arch/$_arch/include ${pkgdir}/usr/lib/modules/${_kernver}/build/arch/$_arch/
  
  # copy files necessary for later builds, like nvidia and vmware
  cp Module.symvers "${pkgdir}/usr/lib/modules/${_kernver}/build"
  cp -a scripts "${pkgdir}/usr/lib/modules/${_kernver}/build"

  # fix permissions on scripts dir
  chmod og-w -R "${pkgdir}/usr/lib/modules/${_kernver}/build/scripts"
  mkdir -p "${pkgdir}/usr/lib/modules/${_kernver}/build/.tmp_versions"

  mkdir -p "${pkgdir}/usr/lib/modules/${_kernver}/build/arch/${_arch}/kernel"

  cp arch/${_arch}/Makefile "${pkgdir}/usr/lib/modules/${_kernver}/build/arch/${_arch}/"

  cp arch/${_arch}/kernel/asm-offsets.s "${pkgdir}/usr/lib/modules/${_kernver}/build/arch/${_arch}/kernel/"

  # add dm headers
  mkdir -p "${pkgdir}/usr/lib/modules/${_kernver}/build/drivers/md"
  cp drivers/md/*.h "${pkgdir}/usr/lib/modules/${_kernver}/build/drivers/md"

  # add inotify.h
  mkdir -p "${pkgdir}/usr/lib/modules/${_kernver}/build/include/linux"
  cp include/linux/inotify.h "${pkgdir}/usr/lib/modules/${_kernver}/build/include/linux/"

  # add wireless headers
  mkdir -p "${pkgdir}/usr/lib/modules/${_kernver}/build/net/mac80211/"
  cp net/mac80211/*.h "${pkgdir}/usr/lib/modules/${_kernver}/build/net/mac80211/"

  # add xfs and shmem for aufs building
  mkdir -p "${pkgdir}/usr/lib/modules/${_kernver}/build/fs/xfs"
  mkdir -p "${pkgdir}/usr/lib/modules/${_kernver}/build/mm"

  # copy in kconfig files
  for i in $(find . -name "Kconfig*"); do
    mkdir -p "${pkgdir}"/usr/lib/modules/${_kernver}/build/`echo ${i} | sed 's|/Kconfig.*||'`
    cp ${i} "${pkgdir}/usr/lib/modules/${_kernver}/build/${i}"
  done

  chown -R root.root "${pkgdir}/usr/lib/modules/${_kernver}/build"
  find "${pkgdir}/usr/lib/modules/${_kernver}/build" -type d -exec chmod 755 {} \;

  # strip scripts directory
  find "${pkgdir}/usr/lib/modules/${_kernver}/build/scripts" -type f -perm -u+w 2>/dev/null | while read binary ; do
    case "$(file -bi "${binary}")" in
      *application/x-sharedlib*) # libraries (.so)
        ${toolchain}strip ${strip_shared} "${binary}";;
      *application/x-archive*) # libraries (.a)
        ${toolchain}strip ${strip_static} "${binary}";;
      *application/x-executable*) # binaries
        ${toolchain}strip ${strip_binaries} "${binary}";;
    esac
  done

  # remove unneeded architectures
  rm -rf "${pkgdir}"/usr/lib/modules/${_kernver}/build/arch/{alpha,arc,arm26,arm64,avr32,blackfin,c6x,cris,frv,h8300,hexagon,ia64,m32r,m68k,m68knommu,metag,mips,microblaze,mn10300,openrisc,parisc,powerpc,ppc,s390,score,sh,sh64,sparc,sparc64,tile,unicore32,um,v850,x86,xtensa}
}

#_package-modules() {
#  pkgdesc="extra modules from legacy for linux kernel - ${_desc}"
#  provides=("linux-modules=${pkgver}")
#  conflicts=('linux-modules')
# 
#}

pkgname=("${pkgbase}" "${pkgbase}-headers")
for _p in ${pkgname[@]}; do
  eval "package_${_p}() {
    _package${_p#${pkgbase}}
  }"
done
