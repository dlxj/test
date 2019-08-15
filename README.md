

https://raw.githubusercontent.com/dlxj/test/master/t.txt

wget -O t.txt --no-check-certificate https://raw.githubusercontent.com/dlxj/test/master/t.txt

Linux老司机如果身边有别的arch机器，你只需要：
1. 用tar把那台机器的根目录整个打包（记得加--one-file-system参数，防止把/proc, /dev等打进来）。
2. 找个新一点的live usb启动机器（grml就挺好）。
3. 分区，mkfs。
4. 整个包解压到根目录。
5. 修改/etc/fstab里的dev或UUID。
6. 支持UEFI的机器上没必要grub，把vmlinuz-linux和initramfs-linux-fallback.img复制到EFI分区，efibootmgr加个启动项即可。精简版的initramfs可以等系统安完之后再生成。
7. 收工。
以上流程其实适用于各种发行版。




Arch Linux


硬盘分区

分成两个区
sda1 512M的引导分区 dos 类型，分配空间的结束扇区输入 +512M
sda2 分全部可用空间

fsdisk -l
fsdisk /dev/sda


格式化
mkfs.fat -F32 /dev/sda1
mkfs.ext4 /dev/sda2



网络安装基本系统

mount  /dev/sda1  /mnt
pacstrap /mnt base base-devel



配置挂载表

genfstab -L /mnt >> /mnt/etc/fstab
cat /mnt/etc/fstab
# 会看到 /dev/sta2 被挂载到 /




转移控制权

arch-chroot /mnt
# 控制权交给刚装好的硬盘系统


如果以后我们的系统出现了问题，只要插入U盘并启动， 将我们的系统根分区挂载到了/mnt下（如果有efi分区也要挂载到/mnt/boot下），再通过这条命令就可以进入我们的系统进行修复操作。


安装必备软件
pacman -Sy
pacman -S git



设置主机名
vim /etc/hostname


设置网络

vim /etc/hosts
# 在最后追加内容

127.0.0.1	localhost
::1		localhost
127.0.1.1	这里是主机名.localdomain	这里是主机名



设置Root密码

passwd



安装Bootloader

pacman -S os-prober
pacman -S grub

grub-install --target=i386-pc /dev/sda

grub-mkconfig -o /boot/grub/grub.cfg

如果出错：
/etc/lvm/lvm.conf这个文件，找到use_lvmetad = 1将1修改为0，保存，重新配置grub



检查是否存在arch linux 入口

vim /boot/grub/grub.cfg


如果不对就重启再配一次，还是不行就 
pacman -S linux 
# 重新部署linux 内核



重启
exit
reboot






# 词类

独立语有：体言(名词、代名词、数量名词)、用言(动词、形容词、形容动词)、副词、连体词、接续词，感叹词

附属语有：助词、助动词

只有用言和助动词有活用

助词和连体词粘在体言后面，助动词粘在用言后面


# 句型

## 主语宾语之间接的是状语

**时间、地点、方法、交通，对象**
> 我现在学日语
> 我在新东方学日语
> 我用这本书学日语

