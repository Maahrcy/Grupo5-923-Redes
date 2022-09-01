## Modificando hostname das VMs
Os passos a seguir devem ser realizados em ambas as VMs

1. No terminal da VM, digite o comando: 
```
sudo hostnamectl set-hostname srv-vm[1-2]-pc[1-4]-<Nome> # Por exemplo: srv-vm1-pc2-macielly
```
2. Atualize o terminal a partir do comando: 
```
logout
```
Observe que, quando acessar novamente através do login, o hostname estará mudado:
<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/hostname.png' width='500' height='300'>
