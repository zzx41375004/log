
## Android 9 mmc 可执行文件测试

### 在虚拟机上的测试

安装好`Android Studio`4.1 版本

下载Andorid9的虚拟机，Pixel 2 XL API 28， CPU/ABI: x86_64; Target: Android 9.0 (Google APIs)

### adb root 

```
adb root
```
`adb root`为必要步骤，若未adb root，则用`adb shell`连接虚拟机后`su -`无权  
`adb root`的目的在于使`adb shell`这个shell进程具有root权限
### adb push

用adb连接Andorid9 虚拟机, 在下列路径下   
` ···\Project1-origin\test2.0\app\src\main\assets\x86_64>`
``` 
abd push ./mmc /data/
adb shell
cd /data/
ls -l 
```
在adb shell里查看mmc  （-rw-rw-rw-）
```
su -
chmod +x mmc
```

mmc  （-rwxrwxrwx）

执行*mmc*

```
generic_x86_64:/data # ./mmc -h
Usage:
        mmc extcsd read <device>
                Print extcsd data from <device>.
        mmc writeprotect boot get <device>
                Print the boot partitions write protect status for <device>.
        mmc writeprotect boot set <device>
                Set the boot partitions write protect status for <device>.
                This sets the eMMC boot partitions to be write-protected until
                the next boot.
··· ···
```

在Android 11.0 API 30 x86  

用adb root后也可以正常使用`su -`
