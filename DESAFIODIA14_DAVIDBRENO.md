# Desafio do Dia 14
## Etapa 1
```bash
[qui set 03 14:51:32] sysadmin@debian [/]$ sudo useradd aluno5
[qui set 03 14:51:47] sysadmin@debian [/]$ sudo groupadd alunos
[qui set 03 14:51:59] sysadmin@debian [/]$ sudo usermod -aG alunos aluno5
[qui set 03 14:52:23] sysadmin@debian [/]$ sudo passwd aluno5
Nova senha: 
Redigite a nova senha: 
passwd: senha atualizada com sucesso
```
## Etapa 2
```bash
[qui set 03 14:56:18] sysadmin@debian [/srv]$ sudo mkdir lab
[qui set 03 14:56:24] sysadmin@debian [/srv]$ sudo chown alunos lab
chown: invalid user: ‘alunos’
[qui set 03 14:56:42] sysadmin@debian [/srv]$ sudo chown sysadmin:alunos lab
[qui set 03 14:56:52] sysadmin@debian [/srv]$ sudo chmod 2770 lab
```
## Etapa 3
```
[qui set 03 15:01:09] sysadmin@debian [/srv]$ sudo touch lab/log{01..30}.txt && cd lab
[qui set 03 15:02:37] sysadmin@debian [/srv/lab]$ mkdir impares
[qui set 03 15:07:11] sysadmin@debian [/srv/lab]$ mv log*{1,3,5,7,9}.txt impares/
[qui set 03 15:07:33] sysadmin@debian [/srv/lab]$ ls
impares    log04.txt  log08.txt  log12.txt  log16.txt  log20.txt  log24.txt  log28.txt
log02.txt  log06.txt  log10.txt  log14.txt  log18.txt  log22.txt  log26.txt  log30.txt
[qui set 03 15:07:36] sysadmin@debian [/srv/lab]$ ls impares/
log01.txt  log05.txt  log09.txt  log13.txt  log17.txt  log21.txt  log25.txt  log29.txt
log03.txt  log07.txt  log11.txt  log15.txt  log19.txt  log23.txt  log27.txt
```
## Etapa 4
```bash
[qui set 03 15:08:02] sysadmin@debian [/srv/lab]$ ln -s log30.txt ultimo.txt
```
## Etapa 5
```bash
[qui set 03 15:17:29] sysadmin@debian [/srv/lab]$ find | sort | head -5
.
./impares
./impares/log01.txt
./impares/log03.txt
./impares/log05.txt
```
## Etapa 6
```bash
[qui set 03 15:17:51] sysadmin@debian [/srv/lab]$ ls -la > relatorio.txt
[qui set 03 15:19:03] sysadmin@debian [/srv/lab]$ cat relatorio.txt 
total 12
drwxrws--- 3 sysadmin alunos 4096 set  3 15:19 .
drwxr-xr-x 6 root     root   4096 set  3 15:00 ..
drwxrwsr-x 2 sysadmin alunos 4096 set  3 15:07 impares
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log02.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log04.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log06.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log08.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log10.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log12.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log14.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log16.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log18.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log20.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log22.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log24.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log26.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log28.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log30.txt
-rw-rw-r-- 1 sysadmin alunos    0 set  3 15:19 relatorio.txt
lrwxrwxrwx 1 sysadmin alunos    9 set  3 15:11 ultimo.txt -> log30.txt
```
##Etapa 7
```bash
[qui set 03 15:19:06] sysadmin@debian [/srv/lab]$ nano ~/.bashrc
[qui set 03 15:21:06] sysadmin@debian [/srv/lab]$ alias rm='rm -i'
[qui set 03 15:21:19] sysadmin@debian [/srv/lab]$ export LAB_DIR=/srv/lab
[qui set 03 15:21:29] sysadmin@debian [/srv/lab]$ touch abc.txt
[qui set 03 15:22:25] sysadmin@debian [/srv/lab]$ rm abc.txt 
rm: remover regular empty file 'abc.txt'? y
[qui set 03 15:22:34] sysadmin@debian [/srv/lab]$ echo $LAB_DIR
/srv/lab
[qui set 03 15:25:03] sysadmin@debian [/srv/lab]$ ll
total 16
drwxrws--- 3 sysadmin alunos 4096 set  3 15:22 .
drwxr-xr-x 6 root     root   4096 set  3 15:00 ..
drwxrwsr-x 2 sysadmin alunos 4096 set  3 15:07 impares
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log02.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log04.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log06.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log08.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log10.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log12.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log14.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log16.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log18.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log20.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log22.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log24.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log26.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log28.txt
-rw-r--r-- 1 root     alunos    0 set  3 15:01 log30.txt
-rw-rw-r-- 1 sysadmin alunos 1150 set  3 15:19 relatorio.txt
lrwxrwxrwx 1 sysadmin alunos    9 set  3 15:11 ultimo.txt -> log30.txt
[qui set 03 15:25:09] sysadmin@debian [/srv/lab]$ source ~/.bashrc
```
