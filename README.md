# Fyp_ath9k
custom beacon generation

The main goal of this repo is to aquire the qos for the management frames.
In this repo contains only two files where we had made our major changes to get the 
qos for the mangement frames. The main changes are done inside the mac80211 tx.c file and 
ath9k_htc_txrx.c located inside the ath9k driver. We used the linux backport 5.4.56-1 for this linux driver customiation amd 
raspberry pi-3b+.

## Step to download and install linux backport (5.4.56-1)

Following steps needs to be followed, 
  
  ```sudo apt-get update```
  
  ```sudo apt install raspberrypi-kernel-headers``` // to install the linuxkernel headers for the raspberry pi
  
  ```sudo apt-get install libncurses5-dev libncursesw5-dev```
  
  ```sudo apt-get install flex bison```
  
  ```wget https://cdn.kernel.org/pub/linux/kernel/projects/backports/stable/v5.4.56/backports-5.4.56-1.tar.xz```
  
  ```tar xf backports-5.4.56-1.tar.xz```
  
  ```cd backports-5.4.56-1```
  
  ```sudo make```
  
  ```sudo make install```
  
  ```sudo reboot```
  
## Injected Beacon frame path

Following diagram show how crafted beacon frames are transmited 
from ```mac80211```--> ```ath9k_htc```---> ```usb```. We did two majaor changes

1.  Make SKB priority in mac80211 tx.c inside ```ieee80211_monitor_start_xmit``` function
2.  Change the data path of the management frame inside the ath9k ```ath9k_tx_start``` function

![image](https://user-images.githubusercontent.com/37435024/99914136-47667600-2d21-11eb-9f74-9490645e74ac.jpeg)

## Enabing the debug mode of the of wireless devices

Type following command. Then blue screen will pop-up like below figure,
    
``` sudo make menuconfig```

![Screenshot (558)](https://user-images.githubusercontent.com/37435024/99941881-c47f0300-2d94-11eb-85fd-ea4b6abd28ff.png)

```Wireless LAN``` ---> ```Atheros ath9k_htc debugging```/ ``` Atheros ath9k debugging```



     
     
     
    
 



