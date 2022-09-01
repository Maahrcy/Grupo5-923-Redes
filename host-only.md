## Host-Only 

1. *ARQUIVO* --> *HOST NETWORK MANAGER*
2. *HABILITAR SERVIDOR DHCP*

Os passos a seguir devem ser realizados em ambas as VMs

3. Acesse as _configurações_ da VM --> _Rede_ --> adicione um *ADAPTADOR 2*
4. No terminal da VM, digite o comando: 
```
sudo nano /etc/netplan/01-netcfg.yaml
```
5. Altere o arquivo anterior da seguinte forma: 
```
network: 
  ethernets:
    enp0s3:
      addresses: [192.168.23.66/28]
      # Por exemplo: 
      # addresses: [192.168.23.[64-78]/28] 
      gateway4: 192.168.23.79
      dhcp4: false
    enp0s8:
      dhcp4: true
  version: 2
```
6. Aplique as configurações a partir do seguinte comando:
```
sudo netplan apply
```
