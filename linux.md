# Linux 经验
### disable notebook's keyboard.
    vi /boot/grub2/grub.cfg
  
    linux16 /vmlinuz-3.10.0-693.21.1.el7.x86_64 root=/dev/mapper/centos-root ro crashkernel=auto rd.lvm.lv=centos/root rd.lvm.lv=centos/swap rhgb quiet i8042.nokbd 
  
find above line and add: i8042.nokbd.
  
> this way maybe affort X11,so use xinput better:

    xinput list
    xinput disable xx

### switch from graphical to command line.
    sudo systemctl set-default multi-user.target
    sudo systemctl set-default graphical.target

### LANG 之迷
我已经的/etc/locale.conf设置好了LANG,如下：  

    LANG="zh_CN.UTF-8"
但启动到命令行后，echo $LANG，变成了en_US.UTF-8  

查原因后发现在/etc/profile.d/lang.sh中，作了修改。  

当consoletype='VT'时，直接把LANG设置成en_us.  

为验证这点，把启动切换到图形方式，LANG就不变了。zh_CN  


