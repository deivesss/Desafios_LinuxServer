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
