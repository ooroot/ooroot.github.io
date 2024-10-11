---
title: 双网关双dns
description: 双网关双dns，进行内外网各走一套
date: 2024-10-11
image: images/
categories:
    - code
tags:
  - 网络
  - 路由器
  - dns
  - gateway
---

本文只是记录
opwrt主路由+paopaogateway网关+paopaodns外网dns+adgh内网dns

架构
opwrt主路由:
ip:192.168.1.1 
网关:192.168.1.1
dns:192.168.1.1

paopaogateway网关
ip:192.168.1.2
网关:192.168.1.1
192.168.1.1

paopaodns DNS
ip:192.168.1.4
网关:192.168.1.1
adgh DNS
IP:192.168.1.1:3000
劫持opwrt主路由dns:53端口作为国内dns

ppgw.ini配置文件
```
#paopao-gateway

# mode=socks5|ovpn|yaml|suburl|free
# default: free
mode=free

# Set fakeip's CIDR here
# default: fake_cidr=7.0.0.0/8
fake_cidr=7.0.0.0/8

# Set your trusted DNS here
# default: dns_ip=1.0.0.1
dns_ip=10.10.10.8
# default: dns_port=53
# If used with PaoPaoDNS, you can set the 5304 port
dns_port=5304

# Clash's web dashboard
clash_web_port="80"
clash_web_password="clashpass"

# default：openport=no
# socks+http mixed 1080
openport=no

# default: udp_enable=no
udp_enable=no

# default:30
sleeptime=30

# socks5 mode settting
# default: socks5_ip=gatewayIP
socks5_ip="10.10.10.5"
# default: socks5_port="7890"
socks5_port="7890"

# ovpn mode settting
# The ovpn file in the same directory as the ppgw.ini.
# default: ovpnfile=custom.ovpn
ovpnfile="custom.ovpn"
ovpn_username=""
ovpn_password=""

# yaml mode settting
# The yaml file in the same directory as the ppgw.ini.
# default: yamlfile=custom.yaml
yamlfile="custom.yaml"

# suburl mode settting
suburl="https://..."
subtime=1d

# fast_node=check/yes/no
fast_node=yes
test_node_url="https://www.youtube.com/generate_204"
ext_node="Traffic|Expire| GB|Days|Date"
cpudelay="3000"
fall_direct="no"
# dns burn setting
# depend on fast_node=yes & mode=suburl/yaml
dns_burn=no
# If used with PaoPaoDNS, you can set the PaoPaoDNS:53
ex_dns="223.5.5.5:53"

# Network traffic records
net_rec=no
max_rec=5000
```
