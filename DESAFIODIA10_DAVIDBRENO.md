# Desafio do Dia 10
## Nível 1
### Listar todos os Arquivos com *SUID* no Sistema e Classificá-los
```bash
sysadmin@debian:~$ find / -perm -4000 -type f 2>/dev/null > suid-encontrados.txt
sysadmin@debian:~$ cat suid-encontrados.txt 
/usr/lib/openssh/ssh-keysign                  -> Esperado
/usr/lib/dbus-1.0/dbus-daemon-launch-helper   -> Esperado
/usr/bin/gpasswd                              -> Esperado
/usr/bin/passwd                               -> Esperado
/usr/bin/chsh                                 -> Esperado
/usr/bin/su                                   -> Esperado
/usr/bin/chfn                                 -> Esperado
/usr/bin/umount                               -> Esperado
/usr/bin/mount                                -> Esperado
/usr/bin/newgrp                               -> Esperado
/usr/bin/sudo                                 -> Esperado
```
### Explicar o Risco de *SUID root* em Scripts não Oficiais
O uso de *SUID root* em scripts nao oficiais pode causar uma falha na segurança do sistema pois nada mais é do que a criação de novas brechas de segurança, o que facilita o êxito de um ataque na rede.
## Nível 2
```bash
sysadmin@debian:/home$ find / -perm -2000 -type f 2>/dev/null
/usr/bin/chage
/usr/bin/expiry
/usr/bin/dotlockfile
/usr/bin/ssh-agent
/usr/bin/crontab
/usr/sbin/unix_chkpwd
/home/alunos/a2.txt
/home/alunos/teste.txt
/home/alunos/a2.py
/home/alunos/a1.txt
/home/alunos/a2.js
```
### Listar Pastas com *Sticky Bit*
*/home/alunos/*
### Criar */srv/hardening* com *SGID (2770)* e Demonstrar Herança
SYSADMIN:
```bash
sysadmin@debian:/srv$ sudo mkdir hardening
sysadmin@debian:/srv$ sudo chmod 2770 hardening
sysadmin@debian:/srv$ sudo chown sysadmin:alunos hardening
```
ALUNO1:
```bash
$ touch arq_alu1
```
ALUNO2:
```bash
$ touch arq_alu2
```
RESULTADO ATÉ ENTÃO:
```bash
sysadmin@debian:/srv/hardening$ ls
arq_alu1  arq_alu2
sysadmin@debian:/srv/hardening$ ls -lah
total 8,0K
drwxrws--T 2 sysadmin alunos 4,0K set  1 15:56 .
drwxr-xr-x 5 root     root   4,0K set  1 15:41 ..
-rw-rw-r-- 1 aluno1   alunos    0 set  1 15:43 arq_alu1
-rw-rw-r-- 1 aluno2   alunos    0 set  1 15:56 arq_alu2
```
ALUNO2:
```bash
$ rm arq_alu1
rm: não foi possível remover 'arq_alu1': Operação não permitida
```
SYSADMIN:
```bash
sysadmin@debian:/srv$ chmod 3770 hardening
```
ALUNO1:
```bash
$ rm arq_alu2
$ ls
arq_alu1
```
