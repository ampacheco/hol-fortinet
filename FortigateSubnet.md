# Create Fortigate Subnet

````
az network vnet create -g lab-ftnt-rg \
-n hub-vet --address-prefix 10.1.0.0/16 \
--subnet-name ExternalSubnet --subnet-prefixes 10.1.1.0/24 \
--subnet-name InternalSubnet --subnet-prefixes 10.1.2.0/24 \
--subnet-name HASyncSubnet --subnet-prefixes 10.1.0.3/24 \
--subnet-name HAMGMTSubnet  --subnet-prefixes 10.1.3.0/24 \
--subnet-name ProteatedASubnet --subnet-prefixes 10.1.5.0/24
````