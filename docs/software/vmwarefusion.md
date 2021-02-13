# VMware Fusion

> 优秀的高性能的虚拟机软件.

## 修改网络配置文件

`vim /Library/Preferences/VMware Fusion/networking`

```vim  
VERSION=1,0
answer VNET_1_DHCP yes
answer VNET_1_DHCP_CFG_HASH 62823A9C8549C06CC182955561BBC3E7A17770D9
answer VNET_1_HOSTONLY_NETMASK 255.255.255.0
answer VNET_1_HOSTONLY_SUBNET 172.16.10.0
answer VNET_1_VIRTUAL_ADAPTER yes
answer VNET_8_DHCP yes
answer VNET_8_DHCP_CFG_HASH 14D86E8401A013365D7A554A80400CAEECA2A7B9
answer VNET_8_HOSTONLY_NETMASK 255.255.255.0
answer VNET_8_HOSTONLY_SUBNET 192.168.123.0
answer VNET_8_NAT yes
answer VNET_8_VIRTUAL_ADAPTER yes
add_bridge_mapping en0 2
```

## 重启网络配置

```bash
sudo /Applications/VMware\ Fusion.app/Contents/Library/vmnet-cli --configure
sudo /Applications/VMware\ Fusion.app/Contents/Library/vmnet-cli --stop
sudo /Applications/VMware\ Fusion.app/Contents/Library/vmnet-cli --start
```

## 虚拟机添加和删除默认网关

```bash
route add default gw 192.168.123.2
route del -net 192.168.123.0 netmask 255.255.255.0
```
