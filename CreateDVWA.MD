## Create DMZ
````
# Create Resource Group
az group create -l eastus -n 000-apacheco-lab-ftnt-rg
 
# Create VNET
az network vnet create -g 000-apacheco-lab-ftnt-rg -n workload-vnet --address-prefix 10.3.0.0/16 --subnet-name dmz-protected-a --subnet-prefixes 10.3.0.0/24
 
# Create NSG
az network nsg create -n dmz-nsg -g 000-apacheco-lab-ftnt-rg 
 
# Creaate NSG Rule
az network nsg rule create -g 000-apacheco-lab-ftnt-rg --nsg-name dmz-nsg -n AllowSshIngress --priority 1000 --protocol TCP --destination-port-range 22 --access allow
 
# Create VM
az vm create -n linuxssh -g 000-apacheco-lab-ftnt-rg --image UbuntuLTS --admin-username azureadmin --admin-password <set-a-password> --vnet-name workload-vnet --subnet dmz-protected-a --nsg dmz-nsg --public-ip-address ""
az vm create -n dvwa -g 000-apacheco-lab-ftnt-rg --image UbuntuLTS --admin-username azureadmin --admin-password <set-a-password> --vnet-name workload-vnet --subnet dmz-protected-a --nsg dmz-nsg --public-ip-address ""
````

## Post Install Tasks on dvwa VM
````
sudo snap install docker
sudo groupadd docker
sudo usermod -aG docker $USER
````

## Install and Run Docker Container
````
docker pull vulnerables/web-dvwa
docker run --restart=always -p 80:80 -d --name dvwa vulnerables/web-dvwa
````
