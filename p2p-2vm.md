## Rede P2P com duas VMs 
Os próximos passos devem ser realizados em ambas as VMs
1. Execute a VM
2. Logue em _administrador_ com a senha _adminifal_
3. No terminal da VM, digite o comando:
```
sudo apt install net-tools -y 
sudo nano /etc/netplan/01-netcfg.yaml # para editar o arquivo
```
4. Edite o arquivo anterior da seguinte forma: 
```
network: 
  ethernets:
    enp0s3:
      addresses: [192.168.23.[64-78]/28] 
      # Por exemplo: 
      # addresses: [192.168.23.66/28]
      gateway4: 192.168.23.79
      dhcp4: false
  version: 2
```

<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/netplan-cfg-img.jpeg' width='500' height='300'>

5. Salve o arquivo com _Control X_ --> _Y_ --> _Enter_
6. Aplique as configurações com o seguinte comando: 
```
sudo netplan apply
```
Após realizados os passos anteriores em ambas as VMs, feche-as e acesse as _configurações_ da VM --> _Rede_

7. Altere o *ADAPTADOR 1* para *REDE INTERNA*
8. Altere o *NOME* para _labredes_
Faça os passos anteriores em ambas as VMs
9. Execute as VMs novamente e teste o ping nas VMs com o comando: 
```
ping 192.168.23.[64-78]
```
Por exemplo, caso o endereço IP da VM1 seja 192.168.23.66 e o endereço IP da VM2 seja 192.168.23.67, o comando a ser digitado:
- Na VM1: 
```
ping 192.168.23.67
```
- Na VM2:
```
ping 192.168.23.66
```
