# Grupo5-923-Redes
Repositório para o projeto do 2º bimestre de Infraestrutura de Redes.

## Tabelas 

| DESCRIÇÃO  |  IP  |  hostname  |  FQDN  |  aliase  |
| ------------------- | ------------------- | ------------------- | ------------------- | ------------------- |
|  VM1-PC1-JULIA |  192.168.23.78/28 |  srv-vm1-pc1-julia |  julia01-pc1.grupo5-923.ifalara.net |  VPN |
|  VM2-PC1-JULIA |  192.168.23.65/28 |  srv-vm2-pc1-julia |  julia02-pc1.grupo5-923.ifalara.net |  mail |
|  VM1-PC2-MACIELLY |  192.168.23.66/28 |  srv-vm1-pc2-macielly |  macielly01-pc2.grupo5-923.ifalara.net |  www |
|  VM2-PC2-MACIELLY |  192.168.23.67/28 |  srv-vm2-pc2-macielly |  macielly02-pc2.grupo5-923.ifalara.net |  file |
|  VM1-PC3-CATIELLY |  192.168.23.68/28 |  srv-vm1-pc3-catielly |  catielly01-pc3.grupo5-923.ifalara.net |  mysql |
|  VM2-PC3-CATIELLY |  192.168.23.69/28 |  srv-vm2-pc3-catielly |  catielly02-pc3.grupo5-923.ifalara.net |  ssd |
|  VM1-PC4-FERNANDA |  192.168.23.70/28 |  srv-vm1-pc4-fernanda |  fernanda01-pc4.grupo5-923.ifalara.net |  nobody |
|  VM2-PC4-FERNANDA |  192.168.23.71/28 |  srv-vm2-pc4-fernanda |  fernanda02-pc4.grupo5-923.ifalara.net |  core |

[Acessar o documento com as tabelas](https://docs.google.com/spreadsheets/d/1wC8-0qN_uJ9s-l_1ESp-2WHDWGVcQKEaONAI2HTbjAo/edit?usp=sharing)

## Tutorial Passo-a-Passo

[Criando uma máquina virtual](creating.md)

### Criando uma máquina virtual

1. Abrir o terminal no PC LINUX
2. No terminal, digite o comando:
```
su redes
```
3. Logue em _redes_ com a senha _admin@Lab92_
4. No terminal, digite o comando: 
```
sudo mkdir /labredes # Caso o diretório ``labredes`` ainda não esteja criado 
```
5. No terminal, digite o comando: 
```
sudo usermod -aG redes aluno # Para adicionar ``aluno`` a ``redes``
```
6. Modifique as permissões de acesso a partir dos comandos sequenciais: 
```
sudo mkdir /labredes/images/original # Caso o diretório não exista
sudo mkdir /labredes/VM/923/<Nome> # Caso o diretório não exista
```
7. Verifique a existência das imagens a partir do comando:
```
ls -la /labredes/images/original # Os arquivos .iso precisam estar nesse diretório
```
8. No terminal, digite o comando: 
```
sudo apt install virtualbox-ext-pack # Caso o Virtual Extension Pack não esteja instalado
```

### Rede P2P com duas VMs 
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

### Modificando hostname das VMs
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

### Nomes estáticos
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
      addresses: [192.168.23.[64-78]/28] 
      # Por exemplo: 
      # addresses: [192.168.23.66/28]
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

### Rede LAN P2P
Os passos a seguir devem ser realizados em todas as VMs de todos os PCs
1. Acesse as _configurações_ da VM --> _Rede_ --> modifique para *PLACA EM MODO BRIDGE* 
2. Modifique o *NOME* para *eno1*
3. Teste o ping entre as VMs de todos os PCs: 
```
ping 192.168.23.[64-78]
``` 
Por exemplo, caso o endereço IP da VM1 do PC1 seja 192.168.23.78 e o endereço IP da VM2 do PC2 seja 192.168.23.67, o comando a ser digitado:
- Na VM1 do PC1:
```
ping 192.168.23.67
```
- Na VM2 do PC2: 
```
ping 192.168.23.78
```



