# Desafio do Dia 15
## Etapa 1
```bash
[qui set 03 15:49:26] sysadmin@debian [~]$ sudo useradd aval1
[qui set 03 15:56:21] sysadmin@debian [/srv/aval]$ sudo passwd aval1
Nova senha: 
Redigite a nova senha: 
passwd: senha atualizada com sucesso
```
## Etapa 2
```bash
[qui set 03 15:50:28] sysadmin@debian [~]$ sudo groupadd avaliadores
[qui set 03 15:50:37] sysadmin@debian [~]$ sudo usermod -aG avaliadores aval1
```
## Etapa 3
```bash
[qui set 03 15:52:12] sysadmin@debian [/srv]$ sudo mkdir aval
[qui set 03 15:53:13] sysadmin@debian [/srv]$ sudo chown sysadmin:avaliadores aval
[qui set 03 15:54:25] sysadmin@debian [/srv]$ sudo chmod 2770 aval
```
## Etapa 4
```bash
[qui set 03 15:52:51] sysadmin@debian [/srv]$ sudo touch aval/teste-{01..10}.log
[qui set 03 15:56:03] sysadmin@debian [/srv/aval]$ ln -s teste-10.log ultimo
[qui set 03 15:58:36] sysadmin@debian [/srv/aval]$ ls
teste-01.log  teste-03.log  teste-05.log  teste-07.log  teste-09.log  ultimo
teste-02.log  teste-04.log  teste-06.log  teste-08.log  teste-10.log
```
## Etapa 5
```bash
[qui set 03 16:03:18] sysadmin@debian [/srv/aval]$ getent passwd | grep /bin/bash | sort | head -5
aluno1:x:1008:1008::/home/aluno1:/bin/bash
aluno2:x:1009:1009::/home/aluno2:/bin/bash
estagiario:x:1004:1007::/home/estagiario:/bin/bash
operador:x:1003:1006::/home/operador:/bin/bash
root:x:0:0:root:/root:/bin/bash
```
## Etapa 7
```bash
[qui set 03 16:04:01] sysadmin@debian [/srv/aval]$ nano ~/.bashrc
[qui set 03 16:07:57] sysadmin@debian [/srv/aval]$ head -6 ~/.bashrc
# ALIASES
alias ll='ls -la'
alias update='sudo apt update && sudo apt full-upgrade'
alias excluir='rm -R -I -v'
# EXPORT'S
export AVAL_DIR=/srv/aval
```
