# qw
quick wireless - bash script to quickly switch wireless modes

With qw you can setup a preconfigured access point and connect clients to it with a single command. In addition the script can be used to sniff in monitor mode, deauth clients from a network and capture the handshake all with only a single and short command for each action.

Furthermore the script can be used to connect to any open or wpa protected network, change and reset the mac address, sniff with airodump-ng and to kill/stop processes which might interfere.

## Installation
The following tools are needed
* hostapd
* dnsmasq
* wpa\_supplicant
* aircrack-ng
* macchanger

I recommend putting the qw file into the PATH

## Howto
To setup an access point with the parameters configured inside the qw script just run

    qw a

on all the clients run

    qw c

to connect to the access point and to request an IP address via dhcp.

The content of the default config files for hostapd and wpa\_supplicant are 
included in the script for portablity reasons. To customize the settings
just edit the lines in the script.
Be sure to change the wpa passphrase.

If you want to record a wpa handshake start sniffing in monitor mode using 
airodump-ng and pass the outfile in the channel parameter. Afterwards run the deauth 
attack against the access point.

    qw s "2 -w outfile"
    qw d <bssid>

To kill every process which might interfere and put the interface down run

    qm k

Warning: this stops/kills the following processes without prompting:
NetworkManager, dhclient, wpa\_supplicant, dnsmasq and hostapd

For more information on the underlying mechanisms check out my website exitno.de for 
[wlan via command line](http://exitno.de/linux_wlan/) or
for [wlan attacks](http://exitno.de/wlan_attacks/).
