# Fyp_ath9k
custom beacon generation

The main goal of this repo is to aquire the qos for the management frames.
In this repo contains only two files where we had made our major changes to get the 
qos for the mangement frames. The main changes are done inside the mac80211 tx.c file and 
ath9k_htc_txrx.c located inside the ath9k driver. We used the linux backport 5.4.56-1 for this linux driver customiation amd 
raspberry pi-3b+.

## Step to download and install linux backport (5.4.56-1)
  
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

![image](https://user-images.githubusercontent.com/37435024/99914136-47667600-2d21-11eb-9f74-9490645e74ac.jpeg)

