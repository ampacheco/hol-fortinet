## Create Fortigate Subnet

````
# add network
az network vnet create -g lab-ftnt-rg -n hub-vnet --address-prefix 10.1.0.0/16

# add subnetworks
az network vnet subnet create --vnet-name hub-vnet -g 000-apacheco-lab-ftnt-rg -n ExternalSubnet --address-prefixes 10.1.1.0/24
az network vnet subnet create --vnet-name hub-vnet -g 000-apacheco-lab-ftnt-rg -n InternalSubnet --address-prefixes 10.1.2.0/24
az network vnet subnet create --vnet-name hub-vnet -g 000-apacheco-lab-ftnt-rg -n HASyncSubnet --address-prefixes 10.1.3.0/24
az network vnet subnet create --vnet-name hub-vnet -g 000-apacheco-lab-ftnt-rg -n HAMGMTSubnet --address-prefixes 10.1.4.0/24
az network vnet subnet create --vnet-name hub-vnet -g 000-apacheco-lab-ftnt-rg -n ProtectedASubnet --address-prefixes 10.1.5.0/24
````

## Open Subnet Issue
