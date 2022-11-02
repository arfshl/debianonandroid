# debian-on-android
Script to install Ubuntu/Debian on Termux
## You Need
- [Termux](https://f-droid.org/packages/com.termux)
- [VNC Viewer](https://play.google.com/store/apps/details?id=com.realvnc.viewer.android) (If you want to install desktop)
## Install Ubuntu/Debian
- Install Ubuntu

      pkg update && apt dist-upgrade && pkg install proot-distro -y && proot-distro install ubuntu && clear && echo 'To start Ubuntu use proot-distro login ubuntu command'

- Install Debian

      pkg update && apt dist-upgrade && pkg install proot-distro -y && proot-distro install debian && clear && echo 'To start Debian use proot-distro login debian command'

### PRoot Login command
- Ubuntu

      proot-distro login ubuntu

- Debian

      proot-distro login debian

### [OPTIONAL] PRoot Auto-Login
- Ubuntu

      echo 'proot-distro login ubuntu' >> $PREFIX/etc/bash.bashrc

- Debian

      echo 'proot-distro login debian' >> $PREFIX/etc/bash.bashrc

### Repository setup, update package, and set timezone

      apt update && apt dist-upgrade && dpkg-reconfigure tzdata

## Install Graphical Environment
### Set up Pulseaudio

      pkg install pulseaudio -y && echo 'pulseaudio --start --load="module-native-protocol-tcp auth-ip-acl=127.0.0.1 auth-anonymous=1" --exit-idle-time=-1' >> $PREFIX/etc/bash.bashrc

### Desktop Environment
- KDE 

      curl -o https://raw.githubusercontent.com/arfshl/debian-on-android/main/kde.sh && sh kde.sh && rm kde.sh

- XFCE

      curl -O https://raw.githubusercontent.com/arfshl/debian-on-android/main/xfce.sh && sh xfce.sh && rm xfce.sh

- MATE

      curl -O https://raw.githubusercontent.com/arfshl/debian-on-android/main/mate.sh && sh mate.sh && rm mate.sh

- LXQt

      curl -O https://raw.githubusercontent.com/arfshl/debian-on-android/main/lxqt.sh && sh lxqt.sh && rm lxqt.sh

- LXDE

      curl -O https://raw.githubusercontent.com/arfshl/debian-on-android/main/lxde.sh && sh lxde.sh && rm lxde.sh

### Window Manager
- i3

      curl -o https://raw.githubusercontent.com/arfshl/debian-on-android/main/i3.sh && sh i3.sh && rm i3.sh

- Openbox 

      curl -o https://raw.githubusercontent.com/arfshl/debian-on-android/main/openbox.sh && sh openbox.sh && rm openbox.sh

- Awesome

      curl -o https://raw.githubusercontent.com/arfshl/debian-on-android/main/awesome.sh && sh awesome.sh && rm awesome.sh

