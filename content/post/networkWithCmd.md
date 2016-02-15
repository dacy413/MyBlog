+++
categories = ["Linux"]
date = "2016-02-05T08:14:44+08:00"
description = "connect wireless with command line"
keywords = ["network"]
title = "connect wireless with cmd"

+++

et with command line

sudo iwlist scan

搜索当前环境下的wifi ssid

wpa_passphrase TRANTECT-NG winningeleven

将psk复制到下面的example中

wlan example

auto wlan0 iface wlan0 inet dhcp netmask 255.255.252.0 gateway 192.168.0.6 wpa-driver wext wpa-ssid TRANTECT-NG wpa-ap-scan 1 wpa-proto WPA wpa-pairwise CCMP wpa-group CCMP wpa-key-mgmt WPA-PSK wpa-psk 819c97624cbd806dbeb3a1de0c46943b3257281fec0a38c538de5ce7fb59d312
