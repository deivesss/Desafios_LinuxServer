# Desafio do Dia 07
## Nível 1
### Utilizando *tail -f* para ler as Logs do Sistema em Tempo Real (utilizando logger em outro terminal)
```bash
sysadmin@debian:/var/log$ sudo tail -f /var/log/syslog
2026-08-26T13:54:14.059871-03:00 debian kernel: Loaded X.509 cert 'wens: 61c038651aabdcf94bd0ac7ff06c7248db18c600'
2026-08-26T13:54:14.059874-03:00 debian kernel: 8021q: adding VLAN 0 to HW filter on device enp0s3
2026-08-26T13:54:14.059874-03:00 debian kernel: e1000: enp0s3 NIC Link is Up 1000 Mbps Full Duplex, Flow Control: RX
2026-08-26T13:59:41.203786-03:00 debian kernel: device-mapper: core: CONFIG_IMA_DISABLE_HTABLE is disabled. Duplicate IMA measurements will not be recorded in the IMA log.
2026-08-26T13:59:41.203814-03:00 debian kernel: device-mapper: uevent: version 1.0.3
2026-08-26T13:59:41.209792-03:00 debian kernel: device-mapper: ioctl: 4.48.0-ioctl (2023-03-01) initialised: dm-devel@lists.linux.dev
2026-08-26T13:59:59.649459-03:00 debian systemd[1]: Reload requested from client PID 4532 ('systemctl') (unit session-3.scope)...
2026-08-26T13:59:59.654833-03:00 debian systemd[1]: Reloading...
2026-08-26T13:59:59.863573-03:00 debian (sd-exec-[4544]: /usr/lib/systemd/system-generators/systemd-ssh-generator failed with exit status 1.
2026-08-26T14:00:00.055643-03:00 debian systemd[1]: Reloading finished in 404 ms.
2026-08-26T14:00:18.741544-03:00 debian sysadmin: batata
```
## Nível 2
### Quantas Linhas tem o Arquivo *etc/passwd*
```bash
sysadmin@debian:/etc$ wc -l passwd
24 passwd
```
### Os 3 primeiros Usuários
```bash
sysadmin@debian:/etc$ head -n 3 passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
```
### Os 3 últimos Usuários
```bash
sysadmin@debian:/etc$ tail -n 3 passwd
messagebus:x:990:990:System Message Bus:/nonexistent:/usr/sbin/nologin
sshd:x:989:65534:sshd user:/run/sshd:/usr/sbin/nologin
sysadmin:x:1000:1000:sysadmin,,,:/home/sysadmin:/bin/bash
```
### Procura do Usuário *root*
```bash
sysadmin@debian:/etc$ head -n 1 passwd
root:x:0:0:root:/root:/bin/bash
```
### Tipo de Arquivo *passwd*
```bash
sysadmin@debian:/etc$ file passwd
passwd: ASCII text
```
### Relatório de *passwd*
```bash
sysadmin@debian:~/Arquivos do David$ nano relatorio_passwd.txt
sysadmin@debian:~/Arquivos do David$ cat relatorio_passwd.txt 
Relatório de /etc/passwd
Número de Linhas                       -> 24 linhas/usuários
Três Primeiros Usuários                -> root, daemon, bin
Três Últimos Usuários                  -> messagebus, sshd, sysadmin
Onde está o usuário Root               -> na linha 1
Confirmar que é um Arquivo de Texto    -> passwd: ASCII text
```
## Nível 3
### Criar *simulacao.log*
```bash
sysadmin@debian:~/Arquivos do David$ touch simulacao.log
```
### Usar *tail -f* em *simulacao.log*
```bash
sysadmin@debian:~/Arquivos do David$ tail -f simulacao.log
```
### Em outro Terminal, escrever *echo "ERRO: falha no modulo X" >> simulacao.log* várias vezes
```bash 
sysadmin@debian:~/Arquivos do David$ echo "ERRO: falha no modulo X" >> simulacao.log
sysadmin@debian:~/Arquivos do David$ echo "ERRO: falha no modulo X" >> simulacao.log
sysadmin@debian:~/Arquivos do David$ echo "ERRO: falha no modulo X" >> simulacao.log
sysadmin@debian:~/Arquivos do David$ echo "ERRO: falha no modulo X" >> simulacao.log
sysadmin@debian:~/Arquivos do David$ echo "ERRO: falha no modulo X" >> simulacao.log
sysadmin@debian:~/Arquivos do David$ echo "ERRO: falha no modulo X" >> simulacao.log
sysadmin@debian:~/Arquivos do David$ echo "ERRO: falha no modulo X" >> simulacao.log
sysadmin@debian:~/Arquivos do David$ echo "ERRO: falha no modulo X" >> simulacao.log
sysadmin@debian:~/Arquivos do David$ echo "ERRO: falha no modulo X" >> simulacao.log
```
### Resultado do *tail -f*
```bash
sysadmin@debian:~/Arquivos do David$ tail -f simulacao.log
ERRO: falha no modulo X
ERRO: falha no modulo X
ERRO: falha no modulo X
ERRO: falha no modulo X
ERRO: falha no modulo X
ERRO: falha no modulo X
ERRO: falha no modulo X
ERRO: falha no modulo X
ERRO: falha no modulo X
```
### Número de Linhas em *simulacao.log*
```bash
sysadmin@debian:~/Arquivos do David$ wc -l simulacao.log 
9 simulacao.log
```
