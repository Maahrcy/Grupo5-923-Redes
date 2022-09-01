<div align='center'>
<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/ifal.png' width='100' height='130'>

**Instituto Federal de Alagoas - Campus Arapiraca**

**Integrantes:** [Julia Vitória Farias da Silva](https://github.com/juliavitoriav), [Macielly da Trindade Almeida](https://github.com/Maahrcy) e [Maria Catielly dos Santos Silva](https://github.com/Mcatielly)

**Professor:** [Alaelson](https://github.com/alaelson/)

**Disciplina:** Infraestrutura de Redes

**Turma:** 923

**Grupo:** 5
</div>

# Grupo5-923-Redes
Repositório para o projeto do 2º bimestre de Infraestrutura de Redes.

## Objetivos
- Testar os conhecimentos adquiridos em sala de aula;
- Criar tutorial de como conectar diversas VMs simultaneamente;
- Conectar as VMs dos PCs por meio do switch;
- Acessar uma VM remotamente por meio do SSH.

## Tabelas 

| DESCRIÇÃO  |  IP  |  hostname  |  FQDN  |  aliase  |
| ------------------- | ------------------- | ------------------- | ------------------- | ------------------- |
|  VM1-PC1-JULIA |  192.168.23.78/28 |  srv-vm1-pc1-julia |  julia01-pc1.grupo5-923.ifalara.net |  VPN |
|  VM2-PC1-JULIA |  192.168.23.65/28 |  srv-vm2-pc1-julia |  julia02-pc1.grupo5-923.ifalara.net |  mail |
|  VM1-PC2-MACIELLY |  192.168.23.66/28 |  srv-vm1-pc2-macielly |  macielly01-pc2.grupo5-923.ifalara.net |  www |
|  VM2-PC2-MACIELLY |  192.168.23.67/28 |  srv-vm2-pc2-macielly |  macielly02-pc2.grupo5-923.ifalara.net |  file |
|  VM1-PC3-CATIELLY |  192.168.23.68/28 |  srv-vm1-pc3-catielly |  catielly01-pc3.grupo5-923.ifalara.net |  mysql |
|  VM2-PC3-CATIELLY |  192.168.23.69/28 |  srv-vm2-pc3-catielly |  catielly02-pc3.grupo5-923.ifalara.net |  ssd |

[Acessar o documento com as tabelas](https://docs.google.com/spreadsheets/d/1wC8-0qN_uJ9s-l_1ESp-2WHDWGVcQKEaONAI2HTbjAo/edit?usp=sharing)

## Tipologia lógica da rede
<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/switch-connection.jpg'>

## Tipologia física da rede
<div>
<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/tf-1.jpg' width='300' height='250'>
<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/tf-2.jpg' width='300' height='250'>
<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/tf-3.jpg' width='300' height='250'>
<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/tf-4.jpg' width='300' height='250'>
<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/tf-5.jpg' width='300' height='250'>
<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/tf-6.jpg' width='300' height='250'>
</div>

## Tutorial

- [Criando uma máquina virtual](creating.md)
- [Rede com duas VMs](p2p-2vm.md)
- [Modificando hostname das VMs](hostname.md)
- [Nomes estáticos](static.md)
- [Host-Only](host-only.md)
- [Rede LAN](lan-p2p.md)
- [Adicionando usuários](adduser.md)


## Pings entre as VMs

- [Conexão entre as VMs dos PCs](conection.md)
- [Conexão entre todas as VMs de todos os PCs com switch](switch-connected.md)
- [SSH nas VMs dos PCs](ssh-connection.md)
- [Configurações das VMs dos PCs](cfg-vm.md)

