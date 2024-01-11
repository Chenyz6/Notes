# Ubuntu22.04 安装QEMU麒麟

1）sudo apt install qemu-system-arm -y

2）准备三个文件

![image-20240105185845647](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240105185845647.png)

qemu：使用qemu-system-aarch64虚拟机环境

rootfs.qcow2：虚拟磁盘镜像文件，可使用qemu-img创建（2.2）

qemu_efi.df：QEMU的UEFI固件，可在linaro网站上下载，https://releases.linaro.org/components/kernel/uefi-linaro/latest/release/qemu64/QEMU_EFI.fd

system.iso：操作系统镜像，请自行准备。

3）创建qcow2虚拟镜像

qemu-img create -f qcow2 rootfs.qcow2 50G

4）安装脚本

qemu-system-aarch64 \
 -m 4096 \
 -cpu cortex-a72 -smp 4,cores=4,threads=1,sockets=1 \
 -M virt \
 -bios ./QEMU_EFI.fd \
 -net nic,model=pcnet \
 -device nec-usb-xhci \
 -device usb-kbd \
 -device usb-mouse \
 -device VGA \
 -drive if=none,file=./KylinSec-Desktop-3.4-4A-2206-301007-aarch64.iso,id=cdrom,media=cdrom \
 -device virtio-scsi-device \
 -device scsi-cd,drive=cdrom \
 -drive if=none,file=./rootfs.qcow2,id=hd0 \
 -device virtio-blk-device,drive=hd0

其中-bios指定UEFI固件文件，-drive指定安装镜像和系统盘。QEMU_UEFI.fd，armrootfs.qcow2，Kylin-Desktop-V10-Release-Build1-20200710-arm64.iso三个镜像文件的位置必须在当前目录下，不然就需要指定其绝对路径。

5）安装过程可能会提示

failed to find romfile "vgabios-stdvga.bin"

解决方案：

sudo apt-get install vgabios

sudo ln -s /usr/share/vgabios/vgabios.stdvga.bin  /usr/share/qemu/vgabios-stdvga.bin

6）启动脚本

qemu-system-aarch64 \
 -m 4096 \
 -cpu cortex-a72 -smp 4,cores=4,threads=1,sockets=1 \
 -M virt \
 -bios ./QEMU_EFI.fd \
 -device nec-usb-xhci \
 -device usb-kbd \
 -device usb-mouse \
 -device VGA \
 -device virtio-scsi-device \
 -drive if=none,file=./rootfs.qcow2,id=hd0 \
 -device virtio-blk-device,drive=hd0