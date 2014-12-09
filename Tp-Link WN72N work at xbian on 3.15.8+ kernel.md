# xbian Tp-link WN725N Config on 3.15.8+ kernel

issue link:<https://github.com/xbianonpi/xbian/issues/640>

## 解决方法在<http://forum.xbian.org/thread-2524-post-24993.html#pid24993>:


shell:

	sudo mkdir /lib/firmware/rtlwifi; 
    sudo wget -O /lib/firmware/rtlwifi/rtl8188efw.bin https://github.com/OpenELEC/wlan-firmware/blob/master/firmware/rtlwifi/rtl8188efw.bin?raw=true
    sudo wget -O /lib/firmware/rtlwifi/rtl8188eufw.bin https://github.com/OpenELEC/wlan-firmware/blob/master/firmware/rtlwifi/rtl8188eufw.bin?raw=true

and editing my /etc/network/interfaces to:

    Code:
    auto lo
    
    iface lo inet loopback
    iface eth0 inet dhcp
    
    allow-hotplug wlan0
    iface wlan0 inet manual
    wpa-roam /etc/wpa_supplicant/wpa_supplicant.conf
    iface default inet dhcp
    
    
and my /etc/wpa_supplicant/wpa_supplicant.conf to:

Code:

    ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev update_config=1

    network={
    ssid="NETWORK_NAME"
    psk="NETWORK_PASSWORD"
    }
    
### 配置完第一次reboot出现system halted,拔电重启正常.

## 非xbian版本可以参看<http://www.raspberrypi.org/forums/viewtopic.php?p=462982>
  
 此帖子中有人写成了一个自动匹配内核版本的脚本,在这<https://dl.dropboxusercontent.com/u/80256631/install-8188eu.tgz> 