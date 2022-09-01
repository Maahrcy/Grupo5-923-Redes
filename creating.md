## Criando uma máquina virtual

1. Abrir o terminal no PC LINUX
2. No terminal, digite o comando:
```
su redes
# No caso, o usuário utilizado será ' redes '
```

Assim como na imagem abaixo:

<img src='https://github.com/Maahrcy/Grupo5-923-Redes/blob/main/img/user.png' width='500' height='300'>

3. Logue no usuário
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
sudo chown -R nobody:group /labredes
sudo chgrp -R redes
sudo chmod -R 777 /labredes
```
7. Verifique a existência das imagens a partir do comando:
```
sudo mkdir /labredes/images/original # Caso o diretório não exista
sudo mkdir /labredes/VM/923/<Nome> # Caso o diretório não exista
ls -la /labredes/images/original # Os arquivos .iso precisam estar nesse diretório
```
8. No terminal, digite o comando: 
```
sudo apt install virtualbox-ext-pack # Caso o Virtual Extension Pack não esteja instalado
```
