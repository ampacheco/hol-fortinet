 
 ````
 # Create Resource Group
 az group create -l eastus -n lab-ftnt-rg
 
 # Create VNET
 az network vnet create -g lab-ftnt-rg -n workload-vnet --address-prefix 10.3.0.0/16 --subnet-name dmz-protected-a --subnet-prefixes 10.3.0.0/24
 
 # Create NSG
 az network nsg create -n dmz-nsg -g lab-ftnt-rg 
 
 # Creaate NSG Rule
 az network nsg rule create -g lab-ftnt-rg --nsg-name dmz-nsg -n AllowSshIngress --priority 1000 --protocol TCP --destination-port-range 22 --access allow
 
 # Create VM
 az vm create -n linuxssh -g lab-ftnt-rg --image UbuntuLTS --admin-username azureadmin --admin-password PassW0rd0987# --vnet-name workload-vnet --subnet dmz-protected-a --nsg dmz-nsg
 az vm create -n dvwa -g lab-ftnt-rg --image UbuntuLTS --admin-username azureadmin --admin-password PassW0rd0987# --vnet-name workload-vnet --subnet dmz-protected-a --nsg dmz-nsg
 ````
