My Desktop Install
==================

Install
-------

Download Alpine standard iso, insert a usb drive, and extract image to drive.  
```
$ sudo dd if=alpine.iso of=/dev/sda
```  
Login as root, and do the following:  
```
$ SWAP_SIZE=0 setup-alpine # if you don't want swap or
$ setup-alpine # if you do want swap
us  # keyboard layout  
us  # variant  
alpinestep # hostname  
eth0  
dhcp  
<wifi name>  
<wifi password>  
n  # manual wifi config
<password>  # for root
<password>  
<time zone>
none  # proxy
f  # mirror f: fastest r: random e: edit file
no  # no user: add a user if you want. I just used root.
openssh # or dropbear  
yes  # ssh login as root
none 
vda  # disk
sys  # installation type
y  # erase disk
$ reboot  
```

Setup
-----

Login as root and do the following:  

## install xorg
```
$ setup-xorg-base  
```  
## install depencies
```
$ apk add git gcc ncurses musl-dev libx11-dev libxft-dev libxinerama-dev  #depencies
$ cd /root # or user directory
```
## install Dwm
```
$ git clone https://git.suckless.org/dwm
$ cd dwm
$ make  
$ make install
```  
## install DMenu
```
$ git clone https://git.suckless.org/dmenu
$ cd dmenu
$ make  
$ make install
```  
## install St
```
$ git clone https://git.suckless.org/st
$ cd st
$ make  
$ make install
```  
## install spleen font
``` 
$ apk add font-spleen
```
## final setup
```
$ cd /root
$ echo "startx" > .profile
$ echo "dwm" > .xinitrc 
$ reboot  
```
