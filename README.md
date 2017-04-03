# netifd

This is a fork of the official **netifd** project of OpenWRT/LEDE distribution.


# Purpose

The repository is a playground for a personal project.  My goal is to provide
means of configuring a device in *Client mode* with several wireless networks.

So if this device is moved to other area with other wireless network available,
no additional reconfiguration would be required.


# Configuration

Example of desired configuration defined in `/etc/config/wireless`:

    config wifi-device 'radio0'
            option type 'mac80211'
            option channel 'auto'
            option hwmode '11g'
            option path 'platform/10300000.wmac'
            option htmode 'HT20'
            option disabled '0'

    config wifi-credentials 'wireless0'
            option encryption 'psk2'
            option ssid 'ssid0'
            option key 'key0'

    config wifi-credentials 'wireless1'
            option encryption 'psk2'
            option ssid 'ssid1'
            option key 'key1'

    config wifi-iface 'default_radio0'
            option device 'radio0'
            option network 'wwan'
            option mode 'sta'
            list   credentials 'wireless0'
            list   credentials 'wireless1'
