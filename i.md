My Desktop Install
==================



Install
-------

Download Alpine standard iso, insert a usb drive, and extract image to drive.  
Login as root, and do the following:  
<code>
$ SWAP_SIZE=0 setup-alpine # if you don't want swap  
us  # keyboard layout  
us  # variant  
alpinestep # hostname  
eth0  
dhcp  
\<wifi name>  
\<wifi password>  
n  # manual config
\<password>  # for root
\<password>  
America/Louisville  # Time zone
none  # proxy
f  # mirror f: fastest r: random e: edit file
no  
openssh  
yes  # ssh login as root
none 
vda  # disk
sys  # installation type
y  # erase disk
$ reboot  
</code>

Setup
-----

Login as root and do the following:  
<code>
$ apk add zsh vim git gcc unzip ncurses musl-dev libx11-dev libxft-dev  #depencies
$ git clone https://github.com/stephenlanghall/desktop.git  # source for stuff
$ unzip desktop.zip  
$ setup-xorg-base  
$ cd .s/dwm  
$ make  
$ make install  
$ cd ../dmenu  
$ make  
$ make install  
$ cd ../st  
$ make  
$ make install  
$ cd ../tewi-font  
$ mkdir /root/.fonts  
$ make  
$ ln out /root/.fonts/tewi  
$ cd /root  
$ chsh -s /bin/zsh  
$ clear > /etc/motd  #optional
$ clear > /etc/issue  #optional
$ reboot  
</code>
