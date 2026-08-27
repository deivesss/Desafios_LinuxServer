# Desafio do Dia 09
## Nível 1
### Criar */srv/compartilhado* com *sudo*
```bash
sysadmin@debian:/srv$ sudo mkdir /srv/compartilhado
```
### Mudar o Grupo para *alunos*
```bash
sysadmin@debian:/srv$ sudo chown -R :alunos compartilhado/
```
### Setar Permissão da Pasta para *770*
```bash
sysadmin@debian:/srv$ sudo chmod 770 compartilhado/
[sudo] senha para sysadmin:
```
### Criar Arquivo como *root*, Modificar como *aluno1* e Ler como *aluno2*
SYSADMIN:
```bash
sysadmin@debian:/srv$ sudo touch compartilhado/teste.txt
```
ALUNO1:
```bash
$ pwd
/srv/compartilhado
$ ls
teste.txt
$ nano teste.txt
```
ALUNO2:
```bash
$ pwd
/srv/compartilhado
$ ls
teste.txt
$ cat teste.txt
batata
```
## Nível 2
### Criar */srv/projetos*, Grupo *alunos*, Permissão *2770*
```bash
sysadmin@debian:/srv$ sudo mkdir /srv/projetos
sysadmin@debian:/srv$ sudo chown -R :alunos projetos/
sysadmin@debian:/srv$ sudo chmod 2770 projetos/
```
### Criar um Arquivo como *aluno1* dentro
```bash
$ touch teste.txt
```
### Herdou o Grupo *alunos*?
```bash
$ ls -lah
total 8,0K
drwxrws--- 2 root   alunos 4,0K ago 27 16:21 .
drwxr-xr-x 4 root   root   4,0K ago 27 16:07 ..
-rw-r--rw- 1 aluno2 alunos    0 ago 27 16:21 teste.txt
```
### Criar a Pasta e o Grupo
```bash
sysadmin@debian:/srv$ sudo mkdir -p /srv/compartilhado
sysadmin@debian:/srv$ sudo groupadd projetistas
```
### Configurar Dono e Permissões
```bash
sysadmin@debian:/srv$ sudo chown root:projetistas /srv/compartilhado
sysadmin@debian:/srv$ sudo chmod 2770 /srv/compartilhado
```
### Criar um Usuário de Teste e adicionar ao Grupo
```bash
sysadmin@debian:/srv$ sudo useradd -m tester
sysadmin@debian:/srv$ sudo usermod -aG projetistas tester
```
### Teste: *trocar para o usuário e tentar criar um arquivo*
```bash
$ whoami
tester
$ touch test.txt
$ ls
teste.txt  test.txt

$ ls -l
total 4
-rw-rw-r-- 1 aluno1 aluno1      7 ago 27 15:38 teste.txt
-rw-rw-r-- 1 tester projetistas 0 ago 27 16:33 test.txt
```
