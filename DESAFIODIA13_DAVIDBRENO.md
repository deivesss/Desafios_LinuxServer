# Desafio do Dia 13
## Nível 1
```bash
sysadmin@debian:~$ alias excluir='rm -I -R -v'
sysadmin@debian:~$ alias ll='ls -la'
sysadmin@debian:~$ alias update='apt update && apt full-upgrade'
sysadmin@debian:~$ source ~/.bashrc
sysadmin@debian:~$ type ll
ll está apelidada para `ls -la'
sysadmin@debian:~$ type excluir
excluir está apelidada para `rm -I -R -v'
```
## Nível 2 
```bash
sysadmin@debian:~$ export PROJETO=/srv/projetos/meuapp
sysadmin@debian:~$ export PATH=$PATH:$PROJETO/scripts
sysadmin@debian:~$ export editconf='?'
sysadmin@debian:~$ export PS1='[\d \t] \u@\h:\w>\$ '
[qui set 03 13:44:06] sysadmin@debian:~>$
```
## Nível 3
```
[qui set 03 13:44:06] sysadmin@debian:~>$ export HISTSIZE=5000
[qui set 03 13:46:07] sysadmin@debian:~>$ export HISTFILESIZE=10000
[qui set 03 13:46:23] sysadmin@debian:~>$ export HISTCONTROL=ignoredups:erasedups
[qui set 03 13:46:40] sysadmin@debian:~>$ echo $HISTTIMEFORMAT

[qui set 03 13:46:57] sysadmin@debian:~>$ export HISTTIMEFORMAT='[\d]'
[qui set 03 13:47:53] sysadmin@debian:~>$ echo $PS1
[\d \t] \u@\h:\w>\$
```
