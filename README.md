# qw
quick wireless - bash script to quickly switch wireless modes

## Installation
The following tools are needed
* hostapd
* dnsmasq
* wpa_supplicant
* aircrack-ng
* macchanger

I recommend putting the qw file into the PATH

## Warning
The script stops/kills the following processes without prompting
* NetworkManager
* dhclient
* wpa_supplicant
* dnsmasq
* hostapd

## Howto

    qw

prints a short help.

You can misuse the channel to pass multiple parameters to airodump-ng

    qw s "2 -w outfile"

The content of the config files for hostapd and wpa_supplicant are 
included in the script for portablity reasons. To customize the settings
just edit the lines in the script.
Be sure to change the wpa2 passphrase.
