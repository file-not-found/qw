# qw
quick wireless - bash script to quickly switch wireless modes

## Installation
The following tools are needed
* hostapd
* dnsmasq
* wpa\_supplicant
* aircrack-ng
* macchanger

I recommend putting the qw file into the PATH

## Howto
Print help

    qw

Start hostapd and dnsmasq. If a default route is found forwarding and NAT are enabled.
If a ssid is given the user will be prompted for a WPA2 passphrase as well.

    qw a [ssid]

Connect to an AP using wpa\_supplicant. If a ssid is given the user will be promted for the
WPA passphrase.

    qw c [ssid]

Sniff in monitor mode using airodump-ng

    qw s

You can misuse the channel to pass multiple parameters to airodump-ng

    qw s "2 -w outfile"

Set interface in managed mode

    qw m

Kill every process which might interfere and put interface down
Warning: this stops/kills the following processes without prompting
(NetworkManager, dhclient, wpa\_supplicant, dnsmasq, hostapd)

    qm k

Set random mac using macchanger

    qm r

Reset permanent mac using macchanger

    qm p

The content of the default config files for hostapd and wpa\_supplicant are 
included in the script for portablity reasons. To customize the settings
just edit the lines in the script.
Be sure to change the wpa2 passphrase.
