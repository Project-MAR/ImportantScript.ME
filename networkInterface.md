### network
```sh
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
   address   10.42.0.107
   netmask   255.255.255.0
   network   10.42.0.0
   broadcast 10.42.0.255
   gateway   10.42.0.1
   
auto wlan0
allow-hotplug wlan0
iface wlan0 inet dhcp
   wpa-ssid "My Secret SSID"
   wpa-psk "My SSID PSK"
   #Option
   #wpa-scan-ssid 1
   #wpa-ap-scan 1
   #wpa-key-mgmt WPA-PSK
   #wpa-proto RSN WPA
   #wpa-pairwise CCMP TKIP
   #wpa-group CCMP TKIP

```

### wpa-supplicant configuration

Open the wpa-supplicant configuration file

```sh
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```

add
```sh
network={
    ssid="The_ESSID_from_earlier"
    psk="Your_wifi_password"
}
```
If a hidden network, add 
```sh
scan_ssid=1
```

---

read more from [raspberry.org](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md) 
