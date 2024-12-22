# rtl88x2bu package for OpenWRT
Driver for a USB3 Wi-Fi adapter based on the **rtl8812bu / rtl8822bu** chipsets
  
**Tip: [select branch](https://github.com/erintera/openwrt-rtl8812bu-package/branches) for OpenWRT version you're using.**  
  
Used driver: https://github.com/morrownr/88x2bu-20210702  
Thanks to [Jason](https://gitlab.com/_jason/openwrt-rtl8812bu-package)  
This was created using the rtl8812au-ct package as a guide (but it's not for 8812au!)  
  
*disclaimer: I have no idea what I'm doing. Use at your own risk.*

## Usage
This is an OpenWRT package. Place this project's files in your OpenWRT source directory under `package/kernel/rtl88x2bu/` and run `make menuconfig` *from OpenWRT source directory* to include it in your build.  
  
**Reboot your OpenWRT device (with adapter connected) after installing driver.**  

## Kernel module parameters (for advanced users)
Read https://github.com/morrownr/88x2bu-20210702/blob/6c2ca754ec23dcf67993f036e76cce562e1e329d/88x2bu.conf for parameters documentation  
  
**OpenWRT notes:**  
- Use ``88x2bu`` , not ``options 88x2bu``
- File location is ``/etc/modules.d/rtl88x2bu.conf`` , not ``/etc/modprobe.d/88x2bu.conf``
  
Example: add ``88x2bu rtw_drv_log_level=0 rtw_led_ctrl=0`` to **/etc/modules.d/rtl88x2bu.conf**



Ссылка на исправление ошибок и сам текст:


[Skillbox Media](https://programmersought.com/article/58058010014/#google_vignette/ "Всплывающая подсказка")

https://programmersought.com/article/58058010014/#google_vignette

solution

Find the way through the foreign forum and GitHub [Portal]

1. VI U-boot / makefile Add KBUILD_CFLAGS + = $ (CALL CC-Disable-Warning, Address-of-Packed-Member) Theore in theory, as long as there is no IF judgment affects the location of this sentence;

2. VI U-BOOT / ARM / ARM / DTS / MAKEFILE CONFIG_ARCH_ROCKCHIP to delete the error DTB; generally RK3036-SDK.DTB, RK3188-Radxarock.dtb, rk3368-lion.dtb, rk3368-sheep.dtb, rk3368 -geekbox.dtb, rk3368-px5-evb.dtb, I remember there is still 1 ~ 2 reports wrong DTB files, please delete it according to the error;

3. VI U-Boot / Scripts / DTC / DTC-LEXER.L Search YYLOC to delete the -YylType YYLLOC;

4.vi u-boot / scripts / dtc / dtc-lexer.lex.c_shipped Search YYLLOC to delete the -YylType YYLLOC;

5. Rehelation, live └ (^ o ^) ┘ ▼ ▼▼

Тут у нас немного исходников от u-boot 

[U-BOOT](https://docs.u-boot.org/en/latest/board/rockchip/rockchip.html/ "Всплывающая подсказка")

https://docs.u-boot.org/en/latest/board/rockchip/rockchip.html

[Manual_build](https://github.com/mirobiala/rtl88x2bu-cl?ysclid=m4zcc56jo1171418288/ "Всплывающая подсказка")

https://github.com/mirobiala/rtl88x2bu-cl?ysclid=m4zcc56jo1171418288

https://wiki.friendlyelec.com/wiki/index.php/How_to_Build_FriendlyWrt#RK3328_Based_Boards

https://mirror-03.infra.openwrt.org/releases/23.05.4/targets/rockchip/armv8/
