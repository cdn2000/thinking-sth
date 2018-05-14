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


