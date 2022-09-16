# debian-on-android
Script to install Ubuntu/Debian on Termux
## You Need
- [Termux](https://f-droid.org/packages/com.termux)
- [VNC Viewer](https://play.google.com/store/apps/details?id=com.realvnc.viewer.android) (If you want to install desktop)
## Install Ubuntu/Debian
- Install Ubuntu

      pkg update && pkg install proot-distro -y && curl -o /data/data/com.termux/files/usr/bin/ubuntu https://raw.githubusercontent.com/arfshl/debian-on-android/main/ubuntu && chmod +x /data/data/com.termux/files/usr/bin/ubuntu && proot-distro install ubuntu && ubuntu

- Install Debian

      pkg update && pkg install proot-distro -y && curl -o /data/data/com.termux/files/usr/bin/debian https://raw.githubusercontent.com/arfshl/debian-on-android/main/debian && chmod +x /data/data/com.termux/files/usr/bin/debian && proot-distro install debian && debian

## Install Desktop Environment
### Set up Pulseaudio

      pkg install pulseaudio -y && echo 'load-module module-native-protocol-tcp auth-ip-acl=127.0.0.1 auth-anonymous=1' >> $PREFIX/etc/pulse/default.pa && echo 'pulseaudio --start --exit-idle-time=-1' >> $PREFIX/etc/bash.bashrc

### Install Desktop Environment
**NOTE:Execute these command in PRoot shell (Shell you get after start Debian/Ubuntu), not Termux shell**
- XFCE

      apt update && apt install curl -y && curl -O https://raw.githubusercontent.com/arfshl/debian-on-android/main/xfce/xfce.sh && sh xfce.sh && rm xfce.sh

- MATE

      apt update && apt install curl -y && curl -O https://raw.githubusercontent.com/arfshl/debian-on-android/main/mate/mate.sh && sh mate.sh && rm mate.sh

- LXQt

      apt update && apt install curl -y && curl -O https://raw.githubusercontent.com/arfshl/debian-on-android/main/lxqt/lxqt.sh && sh lxqt.sh && rm lxqt.sh

- LXDE

      apt update && apt install curl -y && curl -O https://raw.githubusercontent.com/arfshl/debian-on-android/main/lxde/lxde.sh && sh lxde.sh && rm lxde.sh

- KDE 

      apt update && apt install curl -y && curl -o https://raw.githubusercontent.com/arfshl/debian-on-android/main/kde/kde.sh && sh kde.sh && rm kde.sh

## Start PRoot when open Termux immediately
- Ubuntu

      echo 'ubuntu' >> $PREFIX/etc/bash.bashrc

- Debian

      echo 'debian' >> $PREFIX/etc/bash.bashrc



