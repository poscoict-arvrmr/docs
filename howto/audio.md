# 라즈베리파이에 이어폰을 연결했으나 소리가 재생되지 않음. 

참고사이트
 - [https://www.raspberrypi.org/documentation/configuration/audio-config.md](https://www.raspberrypi.org/documentation/configuration/audio-config.md)

```bash
sudo raspi-config
```

```Advanced Options``` 으로 이동하고  
```Audio``` 를 찾아서..  
auto 말고 HDMI 말고 남은 하나 선택했음. 

```bash
pi@raspberrypi:~ $ sudo raspi-config
numid=3,iface=MIXER,name='PCM Playback Route'
  ; type=INTEGER,access=rw------,values=1,min=0,max=2,step=0
  : values=1
pi@raspberrypi:~ $ 
```

# 블루투스 사용하기

참고사이트
 - [https://www.raspberrypi.org/forums/viewtopic.php?t=161944](https://www.raspberrypi.org/forums/viewtopic.php?t=161944)


```
sudo apt-get update
sudo apt-get upgrade
```

```bash
pi@raspberrypi:~ $ sudo apt-get update
받기:1 http://mirrordirector.raspbian.org/raspbian stretch InRelease [15.0 kB] 
기존:2 https://deb.nodesource.com/node_6.x stretch InRelease                   
받기:3 http://archive.raspberrypi.org/debian stretch InRelease [25.3 kB]       
받기:5 http://mirrordirector.raspbian.org/raspbian stretch/main armhf Packages [11.7 MB]
기존:4 https://packagecloud.io/headmelted/codebuilds/ubuntu xenial InRelease
받기:6 http://archive.raspberrypi.org/debian stretch/main armhf Packages [139 kB]
받기:7 http://archive.raspberrypi.org/debian stretch/ui armhf Packages [28.0 kB]
받기:8 http://mirrordirector.raspbian.org/raspbian stretch/contrib armhf Packages [56.8 kB]
내려받기 11.9 M바이트, 소요시간 1분 16초 (155 k바이트/초)                      
패키지 목록을 읽는 중입니다... 완료
pi@raspberrypi:~ $ sudo apt-get upgrade
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다       
상태 정보를 읽는 중입니다... 완료
업그레이드를 계산하는 중입니다... 완료
다음 패키지를 과거 버전으로 유지합니다:
  libraspberrypi-bin libraspberrypi-dev libraspberrypi-doc libraspberrypi0
  raspberrypi-bootloader raspberrypi-kernel
다음 패키지를 업그레이드할 것입니다:
  firmware-atheros firmware-brcm80211 firmware-libertas firmware-misc-nonfree
  firmware-realtek libtasn1-6 pi-bluetooth rpi-chromium-mods
8개 업그레이드, 0개 새로 설치, 0개 제거 및 6개 업그레이드 안 함.
21.6 M바이트 아카이브를 받아야 합니다.
이 작업 후 8,192 바이트의 디스크 공간을 더 사용하게 됩니다.
계속 하시겠습니까? [Y/n] Y
받기:1 http://archive.raspberrypi.org/debian stretch/ui armhf rpi-chromium-mods armhf 20180207 [9,201 kB]
받기:2 http://muug.ca/mirror/raspbian/raspbian stretch/main armhf libtasn1-6 armhf 4.10-1.1+deb9u1 [45.6 kB]
받기:3 http://archive.raspberrypi.org/debian stretch/main armhf firmware-atheros all 1:20161130-3+rpt1 [3,132 kB]
받기:4 http://archive.raspberrypi.org/debian stretch/main armhf firmware-brcm80211 all 1:20161130-3+rpt1 [3,613 kB]
받기:5 http://archive.raspberrypi.org/debian stretch/main armhf firmware-libertas all 1:20161130-3+rpt1 [2,950 kB]
받기:6 http://archive.raspberrypi.org/debian stretch/main armhf firmware-misc-nonfree all 1:20161130-3+rpt1 [2,321 kB]
받기:7 http://archive.raspberrypi.org/debian stretch/main armhf firmware-realtek all 1:20161130-3+rpt1 [342 kB]
받기:8 http://archive.raspberrypi.org/debian stretch/main armhf pi-bluetooth all 0.1.7 [3,782 B]
내려받기 21.6 M바이트, 소요시간 2분 11초 (164 k바이트/초)                      
Reading changelogs... Done
패키지를 미리 설정하는 중입니다...
(데이터베이스 읽는중 ...현재 139193개의 파일과 디렉터리가 설치되어 있습니다.)
Preparing to unpack .../0-rpi-chromium-mods_20180207_armhf.deb ...
Unpacking rpi-chromium-mods (20180207) over (20180112) ...
Preparing to unpack .../1-libtasn1-6_4.10-1.1+deb9u1_armhf.deb ...
Unpacking libtasn1-6:armhf (4.10-1.1+deb9u1) over (4.10-1.1) ...
Preparing to unpack .../2-firmware-atheros_1%3a20161130-3+rpt1_all.deb ...
Unpacking firmware-atheros (1:20161130-3+rpt1) over (1:20161130-3+rpi2) ...
Preparing to unpack .../3-firmware-brcm80211_1%3a20161130-3+rpt1_all.deb ...
Unpacking firmware-brcm80211 (1:20161130-3+rpt1) over (1:20161130-3+rpi2) ...
Preparing to unpack .../4-firmware-libertas_1%3a20161130-3+rpt1_all.deb ...
Unpacking firmware-libertas (1:20161130-3+rpt1) over (1:20161130-3+rpi2) ...
Preparing to unpack .../5-firmware-misc-nonfree_1%3a20161130-3+rpt1_all.deb ...
Unpacking firmware-misc-nonfree (1:20161130-3+rpt1) over (1:20161130-3+rpi2) ...
Preparing to unpack .../6-firmware-realtek_1%3a20161130-3+rpt1_all.deb ...
Unpacking firmware-realtek (1:20161130-3+rpt1) over (1:20161130-3+rpi2) ...
Preparing to unpack .../7-pi-bluetooth_0.1.7_all.deb ...
Unpacking pi-bluetooth (0.1.7) over (0.1.6) ...
firmware-realtek (1:20161130-3+rpt1) 설정하는 중입니다 ...
update-initramfs: deferring update (trigger activated)
rpi-chromium-mods (20180207) 설정하는 중입니다 ...
새 버전의 설정 파일 /etc/chromium-browser/customizations/00-rpi-vars 설치하는 중입니다 ...
pi-bluetooth (0.1.7) 설정하는 중입니다 ...
libtasn1-6:armhf (4.10-1.1+deb9u1) 설정하는 중입니다 ...
Processing triggers for libc-bin (2.24-11+deb9u1) ...
firmware-libertas (1:20161130-3+rpt1) 설정하는 중입니다 ...
firmware-misc-nonfree (1:20161130-3+rpt1) 설정하는 중입니다 ...
update-initramfs: deferring update (trigger activated)
firmware-atheros (1:20161130-3+rpt1) 설정하는 중입니다 ...
firmware-brcm80211 (1:20161130-3+rpt1) 설정하는 중입니다 ...
Processing triggers for initramfs-tools (0.130) ...
pi@raspberrypi:~ $ sudo apt-get install pi-bluetooth
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다       
상태 정보를 읽는 중입니다... 완료
pi-bluetooth is already the newest version (0.1.7).
0개 업그레이드, 0개 새로 설치, 0개 제거 및 6개 업그레이드 안 함.
pi@raspberrypi:~ $ sudo apt-get install blueman pulseaudio pavucontrol pulseaudio-module-bluetooth
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다       
상태 정보를 읽는 중입니다... 완료
The following additional packages will be installed:
  bluez-obexd gir1.2-appindicator3-0.1 gir1.2-notify-0.7 libappindicator3-1
  libasound2-plugins libatkmm-1.6-1v5 libcairomm-1.0-1v5 libdbusmenu-glib4
  libdbusmenu-gtk3-4 libglibmm-2.4-1v5 libgtkmm-3.0-1v5 libical2
  libindicator3-7 libpangomm-1.4-1v5 libpulse-mainloop-glib0 libpulsedsp
  libspeexdsp1 notification-daemon pulseaudio-utils python3-cairo
  python3-gi-cairo rtkit
제안하는 패키지:
  pavumeter paman paprefs
다음 새 패키지를 설치할 것입니다:
  blueman bluez-obexd gir1.2-appindicator3-0.1 gir1.2-notify-0.7
  libappindicator3-1 libasound2-plugins libatkmm-1.6-1v5 libcairomm-1.0-1v5
  libdbusmenu-glib4 libdbusmenu-gtk3-4 libglibmm-2.4-1v5 libgtkmm-3.0-1v5
  libical2 libindicator3-7 libpangomm-1.4-1v5 libpulse-mainloop-glib0
  libpulsedsp libspeexdsp1 notification-daemon pavucontrol pulseaudio
  pulseaudio-module-bluetooth pulseaudio-utils python3-cairo python3-gi-cairo
  rtkit
0개 업그레이드, 26개 새로 설치, 0개 제거 및 6개 업그레이드 안 함.
5,971 k바이트 아카이브를 받아야 합니다.
이 작업 후 21.7 M바이트의 디스크 공간을 더 사용하게 됩니다.
계속 하시겠습니까? [Y/n] Y
받기:1 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libspeexdsp1 armhf 1.2~rc1.2-1 [42.9 kB]
받기:2 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libical2 armhf 2.0.0-0.5+b1 [164 kB]
받기:3 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf notification-daemon armhf 3.20.0-1 [55.4 kB]
받기:4 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libpulse-mainloop-glib0 armhf 10.0-1+deb9u1 [43.9 kB]
받기:5 http://archive.raspberrypi.org/debian stretch/main armhf bluez-obexd armhf 5.43-2+rpt2+deb9u2 [176 kB]
받기:6 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf gir1.2-notify-0.7 armhf 0.7.7-2 [9,740 B]
받기:7 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf python3-cairo armhf 1.10.0+dfsg-5 [23.5 kB]
받기:8 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf python3-gi-cairo armhf 3.22.0-2 [328 kB]
받기:9 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libdbusmenu-glib4 armhf 12.10.2-2 [96.8 kB]
받기:10 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libdbusmenu-gtk3-4 armhf 12.10.2-2 [85.6 kB]
받기:11 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libindicator3-7 armhf 0.5.0-3 [49.5 kB]
받기:12 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libappindicator3-1 armhf 0.4.92-4+b2 [50.4 kB]
받기:13 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf gir1.2-appindicator3-0.1 armhf 0.4.92-4+b2 [38.7 kB]
받기:14 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf blueman armhf 2.0.4-1+b4 [1,698 kB]
받기:15 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libasound2-plugins armhf 1.1.1-1 [72.9 kB]
받기:16 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libglibmm-2.4-1v5 armhf 2.50.0-1 [593 kB]
받기:17 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libatkmm-1.6-1v5 armhf 2.24.2-2 [57.1 kB]
받기:18 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libcairomm-1.0-1v5 armhf 1.12.0-1 [61.7 kB]
받기:19 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libpangomm-1.4-1v5 armhf 2.40.1-3 [50.1 kB]
받기:21 http://ftp.kaist.ac.kr/raspbian/raspbian stretch/main armhf libpulsedsp armhf 10.0-1+deb9u1 [52.0 kB]
받기:20 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf libgtkmm-3.0-1v5 armhf 3.22.0-1 [903 kB]
받기:22 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf pavucontrol armhf 3.0-3.1 [102 kB]
받기:23 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf pulseaudio-utils armhf 10.0-1+deb9u1 [82.8 kB]
받기:24 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf pulseaudio armhf 10.0-1+deb9u1 [1,020 kB]
받기:25 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf rtkit armhf 0.11-4 [31.2 kB]
받기:26 http://ftp.harukasan.org/raspbian/raspbian stretch/main armhf pulseaudio-module-bluetooth armhf 10.0-1+deb9u1 [83.9 kB]
내려받기 5,971 k바이트, 소요시간 20초 (297 k바이트/초)                         
Selecting previously unselected package libspeexdsp1:armhf.
(데이터베이스 읽는중 ...현재 139193개의 파일과 디렉터리가 설치되어 있습니다.)
Preparing to unpack .../00-libspeexdsp1_1.2~rc1.2-1_armhf.deb ...
Unpacking libspeexdsp1:armhf (1.2~rc1.2-1) ...
Selecting previously unselected package libical2:armhf.
Preparing to unpack .../01-libical2_2.0.0-0.5+b1_armhf.deb ...
Unpacking libical2:armhf (2.0.0-0.5+b1) ...
Selecting previously unselected package bluez-obexd.
Preparing to unpack .../02-bluez-obexd_5.43-2+rpt2+deb9u2_armhf.deb ...
Unpacking bluez-obexd (5.43-2+rpt2+deb9u2) ...
Selecting previously unselected package notification-daemon.
Preparing to unpack .../03-notification-daemon_3.20.0-1_armhf.deb ...
Unpacking notification-daemon (3.20.0-1) ...
Selecting previously unselected package libpulse-mainloop-glib0:armhf.
Preparing to unpack .../04-libpulse-mainloop-glib0_10.0-1+deb9u1_armhf.deb ...
Unpacking libpulse-mainloop-glib0:armhf (10.0-1+deb9u1) ...
Selecting previously unselected package gir1.2-notify-0.7:armhf.
Preparing to unpack .../05-gir1.2-notify-0.7_0.7.7-2_armhf.deb ...
Unpacking gir1.2-notify-0.7:armhf (0.7.7-2) ...
Selecting previously unselected package python3-cairo.
Preparing to unpack .../06-python3-cairo_1.10.0+dfsg-5_armhf.deb ...
Unpacking python3-cairo (1.10.0+dfsg-5) ...
Selecting previously unselected package python3-gi-cairo.
Preparing to unpack .../07-python3-gi-cairo_3.22.0-2_armhf.deb ...
Unpacking python3-gi-cairo (3.22.0-2) ...
Selecting previously unselected package libdbusmenu-glib4:armhf.
Preparing to unpack .../08-libdbusmenu-glib4_12.10.2-2_armhf.deb ...
Unpacking libdbusmenu-glib4:armhf (12.10.2-2) ...
Selecting previously unselected package libdbusmenu-gtk3-4:armhf.
Preparing to unpack .../09-libdbusmenu-gtk3-4_12.10.2-2_armhf.deb ...
Unpacking libdbusmenu-gtk3-4:armhf (12.10.2-2) ...
Selecting previously unselected package libindicator3-7:armhf.
Preparing to unpack .../10-libindicator3-7_0.5.0-3_armhf.deb ...
Unpacking libindicator3-7:armhf (0.5.0-3) ...
Selecting previously unselected package libappindicator3-1:armhf.
Preparing to unpack .../11-libappindicator3-1_0.4.92-4+b2_armhf.deb ...
Unpacking libappindicator3-1:armhf (0.4.92-4+b2) ...
Selecting previously unselected package gir1.2-appindicator3-0.1:armhf.
Preparing to unpack .../12-gir1.2-appindicator3-0.1_0.4.92-4+b2_armhf.deb ...
Unpacking gir1.2-appindicator3-0.1:armhf (0.4.92-4+b2) ...
Selecting previously unselected package blueman.
Preparing to unpack .../13-blueman_2.0.4-1+b4_armhf.deb ...
Unpacking blueman (2.0.4-1+b4) ...
Selecting previously unselected package libasound2-plugins:armhf.
Preparing to unpack .../14-libasound2-plugins_1.1.1-1_armhf.deb ...
Unpacking libasound2-plugins:armhf (1.1.1-1) ...
Selecting previously unselected package libglibmm-2.4-1v5:armhf.
Preparing to unpack .../15-libglibmm-2.4-1v5_2.50.0-1_armhf.deb ...
Unpacking libglibmm-2.4-1v5:armhf (2.50.0-1) ...
Selecting previously unselected package libatkmm-1.6-1v5:armhf.
Preparing to unpack .../16-libatkmm-1.6-1v5_2.24.2-2_armhf.deb ...
Unpacking libatkmm-1.6-1v5:armhf (2.24.2-2) ...
Selecting previously unselected package libcairomm-1.0-1v5:armhf.
Preparing to unpack .../17-libcairomm-1.0-1v5_1.12.0-1_armhf.deb ...
Unpacking libcairomm-1.0-1v5:armhf (1.12.0-1) ...
Selecting previously unselected package libpangomm-1.4-1v5:armhf.
Preparing to unpack .../18-libpangomm-1.4-1v5_2.40.1-3_armhf.deb ...
Unpacking libpangomm-1.4-1v5:armhf (2.40.1-3) ...
Selecting previously unselected package libgtkmm-3.0-1v5:armhf.
Preparing to unpack .../19-libgtkmm-3.0-1v5_3.22.0-1_armhf.deb ...
Unpacking libgtkmm-3.0-1v5:armhf (3.22.0-1) ...
Selecting previously unselected package libpulsedsp:armhf.
Preparing to unpack .../20-libpulsedsp_10.0-1+deb9u1_armhf.deb ...
Unpacking libpulsedsp:armhf (10.0-1+deb9u1) ...
Selecting previously unselected package pavucontrol.
Preparing to unpack .../21-pavucontrol_3.0-3.1_armhf.deb ...
Unpacking pavucontrol (3.0-3.1) ...
Selecting previously unselected package pulseaudio-utils.
Preparing to unpack .../22-pulseaudio-utils_10.0-1+deb9u1_armhf.deb ...
Unpacking pulseaudio-utils (10.0-1+deb9u1) ...
Selecting previously unselected package pulseaudio.
Preparing to unpack .../23-pulseaudio_10.0-1+deb9u1_armhf.deb ...
Unpacking pulseaudio (10.0-1+deb9u1) ...
Selecting previously unselected package rtkit.
Preparing to unpack .../24-rtkit_0.11-4_armhf.deb ...
Unpacking rtkit (0.11-4) ...
Selecting previously unselected package pulseaudio-module-bluetooth.
Preparing to unpack .../25-pulseaudio-module-bluetooth_10.0-1+deb9u1_armhf.deb ...
Unpacking pulseaudio-module-bluetooth (10.0-1+deb9u1) ...
libindicator3-7:armhf (0.5.0-3) 설정하는 중입니다 ...
libcairomm-1.0-1v5:armhf (1.12.0-1) 설정하는 중입니다 ...
gir1.2-notify-0.7:armhf (0.7.7-2) 설정하는 중입니다 ...
libical2:armhf (2.0.0-0.5+b1) 설정하는 중입니다 ...
libpulse-mainloop-glib0:armhf (10.0-1+deb9u1) 설정하는 중입니다 ...
Processing triggers for mime-support (3.60) ...
libpulsedsp:armhf (10.0-1+deb9u1) 설정하는 중입니다 ...
Processing triggers for desktop-file-utils (0.23-1) ...
pulseaudio-utils (10.0-1+deb9u1) 설정하는 중입니다 ...
Processing triggers for libglib2.0-0:armhf (2.50.3-2) ...
Processing triggers for menu (2.1.47) ...
libdbusmenu-glib4:armhf (12.10.2-2) 설정하는 중입니다 ...
Processing triggers for libc-bin (2.24-11+deb9u1) ...
rtkit (0.11-4) 설정하는 중입니다 ...
bluez-obexd (5.43-2+rpt2+deb9u2) 설정하는 중입니다 ...
Processing triggers for man-db (2.7.6.1-2) ...
python3-cairo (1.10.0+dfsg-5) 설정하는 중입니다 ...
Processing triggers for gnome-menus (3.13.3-9) ...
libglibmm-2.4-1v5:armhf (2.50.0-1) 설정하는 중입니다 ...
Processing triggers for dbus (1.10.24-0+deb9u1) ...
Processing triggers for hicolor-icon-theme (0.15-1) ...
libspeexdsp1:armhf (1.2~rc1.2-1) 설정하는 중입니다 ...
libatkmm-1.6-1v5:armhf (2.24.2-2) 설정하는 중입니다 ...
notification-daemon (3.20.0-1) 설정하는 중입니다 ...
libdbusmenu-gtk3-4:armhf (12.10.2-2) 설정하는 중입니다 ...
libasound2-plugins:armhf (1.1.1-1) 설정하는 중입니다 ...
python3-gi-cairo (3.22.0-2) 설정하는 중입니다 ...
libpangomm-1.4-1v5:armhf (2.40.1-3) 설정하는 중입니다 ...
libappindicator3-1:armhf (0.4.92-4+b2) 설정하는 중입니다 ...
pulseaudio (10.0-1+deb9u1) 설정하는 중입니다 ...
사용자 pulse을(를) audio 그룹에 등록 중
libgtkmm-3.0-1v5:armhf (3.22.0-1) 설정하는 중입니다 ...
pulseaudio-module-bluetooth (10.0-1+deb9u1) 설정하는 중입니다 ...
gir1.2-appindicator3-0.1:armhf (0.4.92-4+b2) 설정하는 중입니다 ...
pavucontrol (3.0-3.1) 설정하는 중입니다 ...
blueman (2.0.4-1+b4) 설정하는 중입니다 ...
Processing triggers for libc-bin (2.24-11+deb9u1) ...
Processing triggers for dbus (1.10.24-0+deb9u1) ...
Processing triggers for menu (2.1.47) ...
pi@raspberrypi:~ $ 

```
