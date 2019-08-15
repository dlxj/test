

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

