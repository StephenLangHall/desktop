My Desktop Install
==================



Install
-------

Download Alpine standard iso, insert a usb drive, and extract image to drive.  
Login as root, and do the following:  
```
$ SWAP_SIZE=0 setup-alpine # if you don't want swap  
us  # keyboard layout  
us  # variant  
alpinestep # hostname  
eth0  
dhcp  
<wifi name>  
<wifi password>  
n  # manual config
<password>  # for root
<password>  
America/Louisville  # Time zone
none  # proxy
f  # mirror f: fastest r: random e: edit file
no  # no user: add a user if you want. I just used root.
openssh  
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
## install depencies
```
$ apk add zsh vim git gcc unzip ncurses musl-dev libx11-dev libxft-dev  #depencies
$ cd /root # or user directory
$ git clone https://github.com/stephenlanghall/desktop.git  # source for stuff
$ unzip desktop.zip
```
## install xorg
```
$ setup-xorg-base  #install xorg
```
## install Dwm
```
$ cd .s/dwm # my custom build; you can also clone it yourself (https://git.suckless.org/dwm) 
$ make  
$ make install
```
## install DMenu
```
$ cd ../dmenu  # or https://git.suckless.org/dwm
$ make  
$ make install
```
## install St
```
$ cd ../st  # or https://git.suckless.org/dmenu
$ make  
$ make install
```
## install tewi-font
``` 
$ cd ../tewi-font  # https://github.com/lucy/tewi-font
$ mkdir /root/.fonts  
$ make  
$ ln out /root/.fonts/tewi
```
## final setup
```
$ cd /root  
$ chsh -s /bin/zsh  
$ clear > /etc/motd  #optional
$ clear > /etc/issue  #optional
$ reboot  
```
