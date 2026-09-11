# Tarefa: Alta de uma Nova Colaboradora
## Etapa 1
### 1. Confirme em qual máquina você está (nome da máquina) e com qual usuário a sessão iniciou.
```bash
[qui set 10 13:42:00] sysadmin@debian [~]$ hostname
debian
[qui set 10 13:42:14] sysadmin@debian [~]$ whoami
sysadmin
```
### 2. Mostre em qual diretório você se encontra e liste todo o conteúdo da raiz */*, incluindo arquivos ocultos, em formato longo e com tamanhos legíveis.
```bash
[qui set 10 13:42:17] sysadmin@debian [~]$ pwd
/home/sysadmin
[qui set 10 13:42:20] sysadmin@debian [~]$ ls -lah /
total 64K
drwxr-xr-x  18 root root 4,0K set  2 15:49 .
drwxr-xr-x  18 root root 4,0K set  2 15:49 ..
lrwxrwxrwx   1 root root    7 ago 19 14:21 bin -> usr/bin
drwxr-xr-x   3 root root 4,0K set  2 16:23 boot
drwxr-xr-x  18 root root 3,2K set 10 13:39 dev
drwxr-xr-x  71 root root 4,0K set  8 14:04 etc
drwxr-xr-x  12 root root 4,0K set  4 15:24 home
lrwxrwxrwx   1 root root   36 set  2 15:49 initrd.img -> boot/initrd.img-6.12.107+deb13-amd64
lrwxrwxrwx   1 root root   36 set  2 15:49 initrd.img.old -> boot/initrd.img-6.12.105+deb13-amd64
lrwxrwxrwx   1 root root    7 ago 19 14:21 lib -> usr/lib
lrwxrwxrwx   1 root root    9 ago 19 14:21 lib64 -> usr/lib64
drwx------   2 root root  16K ago 19 14:21 lost+found
drwxr-xr-x   3 root root 4,0K ago 19 14:21 media
drwxr-xr-x   2 root root 4,0K ago 19 14:21 mnt
drwxr-xr-x   2 root root 4,0K ago 19 14:21 opt
dr-xr-xr-x 103 root root    0 set 10 13:39 proc
drwx------   4 root root 4,0K ago 20 13:48 root
drwxr-xr-x  20 root root  540 set 10 13:42 run
lrwxrwxrwx   1 root root    8 ago 19 14:21 sbin -> usr/sbin
drwxr-xr-x   7 root root 4,0K set  3 15:52 srv
dr-xr-xr-x  13 root root    0 set 10 13:39 sys
drwxrwxrwt   8 root root  160 set 10 13:39 tmp
drwxr-xr-x  12 root root 4,0K ago 19 14:21 usr
drwxr-xr-x  11 root root 4,0K ago 19 14:55 var
lrwxrwxrwx   1 root root   33 set  2 15:49 vmlinuz -> boot/vmlinuz-6.12.107+deb13-amd64
lrwxrwxrwx   1 root root   33 set  2 15:49 vmlinuz.old -> boot/vmlinuz-6.12.105+deb13-amd64
```
### 3. Mova-se até */var/log*, depois volte à sua home usando a forma abreviada que alterna entre dois diretórios. Suba um nível e desça de volta.
```bash
[qui set 10 13:42:39] sysadmin@debian [~]$ cd /var/log
[qui set 10 13:42:52] sysadmin@debian [/var/log]$ cd ~
[qui set 10 13:43:36] sysadmin@debian [~]$ cd ..
[qui set 10 13:43:57] sysadmin@debian [/home]$ cd sysadmin/
[qui set 10 13:44:00] sysadmin@debian [~]$
```
### 4. Confirme, na raiz, que existem os diretórios do *FHS*: /etc, /var/log, /home e /srv, e observe as permissões deles.
```bash
[qui set 10 13:54:29] sysadmin@debian [~]$ ls -l / & ls -l /var
[1] 863
total 36
drwxr-xr-x  2 root root 4096 set  3 13:05 backups
total 56
lrwxrwxrwx  1 root root     7 ago 19 14:21 bin -> usr/bin
drwxr-xr-x 10 root root 4096 ago 19 14:48 cache
drwxr-xr-x  3 root root  4096 set  2 16:23 boot
drwxr-xr-x 18 root root  3240 set 10 13:39 dev
drwxr-xr-x 23 root root 4096 ago 20 14:06 lib
drwxr-xr-x  2 root root 4096 jul  4 06:05 local
lrwxrwxrwx  1 root root    9 ago 19 14:21 lock -> /run/lock
drwxr-xr-x  7 root root 4096 set 10 13:42 log
drwxrwsr-x  2 root mail 4096 ago 19 14:21 mail
drwxr-xr-x  2 root root 4096 ago 19 14:21 opt
lrwxrwxrwx  1 root root    4 ago 19 14:21 run -> /run
drwxr-xr-x  4 root root 4096 ago 26 13:54 spool
drwxrwxrwt  4 root root 4096 set 10 13:39 tmp
drwxr-xr-x 71 root root  4096 set  8 14:04 etc
drwxr-xr-x 12 root root  4096 set  4 15:24 home
lrwxrwxrwx  1 root root    36 set  2 15:49 initrd.img -> boot/initrd.img-6.12.107+deb13-amd64
lrwxrwxrwx  1 root root    36 set  2 15:49 initrd.img.old -> boot/initrd.img-6.12.105+deb13-amd64
lrwxrwxrwx  1 root root     7 ago 19 14:21 lib -> usr/lib
lrwxrwxrwx  1 root root     9 ago 19 14:21 lib64 -> usr/lib64
drwx------  2 root root 16384 ago 19 14:21 lost+found
drwxr-xr-x  3 root root  4096 ago 19 14:21 media
drwxr-xr-x  2 root root  4096 ago 19 14:21 mnt
drwxr-xr-x  2 root root  4096 ago 19 14:21 opt
dr-xr-xr-x 97 root root     0 set 10 13:39 proc
drwx------  4 root root  4096 ago 20 13:48 root
drwxr-xr-x 20 root root   540 set 10 13:42 run
lrwxrwxrwx  1 root root     8 ago 19 14:21 sbin -> usr/sbin
drwxr-xr-x  7 root root  4096 set  3 15:52 srv
dr-xr-xr-x 13 root root     0 set 10 13:42 sys
drwxrwxrwt  8 root root   160 set 10 13:39 tmp
drwxr-xr-x 12 root root  4096 ago 19 14:21 usr
drwxr-xr-x 11 root root  4096 ago 19 14:55 var
lrwxrwxrwx  1 root root    33 set  2 15:49 vmlinuz -> boot/vmlinuz-6.12.107+deb13-amd64
lrwxrwxrwx  1 root root    33 set  2 15:49 vmlinuz.old -> boot/vmlinuz-6.12.105+deb13-amd64
```
## Etapa 2
### 1. Localize todos os arquivos que terminam em *.conf* dentro de */etc/ssh/*.
```bash
[qui set 10 14:20:50] sysadmin@debian [/etc/ssh]$ find -name "*.conf"
./ssh_config.d/20-systemd-ssh-proxy.conf
```
### 2. Localize todos os arquivos *.log* dentro de */var/log* e diga quantos há.
```bash
[qui set 10 14:28:31] sysadmin@debian [/var/log]$ sudo find -name "*.log"
./apt/term.log
./apt/history.log
./cron.log
./alternatives.log
./kern.log
./auth.log
./installer/Xorg.0.log
./user.log
./dpkg.log
[qui set 10 14:28:57] sysadmin@debian [/var/log]$ sudo find -name "*.log" | wc -l
9
```
### 3. Busque arquivos com mais de *1 MB* dentro de */var*.
```bash
[qui set 10 14:33:35] sysadmin@debian [/var]$ sudo find -size +1M
./lib/ispell/brasileiro.hash
./lib/aspell/pt_BR.rws
./lib/dpkg/info/keyboard-configuration.config
./lib/apt/lists/security.debian.org_debian-security_dists_trixie-security_main_i18n_Translation-en
./lib/apt/lists/deb.debian.org_debian_dists_trixie_main_i18n_Translation-en
./lib/apt/lists/deb.debian.org_debian_dists_trixie_main_i18n_Translation-pt%5fBR
./lib/apt/lists/deb.debian.org_debian_dists_trixie_main_binary-amd64_Packages
./lib/apt/lists/security.debian.org_debian-security_dists_trixie-security_main_binary-amd64_Packages
./cache/debconf/templates.dat
./cache/debconf/templates.dat-old
./cache/apt/srcpkgcache.bin
./cache/apt/pkgcache.bin
./log/journal/604c79dd1d714900a698b49962cc263f/user-1008@00065a828f47681d-7a7d5b61c4a759f5.journal~
./log/journal/604c79dd1d714900a698b49962cc263f/user-1009.journal
./log/journal/604c79dd1d714900a698b49962cc263f/system.journal
./log/journal/604c79dd1d714900a698b49962cc263f/system@000659cd0886ad9b-6c8bcd6571f5fa46.journal~
./log/journal/604c79dd1d714900a698b49962cc263f/user-1000.journal
./log/journal/604c79dd1d714900a698b49962cc263f/user-1008.journal
./log/journal/604c79dd1d714900a698b49962cc263f/user-1000@0006597d0611dfdf-33f31e400a9b3b4f.journal~
./log/journal/604c79dd1d714900a698b49962cc263f/user-1006.journal
./log/journal/604c79dd1d714900a698b49962cc263f/user-1000@00065afba66c5643-d7e79218414e0465.journal~
./log/journal/604c79dd1d714900a698b49962cc263f/user-1007.journal
./log/journal/604c79dd1d714900a698b49962cc263f/system@0006597d05429685-1f591696a45458ac.journal~
./log/journal/604c79dd1d714900a698b49962cc263f/user-1000@000659f54f195dfd-975b2d7ad67fa1b4.journal~
./log/journal/604c79dd1d714900a698b49962cc263f/user-1005.journal
./log/installer/cdebconf/templates.dat
```
### 4. Ao varrer diretórios restritos, você verá ruído (mensagens de permissão negada). Explique, em uma linha, o que faz exatamente o recurso que se costuma adicionar para silenciá-lo.
```bash
[qui set 10 15:05:02] sysadmin@debian [/]$ rm etc/shadow
rm: não foi possível remover 'etc/shadow': Permissão negada
[qui set 10 15:06:08] sysadmin@debian [/]$ rm etc/shadow 2> /dev/null
```
ao encaminhar o retorno de um comando para */dev/null*, aquele retorno é basicamente apagado, pois tudo o que é encaminhado a estecaminho, é simplesmente apagado do sistema.
## Etapa 3
### 1. Crie um grupo chamado recepcao.
```bash
[qui set 10 15:16:58] sysadmin@debian [~]$ sudo groupadd recepcao
```
### 2. Crie a usuária carla com diretório home e shell bash.
```bash
[qui set 10 15:18:58] sysadmin@debian [~]$ sudo useradd carla -s /bin/bash
```
### 3. Adicione carla ao grupo recepcao sem remover os grupos atuais dela.
```bash
[qui set 10 15:21:36] sysadmin@debian [~]$ sudo usermod carla -aG recepcao
```
### 4. Defina uma senha temporária para carla.
```bash
[qui set 10 15:44:10] sysadmin@debian [~]$ sudo passwd carla
Nova senha: 
Redigite a nova senha: 
passwd: senha atualizada com sucesso
```
### 5. Confirme que a usuária e o grupo ficaram registrados nas bases de identidade.
```bash
[qui set 10 15:45:03] sysadmin@debian [~]$ sudo getent passwd carla && sudo getent group recepcao
carla:x:1013:1018::/home/carla:/bin/bash
recepcao:x:1017:carla
```
### 6. Explique por que, ao adicioná-la ao grupo, você usou a forma que acrescenta e não a que substitui tudo.
por que, caso eu substituísse, o grupo "carla" criado automaticamente na criação da usuária, seria removido dela e ela ficaria apenas no grupo de recepcao. já atribuindo, eu apenas acrescentei a usuária a mais um grupo.
## Etapa 4
### Criação da Árvore de Diretórios
```bash
[qui set 10 15:55:52] sysadmin@debian [/srv]$ sudo mkdir mar-de-vidro
[qui set 10 15:56:02] sysadmin@debian [/srv]$ cd mar-de-vidro/
[qui set 10 15:56:43] sysadmin@debian [/srv/mar-de-vidro]$ sudo mkdir pacientes recepcao logs
```
### Ajuste de Permissões
```bash
[qui set 10 15:58:10] sysadmin@debian [/srv]$ sudo chown -R carla:recepcao mar-de-vidro
[qui set 10 15:58:15] sysadmin@debian [/srv]$ cd mar-de-vidro/
[qui set 10 15:58:41] sysadmin@debian [/srv/mar-de-vidro]$ sudo chmod 2760 pacientes/
[qui set 10 16:35:02] sysadmin@debian [/srv/mar-de-vidro]$ sudo chmod 2770 recepcao/
[qui set 10 16:35:30] sysadmin@debian [/srv/mar-de-vidro]$ sudo chmod 1777 logs/
[qui set 10 16:36:09] sysadmin@debian [/srv/mar-de-vidro]$ ls -l
total 12
drwxrwxrwt 2 carla recepcao 4096 set 10 15:56 logs
drwxrwS--- 2 carla recepcao 4096 set 10 15:56 pacientes
drwxrws--- 2 carla recepcao 4096 set 10 15:56 recepcao
```
## Etapa 5
### 1. Torne-se (temporariamente) carla e crie, dentro de /srv/mar-de-vidro/pacientes, o arquivo paciente001.txt com duas linhas: Nome: Ana Pereira e Data: 2026-09-10.
```bash
[sex set 11 13:12:42] sysadmin@debian [~]$ su carla
Senha: 
carla@debian:/home/sysadmin$ cd /srv/mar-de-vidro/pacientes/
carla@debian:/srv/mar-de-vidro/pacientes$ echo -e "Nome: Ana Pereira\nData: 2026:09:10" > paciente001.txt
```
### 2. Volte à sua conta administrativa e confirme quem é o dono e o grupo desse arquivo.
```bash
carla@debian:/srv/mar-de-vidro/pacientes$ su sysadmin
Senha: 
[sex set 11 13:21:01] sysadmin@debian [/srv/mar-de-vidro/pacientes]$ sudo ls -l
total 4
-rw-rw-r-- 1 carla recepcao 35 set 11 13:20 paciente001.txt
```
### 3. Verifique que o grupo é recepcao (não carla) — isso mostra que o SGID funcionou.
```bash
carla recepcao
```
### 4. Mostre o conteúdo do arquivo para confirmar as duas linhas.
```bash
[sex set 11 13:21:08] sysadmin@debian [/srv/mar-de-vidro/pacientes]$ sudo cat paciente001.txt
Nome: Ana Pereira
Data: 2026:09:10
```
## Etapa 6
### 1. Crie uma cópia completa de /srv/mar-de-vidro em /srv/mar-de-vidro-bkp, preservando permissões, donos e datas (não apenas a estrutura).
```bash
[sex set 11 13:54:49] sysadmin@debian [/srv]$ sudo cp -rpv mar-de-vidro mar-de-vidro-backup
'mar-de-vidro' -> 'mar-de-vidro-backup'
'mar-de-vidro/pacientes' -> 'mar-de-vidro-backup/pacientes'
'mar-de-vidro/pacientes/paciente001.txt' -> 'mar-de-vidro-backup/pacientes/paciente001.txt'
'mar-de-vidro/recepcao' -> 'mar-de-vidro-backup/recepcao'
'mar-de-vidro/logs' -> 'mar-de-vidro-backup/logs'
[sex set 11 13:55:48] sysadmin@debian [/srv]$ sudo ls -lahR mar-de-vidro-backup/
mar-de-vidro-backup/:
total 20K
drwxr-xr-x 5 carla recepcao 4,0K set 10 15:56 .
drwxr-xr-x 9 root  root     4,0K set 11 13:54 ..
drwxrwxrwt 2 carla recepcao 4,0K set 10 15:56 logs
drwxrwS--- 2 carla recepcao 4,0K set 11 13:20 pacientes
drwxrws--- 2 carla recepcao 4,0K set 10 15:56 recepcao

mar-de-vidro-backup/logs:
total 8,0K
drwxrwxrwt 2 carla recepcao 4,0K set 10 15:56 .
drwxr-xr-x 5 carla recepcao 4,0K set 10 15:56 ..

mar-de-vidro-backup/pacientes:
total 12K
drwxrwS--- 2 carla recepcao 4,0K set 11 13:20 .
drwxr-xr-x 5 carla recepcao 4,0K set 10 15:56 ..
-rw-rw-r-- 1 carla recepcao   35 set 11 13:20 paciente001.txt

mar-de-vidro-backup/recepcao:
total 8,0K
drwxrws--- 2 carla recepcao 4,0K set 10 15:56 .
drwxr-xr-x 5 carla recepcao 4,0K set 10 15:56 ..
```
### 2. Crie um "atalho" chamado /srv/backup-atual que aponte para a cópia de segurança, e liste /srv para confirmar o enlace e para onde aponta.
```bash
[sex set 11 14:01:19] sysadmin@debian [/srv]$ sudo ln -s mar-de-vidro-backup backup-atual
[sex set 11 14:01:25] sysadmin@debian [/srv]$ ls
aval  backup-atual  compartilhado  hardening  lab  mar-de-vidro  mar-de-vidro-backup  projetos
[sex set 11 14:01:33] sysadmin@debian [/srv]$ ls  backup-atual
logs  pacientes  recepcao
```
### 3. Explique a diferença entre copiar recursivamente e copiar preservando atributos — por que você precisa das duas coisas juntas.
o recursivo apenas inclui os diretórios na cópia. a preservação de atributos apenas preserva o dono, o grupo e as permissões dos arquivos.
## Etapa 7
### 1. Crie, em um único comando, 10 arquivos de log numerados de 01 a 10 (log01.txt ... log10.txt) na sua home.
```bash
[sex set 11 14:12:45] sysadmin@debian [~/logs]$ touch log{01..10}.txt
[sex set 11 14:13:00] sysadmin@debian [~/logs]$ ls
log01.txt  log03.txt  log05.txt  log07.txt  log09.txt
log02.txt  log04.txt  log06.txt  log08.txt  log10.txt
```
### 2. Sem escrever um por um, mova apenas os arquivos 03, 06 e 09 para uma pasta nova chamada selecion.
```bash
[sex set 11 14:13:02] sysadmin@debian [~/logs]$ mkdir selection
[sex set 11 14:14:03] sysadmin@debian [~/logs]$ mv log{03,06,09}.txt selection/
```
### 3. Conte quantos arquivos .conf existem em todo o /etc.
```bash
[sex set 11 14:16:39] sysadmin@debian [~/logs]$ sudo find /etc/ -name "*.conf" | wc -l
55
```
### 4. Liste apenas os 10 primeiros arquivos .conf de /etc, em ordem alfabética.
```bash
[sex set 11 14:16:47] sysadmin@debian [~/logs]$ sudo find /etc/ -name "*.conf" | sort | head
/etc/adduser.conf
/etc/apparmor/parser.conf
/etc/apt/listchanges.conf
/etc/ca-certificates.conf
/etc/debconf.conf
/etc/deluser.conf
/etc/dhcpcd.conf
/etc/e2scrub.conf
/etc/gai.conf
/etc/host.conf
```
## Etapa 8
### 1. A partir de /etc/passwd, gere uma lista das usuárias cujo shell é /bin/bash e salve em /tmp/usuarios-ativos.txt (sobrescrevendo o arquivo, se existir).
```bash
[sex set 11 14:20:19] sysadmin@debian [~]$ sudo cat /tmp/usuarios-ativos.txt
root:x:0:0:root:/root:/bin/bash
sysadmin:x:1000:1000:sysadmin,,,:/home/sysadmin:/bin/bash
operador:x:1003:1006::/home/operador:/bin/bash
estagiario:x:1004:1007::/home/estagiario:/bin/bash
aluno1:x:1008:1008::/home/aluno1:/bin/bash
aluno2:x:1009:1009::/home/aluno2:/bin/bash
aluno3:x:1012:1016::/home/aluno3:/bin/bash
carla:x:1013:1018::/home/carla:/bin/bash
```
### 2. Confirme quantas linhas (usuárias) o arquivo tem.
```bash
[sex set 11 14:20:29] sysadmin@debian [~]$ sudo wc -l /tmp/usuarios-ativos.txt
8 /tmp/usuarios-ativos.txt
```
### 3. Acrescente a data atual ao final do arquivo, sem apagar o que já existia.
```bash
[sex set 11 14:20:29] sysadmin@debian [~]$ sudo wc -l /tmp/usuarios-ativos.txt
8 /tmp/usuarios-ativos.txt
```
### 4. Execute um comando que produza bastante ruído (por exemplo, uma busca ampla sobre /) e envie toda a saída (normal e de erro) para o "ralo" /dev/null. Explique cada parte.
```bash
[sex set 11 14:28:02] sysadmin@debian [~]$ sudo ls -lahR / > /dev/null 2> /dev/null 
[sex set 11 14:28:21] sysadmin@debian [~]$ 
```
o comando `ls -lahR /` exibe todos os diretorios e suas informacoes recursivamente da pasta raiz ´/´. a extensão ´ > /dev/null 2> /dev/null` redireciona todos os resultados e erros para o endereço mencionado.
### 5. Gere um informe que apareça na tela E seja salvo em /tmp/informe-alta.txt, a partir de /tmp/usuarios-ativos.txt.
```bash
[sex set 11 14:39:31] sysadmin@debian [~]$ cat /tmp/usuarios-ativos.txt | tee /tmp/informe-alta.txt
root:x:0:0:root:/root:/bin/bash
sysadmin:x:1000:1000:sysadmin,,,:/home/sysadmin:/bin/bash
operador:x:1003:1006::/home/operador:/bin/bash
estagiario:x:1004:1007::/home/estagiario:/bin/bash
aluno1:x:1008:1008::/home/aluno1:/bin/bash
aluno2:x:1009:1009::/home/aluno2:/bin/bash
aluno3:x:1012:1016::/home/aluno3:/bin/bash
carla:x:1013:1018::/home/carla:/bin/bash
11/09/2026
```
## Etapa 9
### 1. Confirme os valores das variáveis de ambiente que definem o diretório pessoal dela, em quais caminhos o sistema procura comandos e o nome de usuário. (Pense em como "exibir" o valor de uma variável.)
```bash
carla@debian:/home$ env | grep PATH && env | grep USER
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
SUDO_USER=sysadmin
USER=carla
```
### 2. Defina um atalho (alias) para que rm pergunte antes de apagar, e confira com uma listagem dos atalhos ativos.
```bash
carla@debian:~$ nano .bashrc 
carla@debian:~$ source .bashrc 
carla@debian:~$ head -2 .bashrc 
# ALIASES
alias rm="rm -i"
carla@debian:~$ touch test.txt
carla@debian:~$ rm test.txt
rm: remover regular empty file 'test.txt'? yes
carla@debian:~$ cat .bashrc | grep "alias "
alias rm="rm -i"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'
    #alias grep='grep --color=auto'
    #alias fgrep='fgrep --color=auto'
    #alias egrep='egrep --color=auto'
#alias ll='ls -l'
#alias la='ls -A'
#alias l='ls -CF'
```
### 4. Repita o último comando que executou e busque um anterior no histórico. Explique como cada recurso funciona.
```bash
carla@debian:~$ cat .bashrc | grep "alias "
alias rm="rm -i"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'
    #alias grep='grep --color=auto'
    #alias fgrep='fgrep --color=auto'
    #alias egrep='egrep --color=auto'
#alias ll='ls -l'
#alias la='ls -A'
#alias l='ls -CF'
carla@debian:~$ !!
cat .bashrc | grep "alias "
alias rm="rm -i"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'
    #alias grep='grep --color=auto'
    #alias fgrep='fgrep --color=auto'
    #alias egrep='egrep --color=auto'
#alias ll='ls -l'
#alias la='ls -A'
#alias l='ls -CF'
(failed reverse-i-search)`': ^Ct .bashrc | grep "alias "
```
o comando `!!` simplesmente repete o ultimo comando executado. já a combinação de teclas `Ctrl+R` realiza uma busca interativa pelo histórico.
### 5. Justifique por que esse alias é uma boa prática de SysAdmin.
para que ele não acabe excluindo arquivos sem querer, o comando pede uma confirmação antes de cada remoção.
## Etapa 10
### 1. Mostre a árvore completa de /srv/mar-de-vidro (pastas e arquivos dentro).
```bash
[sex set 11 15:28:23] sysadmin@debian [/home]$ sudo ls -R /srv/mar-de-vidro
/srv/mar-de-vidro:
logs  pacientes  recepcao

/srv/mar-de-vidro/logs:

/srv/mar-de-vidro/pacientes:
paciente001.txt

/srv/mar-de-vidro/recepcao:
```
### 2. Confirme donos e grupos dos arquivos de /srv/mar-de-vidro/pacientes/.
```bash
[sex set 11 15:28:29] sysadmin@debian [/home]$ sudo ls -lR /srv/mar-de-vidro/pacientes/
/srv/mar-de-vidro/pacientes/:
total 4
-rw-rw-r-- 1 carla recepcao 35 set 11 13:20 paciente001.txt
```
### 3. Confirme para onde realmente aponta o enlace /srv/backup-atual.
```bash
[sex set 11 15:29:08] sysadmin@debian [/home]$ ls -la /srv/ | grep backup
lrwxrwxrwx  1 root     root          19 set 11 14:01 backup-atual -> mar-de-vidro-backup
drwxr-xr-x  5 carla    recepcao    4096 set 10 15:56 mar-de-vidro-backup
```
### 4. Revise seu próprio histórico de comandos da sessão.
```bash
[sex set 11 15:32:21] sysadmin@debian [/home]$ history | tail
  935  ls -a carla
  936  sudo apt update && sudo apt full_upgrade
  937  sudo apt update && sudo apt full-upgrade
  938  PATH=$PATH:~/bin
  939  sudo ls -r /srv/mar-de-vidro
  940  sudo ls -R /srv/mar-de-vidro
  941  sudo ls -lR /srv/mar-de-vidro/pacientes/
  942  ls -la /srv/ | grep backup
  943  history
  944  history | tail
```
