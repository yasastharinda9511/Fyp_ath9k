# Fyp_ath9k
custom beacon generation

The main goal of this repo is to aquire the qos for the management frames.
In this repo contains only two files where we had made our major changes to get the 
qos for the mangement frames. The main changes are done inside the mac80211 tx.c file and 
ath9k_htc_txrx.c located inside the ath9k driver. We used the linux backport 5.4.56-1 for this linux driver customiation.

## Step to download and install to new linux backport
