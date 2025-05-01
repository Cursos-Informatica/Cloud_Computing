# Notas del laboratorio 02

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

## Como conectarte a una VM a través de SSH

```
ssh azureuser@<IP_PUBLICA>
```

## Obtener los puerto disponibles

```
az network nsg rule list \
  --nsg-name my-vmNSG  --resource-group learn-1b15e28a-1a68-4407-af6f-0dd2d1fc914f  --output table
```