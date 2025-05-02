# Notas del laboratorio 02

## Creación de una máquina virtual Linux

az vm create \
  --resource-group "learn-7e60be08-18d9-47e7-8206-f0da559201d5" \
  --name my-vm \
  --public-ip-sku Standard \
  --image Ubuntu2204 \
  --admin-username azureuser \
  --generate-ssh-keys    

## instalación de Nginx
  az vm extension set \
  --resource-group "learn-7e60be08-18d9-47e7-8206-f0da559201d5" \
  --vm-name my-vm \
  --name customScript \
  --publisher Microsoft.Azure.Extensions \
  --version 2.1 \
  --settings '{"fileUris":["https://raw.githubusercontent.com/MicrosoftDocs/mslearn-welcome-to-azure/master/configure-nginx.sh"]}' \
  --protected-settings '{"commandToExecute": "./configure-nginx.sh"}'    

## Como conectarte a una VM a través de SSH

```
ssh azureuser@<IP_PUBLICA>
```

## Revisar el servicio de NGINX
Ver el estatus del servicio
```
sudo systemctl status nginx
```
Ver si el proceso esta corriendo
```
ps aux | grep nginx
```
Ver si el puerto esta en modo LISTENING

```
sudo netstat -tulnp | grep nginx
```
ó
```
sudo ss -tulnp | grep nginx
```

## Mostrar lista de virtual machine

```
az vm list
```

## Obtener Ips de una maquina virtual

```
az vm list-ip-addresses  \
--name my-vm --resource-group learn-1b15e28a-1a68-4407-af6f-0dd2d1fc914f --output table
```

| VirtualMachine | PublicIPAddresses | PrivateIPAddresses |
|----------------|-------------------|--------------------|
|my-vm           | 172.184.177.243   | 10.0.0.4           |


## Creación de la regla de seguridad de red

az network nsg rule create --resource-group "learn-7e60be08-18d9-47e7-8206-f0da559201d5" --nsg-name my-vmNSG --name allow-http --protocol tcp --priority 100 --destination-port-range 80 --access Allow

## Visualizar de la regla de seguridad de red
az network nsg rule list --resource-group "learn-7e60be08-18d9-47e7-8206-f0da559201d5" --nsg-name my-vmNSG --query '[].{Name:name, Priority:priority, Port:destinationPortRange, Access:access}' --output table



