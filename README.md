# Turn old laptop into a server project
The first thing is to create a booteable USB with ubuntu server.
Then install it on an old laptop. It's important to unset the option "Set up this disk as an LVM group".
When installation has finished use `ip link` to get the network interface names. The one that start with W is the interface for wifi (for example wlan0).
Use `ip link set WIFI_INTERFACE_NAME up` to activate the interface (if it's not activated).
Use `iwlist WIFI_INTERFACE_NAME scan` to scan wifi networks available
USe `wpa_passphrase WIFI_NETWORK PASS_WORD > /etc/wifi` to save config of a network on /etc/wifi
Use `wpa_supplicant -B -i WIFI_INTERFACE_NAME -D wext -c /etc/wifi` to connect

