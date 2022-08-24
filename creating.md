## Criando uma máquina virtual

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
