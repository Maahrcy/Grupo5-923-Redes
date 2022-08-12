## Nomes estáticos
Os passos a seguir devem ser realizados em todas as VMs de todos os PCs
1. No terminal, digite o comando: 
```
sudo nano /etc/hosts
```
2. Altere o arquivo anterior da seguinte forma: 
```
127.0.0.1 localhost
127.0.1.1 <hostname>
192.168.23.[64-78] <hostname> <fdqn> <aliases>
```
- VMs conectadas da VM1 do PC2:
```
127.0.0.1 localhost
127.0.1.1 srv-vm1-pc2-macielly
192.168.23.78 srv-vm1-pc1-julia julia01-pc1.grupo5-923.ifalara.net vpn
192.168.23.65 srv-vm2-pc1-julia julia02-pc1.grupo5-923.ifalara.net mail
192.168.23.66 srv-vm1-pc2-macielly macielly01-pc2.grupo5-923.ifalara.net www
192.168.23.67 srv-vm2-pc2-macielly macielly02-pc2.grupo5-923.ifalara.net file
192.168.23.68 srv-vm1-pc3-catielly catielly01-pc3.grupo5-923.ifalara.net mysql
192.168.23.69 srv-vm2-pc3-catielly catielly02-pc3.grupo5-923.ifalara.net ssd
```
