## link do HA
http://homeassistant.local:8123

https://rod70.xyz

--- 
## router pdf config
https://www.polsatbox.pl/Edimax_LT-6408n_instrukcja_obslugi.pdf

---
## Jak zainstalować HA na kompie bez UEFI
https://community.home-assistant.io/t/install-ha-on-old-laptop-without-uefi/407443/38
```
Thank you both @dbrand666 and @blind-oracle – its working great! This is how I did it (hoping it helps other newbies) with both your help:
Using Debian 11 Live I installed HAOS @ Terminal:
Logged in as root user

sudo su -

Downloaded and installed Home Assistant

curl -L https://github.com/home-assistant/operating-system/releases/download/9.4/haos_generic-x86-64-9.4.img.xz |xz -d >/dev/sda

Mounted sda1

sudo mount /dev/sda1 /mnt

Installed grub2

sudo apt install grub2
sudo grub-install --compress=xz --root-directory=/mnt /dev/sda --force
Configured the grub.cfg file

cat <<! | sudo dd of=/mnt/boot/grub/grub.cfg
set root=(hd0,gpt1)
configfile (hd0,gpt1)/efi/boot/grub.cfg
!
Unmount sda1

sudo umount /dev/sda1
exit
Closed Terminal, shutdown pc, removed Debian 11 Live boot usb and restarted x86-64-bit system with a non-UEFI Legacy BIOS.

Thank you both, I could not have done it without your support – onward to Automation Creation!
```


---
## jakieś
https://community.home-assistant.io/t/how-to-scroll-in-hasio-console/291904/7

https://community.home-assistant.io/t/manually-updated-sensor-how-to/174137


---
## duckDNS nie działa jeśli nie ma się publicznego IP :(
https://www.duckdns.org/login-google?state=uhiuhogyufowaeohawhesauoi&code=4%2F0AfJohXm5-e9ljp_jg3xI3EedgBJ4LvDWVBIMQOAR8Hu9i4zbfiU0lm_gDUvC-fZM9xo6rw&scope=email+openid+https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fuserinfo.email&authuser=0&prompt=none
http://jkrod.duckdns.org/

---
## plugin do DHT 11 podłaczeonego do RPI - uwaga, mozna spalić urządzenie xd
https://github.com/richardzone/homeassistant-dht

![image](https://github.com/fbrzuzka/home-assistant-configuration/assets/8392787/104170d6-cf94-4b83-94b3-576824c2e8dc)

