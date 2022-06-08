## Min/Max supported subnet sizing
* Min IPv4 - /29
* Max IPv4 - /2
* IPv6 must be exactly /64

## Ranges that can be used: 
```
10.0.0.0 - 10.255.255.255 (10/8 prefix)
172.16.0.0 - 172.31.255.255 (172.16/12 prefix)
192.168.0.0 - 192.168.255.255 (192.168/16 prefix)
```

## You cannot add the following address ranges:
```
224.0.0.0/4 (Multicast)
255.255.255.255/32 (Broadcast)
127.0.0.0/8 (Loopback)
169.254.0.0/16 (Link-local)
168.63.129.16/32 (Internal DNS, DHCP, and Azure Load Balancer health probe)
```

## IP address restrictions within a subnet
Azure reserves the first 4 and last IP address for a total of 5 IP addresses. 
### Example
Using range of 192.168.1.0/24 the below addresses would be reserved by Azure: 
* 192.168.1.0 : Network address
* 192.168.1.1 : Reserved by Azure for the default gateway
* 192.168.1.2, 192.168.1.3 : Reserved by Azure to map the Azure DNS IPs to the VNet space
* 192.168.1.255 : Network broadcast address.

## Dedicated subnet recommendations
* GatewaySubnet /27
* AzureFirewallSubnet /26
* AzureBastionSubnet /26

see, https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-for-azure-services

## Application Gateway

* Application Gateway (Standard or WAF) SKU can support up to 32 instances (32 instance IP addresses + 1 private front-end IP + 5 Azure reserved) – so a minimum subnet size of /26 is recommended

* Application Gateway (Standard_v2 or WAF_v2 SKU) can support up to 125 instances (125 instance IP addresses + 1 private front-end IP + 5 Azure reserved). A minimum subnet size of /24 is recommended.

> Although a /24 subnet is not required per Application Gateway v2 SKU deployment, it is highly recommended. This is to ensure that Application Gateway v2 has sufficient space for autoscaling expansion and maintenance upgrades. You should ensure that the Application Gateway v2 subnet has sufficient address space to accommodate the number of instances required to serve your maximum expected traffic. If you specify the maximum instance count, then the subnet should have capacity for at least that many addresses. 
