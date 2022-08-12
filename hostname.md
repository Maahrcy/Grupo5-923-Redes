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

### SSH 
Os passos a seguir devem ser realizados em ambas as VMs
1. Acesse as _configurações_ da VM --> _Rede_ --> modifique *REDE INTERNA* para *NAT*
2. No terminal, digite o seguinte comando: 
```
sudo apt-get install openssh-server
```
3. Altere o _firewall_ para _allow_ a partir dos seguintes comandos: 
```
sudo ufw allow ssh
sudo ufw enable
```
