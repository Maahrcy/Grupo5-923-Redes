## SSH 
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
