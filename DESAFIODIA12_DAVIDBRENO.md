# Desafio do Dia 12
## Nível 1
### Rodar 3 Comandos (ex.: ls -la, date, df -h) e Salvar *stdout* e *stderr* de cada um em Arquivos Separados usando *>* e *2>*
```bash
sysadmin@debian:~$ ls -lss > ls-la.txt 2>&1
sysadmin@debian:~$ cat ls-la.txt 
total 8
4 -rw-rw-r-- 1 sysadmin sysadmin  62 set  2 13:18 batata.txt
0 -rw-rw-r-- 1 sysadmin sysadmin   0 set  2 13:50 ls-la.txt
4 -rw-rw-r-- 1 sysadmin sysadmin 112 set  2 13:22 potato.txt
sysadmin@debian:~$ LS -lss >> ls-la.txt 2>&1
sysadmin@debian:~$ cat ls-la.txt 
total 8
4 -rw-rw-r-- 1 sysadmin sysadmin  62 set  2 13:18 batata.txt
0 -rw-rw-r-- 1 sysadmin sysadmin   0 set  2 13:50 ls-la.txt
4 -rw-rw-r-- 1 sysadmin sysadmin 112 set  2 13:22 potato.txt
-bash: LS: comando não encontrado
```
``` bash
sysadmin@debian:~$ date > date.txt 2>&1
sysadmin@debian:~$ cat date.txt 
qua 02 set 2026 13:55:29 -03
sysadmin@debian:~$ date s >> date.txt 2>&1
sysadmin@debian:~$ cat date.txt 
qua 02 set 2026 13:55:29 -03
date: data inválida ‘s’
```
```bash
sysadmin@debian:~$ df -h > df.txt 2>&1
sysadmin@debian:~$ cat df.txt 
Sist. Arq.      Tam. Usado Disp. Uso% Montado em
udev            960M     0  960M   0% /dev
tmpfs           198M  580K  197M   1% /run
/dev/sda1        19G  1,5G   17G   9% /
tmpfs           987M     0  987M   0% /dev/shm
tmpfs           1,0M     0  1,0M   0% /run/credentials/systemd-journald.service
tmpfs           5,0M     0  5,0M   0% /run/lock
tmpfs           987M     0  987M   0% /tmp
tmpfs           1,0M     0  1,0M   0% /run/credentials/getty@tty1.service
tmpfs           198M  4,0K  198M   1% /run/user/1000
tmpfs           198M  4,0K  198M   1% /run/user/1008
tmpfs           198M  4,0K  198M   1% /run/user/1009
sysadmin@debian:~$ df -f >> df.txt 2>&1
sysadmin@debian:~$ cat df.txt 
Sist. Arq.      Tam. Usado Disp. Uso% Montado em
udev            960M     0  960M   0% /dev
tmpfs           198M  580K  197M   1% /run
/dev/sda1        19G  1,5G   17G   9% /
tmpfs           987M     0  987M   0% /dev/shm
tmpfs           1,0M     0  1,0M   0% /run/credentials/systemd-journald.service
tmpfs           5,0M     0  5,0M   0% /run/lock
tmpfs           987M     0  987M   0% /tmp
tmpfs           1,0M     0  1,0M   0% /run/credentials/getty@tty1.service
tmpfs           198M  4,0K  198M   1% /run/user/1000
tmpfs           198M  4,0K  198M   1% /run/user/1008
tmpfs           198M  4,0K  198M   1% /run/user/1009
df: opção inválida -- “f”
Tente "df --help" para mais informações.
```
## Nível 2
### Listar Usuários com Shell */bin/bash* do */etc/passwd*
```bash
sysadmin@debian:~$ getent passwd | grep /bin/bash
root:x:0:0:root:/root:/bin/bash
sysadmin:x:1000:1000:sysadmin,,,:/home/sysadmin:/bin/bash
operador:x:1003:1006::/home/operador:/bin/bash
estagiario:x:1004:1007::/home/estagiario:/bin/bash
aluno1:x:1008:1008::/home/aluno1:/bin/bash
aluno2:x:1009:1009::/home/aluno2:/bin/bash
```
### Extrair Nome e Diretório *home*
```bash
sysadmin@debian:~$ getent passwd | grep /bin/bash | cut -d: -f1,6
root:/root
sysadmin:/home/sysadmin
operador:/home/operador
estagiario:/home/estagiario
aluno1:/home/aluno1
aluno2:/home/aluno2
```
### Ordenar, Contar e Salvar com *tee* em *bash-users.txt*
```bash
sysadmin@debian:~$ getent passwd | grep /bin/bash | cut -d: -f1,6 | sort | nl | tee bash-users.txt
     1	aluno1:/home/aluno1
     2	aluno2:/home/aluno2
     3	estagiario:/home/estagiario
     4	operador:/home/operador
     5	root:/root
     6	sysadmin:/home/sysadmin
```
### Explicar cada Etapa
O comando *getent passwd* obtém a lista de usuários. O pipe repassa essa lista para o *grep*, que filtra a lista para as linhas que contém */bin/bash*. O pipe passa essa lista filtrada para o comando *cut*, que pega apenas os conteúdos 1 e 6, que correspondem ao nome do usuário e seu diretório home. O pipe repassa a lista para *sort*, que ordena a lista. O pipe repassa a lista para *nl*, que acrescenta o número de cada linha. Após especificar exaamente o que queremos daquela lista, o pipe repassa a lista para *tee*, que retorna a lista e a escreve no arquivo *bash-users.txt*.
## Nível 3
### Criando 5 Arquivos *.conf*
```bash
sysadmin@debian:~$ cat <<EOF > app.conf
> batata = 9
> seloko = 3
> host = "null"
> port = 3000
> EOF
sysadmin@debian:~$ cat <<EOF > db.conf
> host = 192.0.98.6.4
> host2 = 168.543.432.4.5
> port = 3001
> EOF
sysadmin@debian:~$ cat <<EOF > backup.conf
> g
> d
> s
> g
> yjhd
> egh
> host
> port backup
> EOF
sysadmin@debian:~$ cat <<EOF > log.conf
> fd
> g]tfbx
> xdbxrtb
> xtnxtfg
> host log
> EOF
sysadmin@debian:~$ cat <<EOF > monitor.conf
> bdf
> dtb
> host monitor
> port monitor
> EOF
```
### Listando as Linhas que contém *host* e *port* e as escrevendo em *configuracoes-rede.txt*
```bash
sysadmin@debian:~$ cat app.conf db.conf backup.conf log.conf monitor.conf | grep host | tee -a configuracoes-rede.txt 2< erro.txt && cat app.conf db.conf backup.conf log.conf monitor.conf | grep port | tee -a configuracoes-rede.txt 2< erro.txt
host = "null"
host = 192.0.98.6.4
host2 = 168.543.432.4.5
host
host log
host monitor
port = 3000
port = 3001
port backup
port monitor
sysadmin@debian:~$ cat configuracoes-rede.txt 
host = "null"
host = 192.0.98.6.4
host2 = 168.543.432.4.5
host
host log
host monitor
port = 3000
port = 3001
port backup
port monitor
```
