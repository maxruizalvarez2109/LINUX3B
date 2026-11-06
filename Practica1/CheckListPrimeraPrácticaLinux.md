SISTEMA OPERATIVO LINUX · SESIÓN 01
Universidad Autónoma de Zacatecas · Ingeniería de Software
Docente: Dr. Alejandro Morgan

PRIMERA PRÁCTICA: CONECTA, INSPECCIONA Y EXPLICA

[x] Identificar distribución y kernel
[x] Confirmar usuario, grupos y ruta
[x] Examinar archivos y permisos
[x] Observar proceso y servicio
[x] Relacionar puerto y evidencia

==🔴Evidencia mínima por actividad:==
- Comando o acción
- Salida relevante
- Interpretación técnica
- Decisión o siguiente prueba

Nombre: Maximiliano Ruiz Álvarez

#### Ejercicio 1: Identificar distribución y kernel

==🔴Comando o acción:==

cat /etc/os-release --> Distribución
uname -r  --> Kernel

==🔴Salida relevante:==

ubuntu@UbuntuLinux:~$ cat /etc/os-release
PRETTY_NAME="Ubuntu 26.04 LTS"
NAME="Ubuntu"
VERSION_ID="26.04"
VERSION="26.04 (Resolute Raccoon)"
VERSION_CODENAME=resolute
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=resolute
LOGO=ubuntu-logo

ubuntu@UbuntuLinux:~$ uname -r
7.0.0-30-generic

![[IdentificarDistribucionYKernel.png|700]]

==🔴Interpretación técnica:==

El comando `cat /etc/os-release` sirve para ver qué sistema operativo está instalado (en este caso, Ubuntu 26.04). 
El comando `uname -r` sirve para saber la versión exacta del núcleo del sistema o kernel (7.0.0-30).

==🔴Decisión o siguiente prueba:==

Como ya sé qué sistema operativo tengo, el siguiente paso es ver qué usuario estoy utilizando y qué permisos tengo dentro de este sistema.


#### Ejercicio 2: Confirmar usuario, grupos y ruta

==🔴Comando o acción:==

whoami 
id 
groups 
pwd

==🔴Salida relevante:==

ubuntu@UbuntuLinux:~$ whoami
ubuntu

ubuntu@UbuntuLinux:~$ id
uid=1000(ubuntu) gid=1000(ubuntu) groups=1000(ubuntu),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),100(users),111(lpadmin),114(lxd)

ubuntu@UbuntuLinux:~$ groups
ubuntu adm cdrom sudo dip plugdev users lpadmin lxd

ubuntu@UbuntuLinux:~$ pwd
/home/ubuntu

![[Ejercicio2ConfirmarUsuariosRutas 1.png]]


==🔴Interpretación técnica:==

El comando `whoami` sirve para ver el nombre del usuario actual. 
Los comandos `id` y `groups` sirven para saber a qué grupos pertenece el usuario (como el grupo "sudo", que permite ser administrador). 
El comando `pwd` sirve para saber en qué carpeta exacta se está trabajando (`/home/ubuntu`).

==🔴Decisión o siguiente prueba:==

Sabiendo que estoy en mi carpeta personal, ahora voy a listar los archivos que tengo aquí guardados y checar qué permisos tienen.


#### Ejercicio 3: Examinar archivos y permisos

==🔴Comando o acción:==

ls -la
stat

==🔴Salida relevante:==

ubuntu@UbuntuLinux:~$ ls -la
total 112
drwx--xr-x 17 ubuntu ubuntu 4096 Nov  6 00:30 .
drwxr-xr-x  3 root   root   4096 Aug 21 01:01 ..
-rw-------  1 ubuntu ubuntu 2083 Oct 30 10:12 .bash_history
-rw-r--r--  1 ubuntu ubuntu  220 Feb 13  2026 .bash_logout
-rw-r--r--  1 ubuntu ubuntu 3771 Feb 13  2026 .bashrc
drwx------ 15 ubuntu ubuntu 4096 Oct 22 23:20 .cache
drwx------ 16 ubuntu ubuntu 4096 Sep 25 07:48 .config
drwx------  4 ubuntu ubuntu 4096 Aug 21 01:16 .local
-rw-r--r--  1 ubuntu ubuntu  807 Feb 13  2026 .profile
drwx------  2 ubuntu ubuntu 4096 Aug 21 01:15 .ssh
-rw-r-----  1 ubuntu ubuntu    5 Nov  6 00:29 .vboxclient-clipboard-tty2-control.pid
-rw-r-----  1 ubuntu ubuntu    5 Nov  6 00:29 .vboxclient-clipboard-tty2-service.pid
-rw-r-----  1 ubuntu ubuntu    5 Nov  6 00:29 .vboxclient-draganddrop-tty2-control.pid
-rw-r-----  1 ubuntu ubuntu    5 Nov  6 00:29 .vboxclient-hostversion-tty2-control.pid
-rw-r-----  1 ubuntu ubuntu    5 Nov  6 00:29 .vboxclient-seamless-tty2-control.pid
-rw-r-----  1 ubuntu ubuntu    5 Nov  6 00:29 .vboxclient-vmsvga-session-tty2-control.pid
-rw-r-----  1 ubuntu ubuntu    5 Nov  6 00:29 .vboxclient-vmsvga-session-tty2-service.pid
drwxr-xr-x  2 ubuntu ubuntu 4096 Aug 21 01:16 Desktop
drwxr-xr-x  2 ubuntu ubuntu 4096 Oct  9 10:57 Documents
drwxr-xr-x  2 ubuntu ubuntu 4096 Aug 21 01:16 Downloads
drwxr-xr-x  2 ubuntu ubuntu 4096 Aug 21 01:16 Music
drwxr-xr-x  3 ubuntu ubuntu 4096 Aug 21 06:32 Pictures
drwxr-xr-x  2 ubuntu ubuntu 4096 Aug 21 01:16 Public
drwxr-xr-x  2 ubuntu ubuntu 4096 Aug 21 01:16 Templates
drwxr-xr-x  2 ubuntu ubuntu 4096 Aug 21 01:16 Videos
drwx--xr-x  6 ubuntu ubuntu 4096 Aug 28 09:01 laboratorio-cli
drwxrwxr-x  5 ubuntu ubuntu 4096 Oct 30 09:45 scripts
drwx------  6 ubuntu ubuntu 4096 Aug 21 09:00 snap

ubuntu@UbuntuLinux:~$ stat .bashrc
  File: .bashrc
  size: 3771      	Blocks: 8          IO Block: 4096   regular file
Device: 8,2	Inode: 1316481     Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/  ubuntu)   Gid: ( 1000/  ubuntu)
Access: 2026-11-05 23:00:09.011279159 -0600
Modify: 2026-02-13 06:16:08.000000000 -0600
Change: 2026-08-21 01:01:03.781058789 -0600
 Birth: 2026-08-21 01:01:03.780058782 -0600

![[Ejercicio3ExaminarArchivosYPermisos2.png]]


==🔴Interpretación técnica:==

El comando `ls -la` sirve para ver todos los archivos (incluso los ocultos) y revisar sus permisos o tamaño. El comando `stat` sirve para ver información más detallada de un solo archivo, como las fechas exactas en que se creó o se modificó.

==🔴Decisión o siguiente prueba:==

Ya que revisé cómo ver los archivos y sus detalles, mi siguiente prueba será revisar qué programas o procesos se están ejecutando actualmente en la computadora.


#### Ejercicio 4: Observar proceso y servicio

==🔴Comando o acción:==

ps
systemctl status

==🔴Salida relevante:==

ubuntu@UbuntuLinux:~$ ps
    PID TTY          TIME CMD
   5441 pts/0    00:00:00 bash
   5451 pts/0    00:00:00 ps
   
ubuntu@UbuntuLinux:~$ systemctl status
● UbuntuLinux
    State: degraded
    Units: 578 loaded (incl. loaded aliases)
     Jobs: 0 queued
   Failed: 1 units
    Since: Fri 2026-11-06 00:28:39 CST; 41min ago
  systemd: 259.5-0ubuntu3.4
  Tainted: unmerged-bin
   CGroup: /
           ├─init.scope
           │ └─1 /usr/lib/systemd/systemd --switched-root --system --deserialize=51
           ├─system.slice
           │ ├─ModemManager.service
           │ │ └─1002 /usr/sbin/ModemManager
           │ ├─NetworkManager.service
           │ │ └─945 /usr/sbin/NetworkManager --no-daemon
           │ ├─accounts-daemon.service
           │ │ └─827 /usr/libexec/accounts-daemon
           │ ├─avahi-daemon.service
           │ │ ├─778 "avahi-daemon: running [UbuntuLinux.local]"
           │ │ └─882 "avahi-daemon: chroot helper"
           │ ├─chrony.service
           │ │ ├─780 /bin/sh /usr/lib/systemd/scripts/chronyd-starter.sh -n -F 1
           │ │ ├─944 /usr/sbin/chronyd -n -F 1
           │ │ └─966 /usr/sbin/chronyd -n -F 1
           │ ├─colord.service
           │ │ └─2767 /usr/libexec/colord
           │ ├─cron.service
           │ │ └─828 /usr/sbin/cron -f -P
           │ ├─dbus.service
           │ │ └─782 @dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation --syslog-only
           │ ├─gdm.service
           │ │ └─2516 /usr/sbin/gdm3
           │ ├─named.service
           │ │ └─1096 /usr/sbin/named -f -u bind
           │ ├─networkd-dispatcher.service
           │ │ └─799 /usr/bin/python3 /usr/bin/networkd-dispatcher --run-startup-triggers
           │ ├─nginx.service
           │ │ ├─1156 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
           │ │ └─1162 "nginx: worker process"
           │ ├─polkit.service
           │ │ └─801 /usr/lib/polkit-1/polkitd --no-debug --log-level=notice
           │ ├─power-profiles-daemon.service
           │ │ └─2511 /usr/libexec/power-profiles-daemon
           │ ├─rsyslog.service
           │ │ └─853 /usr/sbin/rsyslogd -n -iNONE
           │ ├─rtkit-daemon.service
           │ │ └─2619 /usr/libexec/rtkit-daemon
           │ ├─snapd.service
           │ │ └─815 /snap/snapd/current/usr/lib/snapd/snapd
           │ ├─ssh.service
           │ │ └─1112 "sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups"
           │ ├─switcheroo-control.service
           │ │ └─832 /usr/libexec/switcheroo-control
           │ ├─system-cups.slice
           │ │ ├─cups-browsed.service
           │ │ │ └─5372 /usr/sbin/cups-browsed
           │ │ └─cups.service
           │ │   ├─5370 /usr/sbin/cupsd -l
           │ │   └─5371 /usr/lib/cups/notifier/dbus dbus://
           │ ├─systemd-journald.service
           │ │ └─324 /usr/lib/systemd/systemd-journald
           │ ├─systemd-logind.service
           │ │ └─840 /usr/lib/systemd/systemd-logind
           │ ├─systemd-oomd.service
           │ │ └─365 /usr/lib/systemd/systemd-oomd
           │ ├─systemd-resolved.service
           │ │ └─366 /usr/lib/systemd/systemd-resolved
           │ ├─systemd-udevd.service
           │ │ └─udev
           │ │   └─393 /usr/lib/systemd/systemd-udevd
           │ ├─udisks2.service
           │ │ └─842 /usr/libexec/udisks2/udisksd
           │ ├─unattended-upgrades.service
           │ │ └─1078 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal
           │ ├─upower.service
           │ │ └─2812 /usr/libexec/upowerd
           │ ├─vboxadd.service
           │ │ ├─2024 /usr/bin/VBoxDRMClient
           │ │ └─2027 /usr/sbin/VBoxService --pidfile /var/run/vboxadd-service.sh
           │ └─wpa_supplicant.service
           │   └─946 /usr/sbin/wpa_supplicant -u -s -O "DIR=/run/wpa_supplicant GROUP=netdev"
           └─user.slice
             └─user-1000.slice
               ├─session-2.scope
               │ ├─3197 "gdm-session-worker [pam/gdm-password]"
               │ ├─3343 /usr/libexec/gdm-wayland-session "/usr/bin/gnome-session --session=ubuntu"
               │ └─3364 /usr/libexec/gnome-session-init-worker ubuntu
               └─user@1000.service
                 ├─app.slice
                 │ ├─app-gnome-org.gnome.Evolution\x2dalarm\x2dnotify-3738.scope
                 │ │ └─3738 /usr/libexec/evolution-data-server/evolution-alarm-notify
                 │ ├─app-gnome-org.gnome.SettingsDaemon.DiskUtilityNotify-3733.scope
                 │ │ └─3733 /usr/libexec/gsd-disk-utility-notify
                 │ ├─app-gnome-update\x2dnotifier-3736.scope
                 │ │ └─3736 /usr/bin/update-notifier
                 │ ├─app-gnome-vboxclient-3744.scope
                 │ │ ├─4351 /usr/bin/VBoxClient --clipboard
                 │ │ ├─4353 /usr/bin/VBoxClient --clipboard
                 │ │ ├─4383 /usr/bin/VBoxClient --vmsvga-session
                 │ │ └─4385 /usr/bin/VBoxClient --vmsvga-session
                 │ ├─app-gnome\x2dsession\x2dmanager.slice
                 │ │ └─gnome-session-manager@ubuntu.service
                 │ │   └─3545 /usr/libexec/gnome-session-service --session=ubuntu
                 │ ├─dconf.service
                 │ │ └─4221 /usr/libexec/dconf-service
                 │ ├─evolution-addressbook-factory.service
                 │ │ └─3989 /usr/libexec/evolution-addressbook-factory
                 │ ├─evolution-calendar-factory.service
                 │ │ └─3964 /usr/libexec/evolution-calendar-factory
                 │ ├─evolution-source-registry.service
                 │ │ └─3686 /usr/libexec/evolution-source-registry
                 │ ├─gcr-ssh-agent.service
                 │ │ └─3504 /usr/libexec/gcr-ssh-agent --base-dir /run/user/1000/gcr
                 │ ├─gnome-keyring-daemon.service
                 │ │ └─3304 /usr/bin/gnome-keyring-daemon --foreground --components=pkcs11,secrets --control-directory=/run/user/1000/keyring
                 │ ├─gnome-session-monitor.service
                 │ │ └─3505 /usr/libexec/gnome-session-ctl --monitor
                 │ ├─mpris-proxy.service
                 │ │ └─3305 /usr/bin/mpris-proxy
                 │ ├─ptyxis-spawn-9c744358-06dd-4939-bd7a-23e73ef0444d.scope
                 │ │ ├─5441 /usr/bin/bash
                 │ │ ├─5461 systemctl status
                 │ │ └─5462 pager
                 │ ├─snap.snapd-desktop-integration.snapd-desktop-integration.service
                 │ │ ├─3303 /snap/snapd-desktop-integration/391/usr/bin/user-session-helper /snap/snapd-desktop-integration/391/usr/bin/snapd-desktop-integration
                 │ │ └─4459 /snap/snapd-desktop-integration/391/usr/bin/snapd-desktop-integration
                 │ ├─ssh-agent.service
                 │ │ └─3506 /usr/bin/ssh-agent -D
                 │ ├─xdg-desktop-portal-gnome.service
                 │ │ └─3986 /usr/libexec/xdg-desktop-portal-gnome
                 │ └─xdg-desktop-portal-gtk.service
                 │   └─4438 /usr/libexec/xdg-desktop-portal-gtk
                 ├─background.slice
                 │ └─localsearch-3.service
                 │   └─3943 /usr/libexec/localsearch-3
                 ├─init.scope
                 │ ├─3239 /usr/lib/systemd/systemd --user
                 │ └─3245 "(sd-pam)"
                 └─session.slice
                   ├─at-spi-dbus-bus.service
                   │ ├─3590 /usr/libexec/at-spi-bus-launcher
                   │ ├─3599 /usr/bin/dbus-daemon --config-file=/usr/share/defaults/at-spi2/accessibility.conf --nofork --print-address 11 --address=unix:path=/run/user/1000/at-spi/bus
                   │ └─3601 /usr/libexec/at-spi2-registryd --use-gnome-session
                   ├─dbus.service
                   │ ├─3299 /usr/bin/dbus-daemon --session --address=systemd: --nofork --nopidfile --systemd-activation --syslog-only
                   │ ├─3644 /usr/libexec/gnome-shell-calendar-server
                   │ ├─3688 /usr/bin/gjs -m /usr/share/gnome-shell/org.gnome.Shell.Notifications
                   │ ├─3905 /usr/bin/gjs -m /usr/share/gnome-shell/org.gnome.ScreenSaver
                   │ ├─3908 /usr/libexec/ibus-portal
                   │ ├─3941 /usr/libexec/goa-daemon
                   │ ├─4003 /usr/libexec/goa-identity-service
                   │ ├─4537 /usr/bin/gnome-text-editor --gapplication-service
                   │ ├─5422 /usr/bin/ptyxis --gapplication-service
                   │ └─5429 /usr/libexec/ptyxis-agent --socket-fd=3 --rlimit-nofile=1024
                   ├─filter-chain.service
                   │ └─3311 /usr/bin/pipewire -c filter-chain.conf
                   ├─gvfs-afc-volume-monitor.service
                   │ └─4033 /usr/libexec/gvfs-afc-volume-monitor
                   ├─gvfs-daemon.service
                   │ ├─3518 /usr/libexec/gvfsd
                   │ ├─3534 /usr/libexec/gvfsd-fuse /run/user/1000/gvfs -f
                   │ └─4233 /usr/libexec/gvfsd-trash --spawner :1.21 /org/gtk/gvfs/exec_spaw/0
                   ├─gvfs-goa-volume-monitor.service
                   │ └─4044 /usr/libexec/gvfs-goa-volume-monitor
                   ├─gvfs-gphoto2-volume-monitor.service
                   │ └─4039 /usr/libexec/gvfs-gphoto2-volume-monitor
                   ├─gvfs-metadata.service
                   │ └─4192 /usr/libexec/gvfsd-metadata
                   ├─gvfs-mtp-volume-monitor.service
                   │ └─4022 /usr/libexec/gvfs-mtp-volume-monitor
                   ├─gvfs-udisks2-volume-monitor.service
                   │ └─3994 /usr/libexec/gvfs-udisks2-volume-monitor
                   ├─org.freedesktop.IBus.session.GNOME.service
                   │ ├─3694 /usr/bin/ibus-daemon --panel disable
                   │ ├─3860 /usr/libexec/ibus-dconf
                   │ ├─3862 /usr/libexec/ibus-extension-gtk3
                   │ └─4061 /usr/libexec/ibus-engine-simple
                   ├─org.gnome.SettingsDaemon.A11ySettings.service
                   │ └─3698 /usr/libexec/gsd-a11y-settings
                   ├─org.gnome.SettingsDaemon.Color.service
                   │ └─3700 /usr/libexec/gsd-color
                   ├─org.gnome.SettingsDaemon.Datetime.service
                   │ └─3704 /usr/libexec/gsd-datetime
                   ├─org.gnome.SettingsDaemon.Housekeeping.service
                   │ └─3708 /usr/libexec/gsd-housekeeping
                   ├─org.gnome.SettingsDaemon.Keyboard.service
                   │ └─3711 /usr/libexec/gsd-keyboard
                   ├─org.gnome.SettingsDaemon.MediaKeys.service
                   │ └─3721 /usr/libexec/gsd-media-keys
                   ├─org.gnome.SettingsDaemon.Power.service
                   │ └─3722 /usr/libexec/gsd-power
                   ├─org.gnome.SettingsDaemon.PrintNotifications.service
                   │ ├─3727 /usr/libexec/gsd-print-notifications
                   │ └─3937 /usr/libexec/gsd-printer
                   ├─org.gnome.SettingsDaemon.Rfkill.service
                   │ └─3731 /usr/libexec/gsd-rfkill
                   ├─org.gnome.SettingsDaemon.ScreensaverProxy.service
                   │ └─3734 /usr/libexec/gsd-screensaver-proxy
                   ├─org.gnome.SettingsDaemon.Sharing.service
                   │ └─3739 /usr/libexec/gsd-sharing
                   ├─org.gnome.SettingsDaemon.Smartcard.service
                   │ └─3742 /usr/libexec/gsd-smartcard
                   ├─org.gnome.SettingsDaemon.Sound.service
                   │ └─3750 /usr/libexec/gsd-sound
                   ├─org.gnome.SettingsDaemon.UsbProtection.service
                   │ └─3769 /usr/libexec/gsd-usb-protection
                   ├─org.gnome.SettingsDaemon.Wwan.service
                   │ └─3806 /usr/libexec/gsd-wwan
                   ├─org.gnome.SettingsDaemon.XSettings.service
                   │ ├─4291 /usr/libexec/gsd-xsettings
                   │ └─4449 /usr/libexec/ibus-x11
                   ├─org.gnome.Shell@ubuntu.service
                   │ ├─3567 /usr/bin/gnome-shell --mode=ubuntu
                   │ ├─3946 /usr/bin/Xwayland :0 -rootless -noreset -accessx -core -auth /run/user/1000/.mutter-Xwaylandauth.GRW0X3 -listenfd 4 -listenfd 5 -displayfd 6 -initfd 7 -byteswappedclients -enable-ei-portal
                   │ ├─4349 /usr/libexec/mutter-x11-frames
                   │ └─5119 gjs /usr/share/gnome-shell/extensions/ding@rastersoft.com/app/ding.js -E -P /usr/share/gnome-shell/extensions/ding@rastersoft.com/app
                   ├─pipewire-pulse.service
                   │ └─3312 /usr/bin/pipewire-pulse
                   ├─pipewire.service
                   │ └─3301 /usr/bin/pipewire
                   ├─wireplumber.service
                   │ └─3308 /usr/bin/wireplumber
                   ├─xdg-desktop-portal.service
                   │ └─3945 /usr/libexec/xdg-desktop-portal
                   ├─xdg-document-portal.service
                   │ ├─3496 /usr/libexec/xdg-document-portal
                   │ └─3521 fusermount3 -o rw,nosuid,nodev,fsname=portal,auto_unmount,subtype=portal -- /run/user/1000/doc
                   └─xdg-permission-store.service
                     └─3509 /usr/libexec/xdg-permission-store

![[Ejercicio4Servicio 1.png]]

==🔴Interpretación técnica:==

El comando `ps` sirve para ver los programas que se están corriendo en este momento en la pantalla.
El comando `systemctl status` sirve para ver todos los servicios que están funcionando en el fondo del sistema de forma automática (como la red o un servidor web).

==🔴Decisión o siguiente prueba:==

Como ya se vieron los servicios que están corriendo en el fondo, ahora se comprobará por qué puertos se están comunicando y se revisará el historial de la máquina.


#### Ejercicio 5: Relacionar puerto y evidencia

==🔴Comando o acción:==

ss -ltnp
journalctl

==🔴Salida relevante:==

ubuntu@UbuntuLinux:~$ ss -ltnp
State                          Recv-Q                          Send-Q                                                   Local Address:Port                                                   Peer Address:Port                         Process                         
LISTEN                         0                               511                                                            0.0.0.0:80                                                          0.0.0.0:*                                                            
LISTEN                         0                               4096                                                           0.0.0.0:22                                                          0.0.0.0:*                                                            
LISTEN                         0                               10                                                         10.10.24.80:53                                                          0.0.0.0:*                                                            
LISTEN                         0                               4096                                                         127.0.0.1:631                                                         0.0.0.0:*                                                            
LISTEN                         0                               5                                                            127.0.0.1:953                                                         0.0.0.0:*                                                            
LISTEN                         0                               4096                                                     127.0.0.53%lo:53                                                          0.0.0.0:*                                                            
LISTEN                         0                               4096                                                        127.0.0.54:53                                                          0.0.0.0:*                                                            
LISTEN                         0                               511                                                               [::]:80                                                             [::]:*                                                            
LISTEN                         0                               4096                                                              [::]:22                                                             [::]:*                                                            
LISTEN                         0                               5                                                                [::1]:953                                                            [::]:*                                                            
LISTEN                         0                               4096                                                             [::1]:631                                                            [::]:*              

ubuntu@UbuntuLinux:~$ journalctl
Aug 21 01:15:00 UbuntuLinux kernel: Linux version 7.0.0-30-generic (buildd@lcy02-amd64-048) (x86_64-linux-gnu-gcc (Ubuntu 15.2.0-16ubuntu1) 15.2.0, GNU ld (GNU Binutils for Ubuntu) 2.46) #30-Ubuntu SMP PREEMPT_DYNAMIC Fri Jul 31 18:22:54 UTC 2026 (Ubuntu 7.0.0-3>
Aug 21 01:15:00 UbuntuLinux kernel: Command line: BOOT_IMAGE=/boot/vmlinuz-7.0.0-30-generic root=UUID=e9527353-f321-42ca-9804-36e45da461e7 ro crashkernel=2G-4G:320M,4G-32G:512M,32G-64G:1024M,64G-128G:2048M,128G-:4096M
Aug 21 01:15:00 UbuntuLinux kernel: KERNEL supported cpus:
Aug 21 01:15:00 UbuntuLinux kernel:   Intel GenuineIntel
Aug 21 01:15:00 UbuntuLinux kernel:   AMD AuthenticAMD
Aug 21 01:15:00 UbuntuLinux kernel:   Hygon HygonGenuine
Aug 21 01:15:00 UbuntuLinux kernel:   Centaur CentaurHauls
Aug 21 01:15:00 UbuntuLinux kernel:   zhaoxin   Shanghai  
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-provided physical RAM map:
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [mem 0x0000000000000000-0x000000000009fbff]  System RAM
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [mem 0x000000000009fc00-0x000000000009ffff]  device reserved
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [gap 0x00000000000a0000-0x00000000000effff]
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [mem 0x00000000000f0000-0x00000000000fffff]  device reserved
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [mem 0x0000000000100000-0x00000000dffeffff]  System RAM
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [mem 0x00000000dfff0000-0x00000000dfffffff]  ACPI data
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [gap 0x00000000e0000000-0x00000000febfffff]
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [mem 0x00000000fec00000-0x00000000fec00fff]  device reserved
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [gap 0x00000000fec01000-0x00000000fedfffff]
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [mem 0x00000000fee00000-0x00000000fee00fff]  device reserved
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [gap 0x00000000fee01000-0x00000000fffbffff]
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [mem 0x00000000fffc0000-0x00000000ffffffff]  device reserved
Aug 21 01:15:00 UbuntuLinux kernel: BIOS-e820: [mem 0x0000000100000000-0x000000011fffffff]  System RAM
Aug 21 01:15:00 UbuntuLinux kernel: NX (Execute Disable) protection: active
Aug 21 01:15:00 UbuntuLinux kernel: APIC: Static calls initialized
Aug 21 01:15:00 UbuntuLinux kernel: SMBIOS 2.5 present.
Aug 21 01:15:00 UbuntuLinux kernel: DMI: innotek GmbH VirtualBox/VirtualBox, BIOS VirtualBox 12/01/2006
Aug 21 01:15:00 UbuntuLinux kernel: DMI: Memory slots populated: 0/0
Aug 21 01:15:00 UbuntuLinux kernel: Hypervisor detected: KVM
Aug 21 01:15:00 UbuntuLinux kernel: last_pfn = 0xe0000 max_arch_pfn = 0x400000000
Aug 21 01:15:00 UbuntuLinux kernel: kvm-clock: Using msrs 4b564d01 and 4b564d00
Aug 21 01:15:00 UbuntuLinux kernel: kvm-clock: using sched offset of 1815978746157 cycles
Aug 21 01:15:00 UbuntuLinux kernel: clocksource: kvm-clock: mask: 0xffffffffffffffff max_cycles: 0x1cd42e4dffb, max_idle_ns: 881590591483 ns
Aug 21 01:15:00 UbuntuLinux kernel: tsc: Detected 2495.998 MHz processor
Aug 21 01:15:00 UbuntuLinux kernel: e820: update [mem 0x00000000-0x00000fff] System RAM ==> device reserved
Aug 21 01:15:00 UbuntuLinux kernel: e820: remove [mem 0x000a0000-0x000fffff] System RAM
Aug 21 01:15:00 UbuntuLinux kernel: last_pfn = 0x120000 max_arch_pfn = 0x400000000
Aug 21 01:15:00 UbuntuLinux kernel: MTRR map: 3 entries (3 fixed + 0 variable; max 19), built from 8 variable MTRRs
Aug 21 01:15:00 UbuntuLinux kernel: x86/PAT: Configuration [0-7]: WB  WC  UC- UC  WB  WP  UC- WT  
Aug 21 01:15:00 UbuntuLinux kernel: CPU MTRRs all blank - virtualized system.
Aug 21 01:15:00 UbuntuLinux kernel: last_pfn = 0xe0000 max_arch_pfn = 0x400000000
Aug 21 01:15:00 UbuntuLinux kernel: found SMP MP-table at [mem 0x0009fbf0-0x0009fbff]
Aug 21 01:15:00 UbuntuLinux kernel: RAMDISK: [mem 0x32e0b000-0x356fcfff]
Aug 21 01:15:00 UbuntuLinux kernel: ACPI: Early table checksum verification disabled
Aug 21 01:15:00 UbuntuLinux kernel: ACPI: RSDP 0x00000000000E0000 000024 (v02 VBOX  )


![[Ejercicio5PuertoEvidencia.png]]

==🔴Interpretación técnica:==

El comando `ss -ltnp` sirve para ver qué puertos de red están abiertos y escuchando (como el puerto 80 y el 22).
El comando `journalctl` sirve para leer el historial de mensajes del sistema, lo que ayuda a confirmar que se está usando una máquina virtual de VirtualBox.

==🔴Decisión o siguiente prueba:==

Como conclusión de esta primera práctica, logré inspeccionar correctamente mi entorno de trabajo en Linux, así como, pude identificar las características del sistema, comprobar mi usuario, examinar el manejo de mis archivos y observar el comportamiento de los servicios y la red, cumpliendo de forma exitosa con todos los objetivos de la tarea.