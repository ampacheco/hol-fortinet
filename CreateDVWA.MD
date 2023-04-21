 1936  az group create -l eastus -n lab-ftnt-rg
 1937  az vnet
 1938  az network vnet create -g lab-ftnt-rg -n workload-vnet --address-prefix 10.3.0.0/16 --subnet-name dmz-protected-a --subnet-prefixes 10.3.0.0/24
 1939  az vm create --help
 1940  az vm create -g lab-ftnt-rg -n linuxssh --image UbuntuLTS --authentication-type password --admin-username azureadmin --admin-password az vm create --helpaz vm create --helpPassw0rd --nsg-rule SSH --ports 22
 1941  az vm create -g lab-ftnt-rg -n linuxssh --image UbuntuLTS --authentication-type password --admin-username azureadmin --admin-password "az vm create -g lab-ftnt-rg -n linuxssh --image UbuntuLTS --authentication-type password --admin-username azureadmin --admin-password az vm create --helpaz vm create --helpPassw0rd --nsg-rule SSH --ports 22az vm create -g lab-ftnt-rg -n linuxssh --image UbuntuLTS --authentication-type password --admin-username azureadmin --admin-password az vm create --helpaz vm create --helpPassw0rd --nsg-rule SSH --ports 22Passw0rd" --nsg-rule SSH --port 22
 1942  az vm create -g lab-ftnt-rg -n linuxssh --image UbuntuLTS --authentication-type password --admin-username azureadmin --admin-password PassW0rd1234$ --nsg-rule SSH --port 22
 1943  az vm create -g lab-ftnt-rg -n linuxssh --image UbuntuLTS --authentication-type password --admin-username azureadmin --admin-password PassW0rd1234$ --nsg-rule SSH --ports 22
 1944  #[200~az network nsg rule create     --resource-group myResourceGroup     --nsg-name myNetworkSecurityGroup     --name myNetworkSecurityGroupRuleSSH     --protocol tcp     --priority 1000     --destination-port-range 22     --access allow~
 1945  az network nsg create --help
 1946  az network nsg rule create -g lab-ftnt-rg --nsg-name dmz-nsg --name openSSHPort --protocol tcp --priority 1000 --destination-port-range 22 --access allow
 1947  az network nsg rule create --resource-group lab-ftnt-rg --nsg-name dmz-nsg --name openSSHPort --protocol tcp --priority 1000 --destination-port-range 22 --access allow
 1948  az network nsg rule create --help
 1949  az network nsg rule create -g lab-ftnt-rg --nsg-name dmz-nsg -n AllowSshIngress --priority 1000 --protocol TCP --destination-port-range 22 --access allow
 1950  az network nsg create -n dmz-nsg -g lab-ftnt-rg 
 1951  az network nsg rule create -g lab-ftnt-rg --nsg-name dmz-nsg -n AllowSshIngress --priority 1000 --protocol TCP --destination-port-range 22 --access allow
 1952  az vm create -n linuxssh -g lab-ftnt-rg --image UbuntuLTS --admin-username azureadmin --admin-password PassW0rd0987# --help
 1953  az vm create -n linuxssh -g lab-ftnt-rg --image UbuntuLTS --admin-username azureadmin --admin-password PassW0rd0987# --vnet-name workload-vnet --subnet dmz-protected-a --nsg dmz-nsg
 1954  az vm create -n dvwa -g lab-ftnt-rg --image UbuntuLTS --admin-username azureadmin --admin-password PassW0rd0987# --vnet-name workload-vnet --subnet dmz-protected-a --nsg dmz-nsg
 1955  az vm create -n dvwa -g lab-ftnt-rg --image UbuntuLTS --admin-username azureadmin --admin-password PassW0rd0987# --vnet-name workload-vnet --subnet dmz-protected-a --nsg dmz-nsg --public-ip-address ""  
 1956  az vm create -n linuxssh -g lab-ftnt-rg --image UbuntuLTS --admin-username azureadmin --admin-password PassW0rd0987# --vnet-name workload-vnet --subnet dmz-protected-a --nsg dmz-nsg --public-ip-address ""  
 1957  az vm list -otable
