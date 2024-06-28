# Using the VoidLinuxInstaller Follow the Packages


https://github.com/Le0xFF/VoidLinuxInstaller
xbps-install -Suvy xbps
sudo xbps-install void-repo-nonfree void-repo-multilib void-repo-multilib-nonfree
xbps-install -Sun
xbps-install xorg xinit git make neofetch htop pipewire kitty noto-fonts-cjk bash-completion rofi
xbps-install -S base-devel libX11-devel libXft-devel libXinerama-devel fontconfig-devel freetype-devel 
xbps-install iwd blueman bluez network-manager-applet Thunar neovim libspa-bluetooth bluez-alsa CopyQ
xbps-install  noto-fonts-emoji noto-fonts-ttf noto-fonts-ttf-extra flatpak python3 python3-pip python3-mypy xarchiver rofi-emoji 


xbps-install fcitx fcitx-mozc fcitx-configtool libfcitx-gtk3 libfcitx-gtk libfcitx fcitx-libpinyin
https://www.youtube.com/watch?v=ptbFWnowvLo
https://dev.to/karyan40024/void-linux-gnome--4p3j#bluetooth_conf

git clone https://git.suckless.org/dwm
xbps-install cups cups-pk-helper cups-filters foomatic-db foomatic-db-engine
https://youtu.be/jcIhOGxSEiI?si=CUO3nOezFithWQuF

https://ivonblog.com/posts/install-void-linux/
https://www.youtube.com/watch?v=iKKAHWPMr10

xbps-install pavucontrol sxhkd stow lsd flameshot feh pywal  mtpfs gvfs-mtp gvfs-gphoto2 slock android-tools redshift
xbps-install pipewire alsa-utils wireplumber pulseaudio pipewire-pulse bluez-alsa
xbps-install vulkan-loader mesa-vulkan-intel intel-video-accel 

mkdir -p /etc/alsa/conf.d
 cd /etc/alsa/conf.d
sudo ln -s /usr/share/alsa/alsa.conf.d/50-pipewire.conf /etc/alsa/conf.d
sudo ln -s /usr/share/alsa/alsa.conf.d/99-pipewire-default.conf /etc/alsa/conf.d
edit a file
cd /etc/pulse
sudo nvim client.conf
autospawn = no and uncomment it
pipewire
pipewire-pulse
wireplumber 
autostart window manager sheetnaniganz

sudo usermod -a -G network audio video marks


stow --adopt -nvt ~ *
/etc/bash
if [ -f "$HOME" /.config/bash/.bash_profile ]; then
        . "$HOME"/.config/bash/.bash_profile
fi





https://gist.github.com/bastomiadi/abf27618341fc561735adfb17e586916


Download twrp recovery file and paste into platforms folder

use ur recovery file based on your android version

usr/lib/android-sdk/platforms-tools

ok. connect ur android using usb debugging

now type following commands

adb reboot bootloader

fastboot devices

fastboot oem unlock

Once your device boots into bootloader mode, type this into the command line.

fastboot flash recovery twrp-2.8.x.x-xxx.img

rename with recovery.img
fastboot boot path_of_img


xbps-install dbus qemu libvirt swtpmvirt-manager xbp bridge-utils
usermod -aG libvirt your_username
ln -s /etc/sv/dbus /var/service
ln -s /etc/sv/libvirtd /var/service
ln -s /etc/sv/libvirtd /var/service
ln -s /etc/sv/virtlogd /var/service
ln -s /etc/sv/polkitd /var/service/

oobee\BypassNRO
python3-mypy
export $(dbus-launch in /etc/profile to make it work lmao

touchpad setup
sudo mkdir /etc/X11/xorg.conf.d
nvim 70-synaptics.confsudo xbps-install void-repo-nonfree void-repo-multilib void-repo-multilib-nonfree
        Option "TapButton2" "3"
        Option "TapButton3" "2"
        Option "VertEdgeScroll" "on"
        Option "VertTwoFingerScroll" "on"
        Option "HorizEdgeScroll" "on"
        Option "HorizTwoFingerScroll" "on"
        Option "CircularScrolling" "on"
        Option "CircScrollTrigger" "2"
        Option "EmulateTwoFingerMinZ" "40"
        Option "EmulateTwoFingerMinW" "8"
        Option "CoastingSpeed" "0"
        Option "FingerLow" "30"
        Option "FingerHigh" "50"
        Option "MaxTapTime" "125"
        ...
EndSection

https://www.reddit.com/r/voidlinux/comments/13y6g86/pipewire_drives_me_nuts_on_void_a_rant_and_a_cry/

sudo xbps-install python3 python3-dbus python3-setuptools cmake  gtksourceview libbtrfsutil-devel
sudo xbps-install -S git cmake qt5 qt5-tools-devel qt5-svg gcc btrfs-progs qt6-base qt6-base-devel qt6-tools qt6-tools-devel qt5ct qt6ct


python setup.py install --record files.txt
sudo xbps-install -S libbtrfs libbtrfs-devel libbtrfsutil 

sudo rm $(cat files.txt)

https://www.schotty.com/Cheatsheets/Pywal_cheatsheet/#walvim

https://gitlab.com/btrfs-assistant/btrfs-assistant/-/tree/e7625d1cc604287b4fac31733a114ef854af157e

sudo swapoff -a

sudo dd if=/dev/zero of=/directory of swap bs=1G count=4
sudo mkswap /directory of swap
sudo swapon /direcotry of swap
grep SwapTotal /proc/meminfo -- get the amount of swap file

sudo xbps-install ufw gufw bleachbit

https://youtu.be/uL2FgJLzmCo?si=pwlGS070RHjkSGFs

libvirt apparmor error
sudo rm -rf /etc/apparmor.d/libvirt
sudo vim /etc/libvirt/qemu.conf
security_driver = "none"