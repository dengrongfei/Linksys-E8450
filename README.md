# Linksys-E8450

由于文件mtd3 文件大小超出web上传的25mb限制，我将其放在dropbox。

刷回原厂步骤：（先安装xshell和WinSCP）
1. 先联网，去到软件中心点击更新源，搜索安装 mtd-rw模块
2.xshell输入 echo c > /proc/sysrq-trigger 只要这个命令就行，等待重启
3.重启之后，此时WEB管理系统页面显示initramfs system
4.用WinSCP上传mtd 4个文件以及FW_RT3200_1.0.01.101415_prod.img镜像到/tmp 目录中
执行

过程放在上面的文件夹了

注意ssh是否有无提示报错，如果有，请恢复系统，重新按照步骤再试（会出现在mtd0-2的命令，以及提示没有mtd-rw这个模块）
之后
mtd -p 0x200000 write /tmp/FW_E8450_1.0.01.101415_prod.img /dev/mtd3

5.断电 ，之后按住复位键30秒插电松开。此时电源灯会一直闪，等会就恢复到原厂系统中
6. 由于使用别人备份的系统包，所以返回原厂系统后MAC地址以及默认密码，wifi名字都会与贴在底部的标签不同，不过目测不影响正常使用。
你可以试试mtd0,1,2 都是自己备份的，mtd3用别人备份的文件试试看，看mac地址会不会更改

此过程重要的是mtd3文件



Since the mtd3 file size exceeds the 25mb limit for web uploads, I share in dropbox.

Steps to flash back to the original factory: (install xshell and WinSCP first)
1. Connect to the Internet first, go to the software center and click on the update source, search and install the mtd-rw module
2. xshell input echo c > /proc/sysrq-trigger as long as this command, wait for restart
3. After restarting, the WEB management system page will displays initramfs system
4. Use WinSCP to upload mtd total 4 files and FW_RT3200_1.0.01.101415_prod.img image to /tmp directory
run command

placed in the above folder

Pay attention to whether ssh reports an error or not. If so, please restore the system and follow the steps to try again (the command that will appear in mtd0-2, and the prompt that there is no mtd-rw module)
after
mtd -p 0x200000 write /tmp/FW_E8450_1.0.01.101415_prod.img /dev/mtd3

5. Power off, then press and hold the reset button for 30 seconds to plug in and release. At this time, the power light will keep flashing, and it will restore to the original system after a while.
6. Since the mtd3 package backed up by others backup, the MAC address, default password, and wifi name will be different from the label on the bottom after returning to the original system, but the seem not affect normal use.
You can try mtd0, 1, and 2, which yourself, mtd3 backed up by others to see if the mac address will change.

Important for this process is the mtd3 file
