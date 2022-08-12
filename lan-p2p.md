## Rede LAN P2P
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
