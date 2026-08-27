# Desafio do Dia 08
## Nível 1
### Criar Grupo *alunos*
```bash
sysadmin@debian:~$ sudo groupadd alunos
```
### Criar Usuário *backup*
```bash
sysadmin@debian:~$ sudo useradd -m -s /usr/sbin/nologin backup
```
### Adicionar Usuário *backup* ao Grupo *alunos*
```bash
sysadmin@debian:~$ sudo usermod -aG alunos backup
sysadmin@debian:~$ getent passwd backup
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
```
## Nível 2
### Criar Usuários *monitor* e *deploy*
```bash
sysadmin@debian:~$ sudo useradd -m -s /usr/sbin/nologin monitor
sysadmin@debian:~$ sudo useradd -m -s /usr/sbin/nologin deploy
```
### Criar Grupos *grupo-monitor* e *grupo-deploy*
```bash
sysadmin@debian:~$ sudo groupadd grupo-monitor
sysadmin@debian:~$ sudo groupadd grupo-deploy
```
### Atribuir cada Usuário ao seu Grupo e atribuir Grupo *sudo* ao Usuário *deploy*
```bash
sysadmin@debian:~$ sudo usermod -aG grupo-monitor monitor
sysadmin@debian:~$ sudo usermod -aG grupo-deploy deploy
sysadmin@debian:~$ sudo usermod -aG sudo deploy
```
### *getent*
```bash
sysadmin@debian:~$ getent passwd backup
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
sysadmin@debian:~$ getent passwd deploy
deploy:x:1002:1003::/home/deploy:/usr/sbin/nologin
sysadmin@debian:~$ getent passwd monitor
monitor:x:1001:1002::/home/monitor:/usr/sbin/nologin
```
## Nível 3
### Criar um Usuário com Shell Específico e mudar sua Senha
```bash
sysadmin@debian:~$ sudo useradd -m -s /bin/bash operador
[sudo] senha para sysadmin: 
sysadmin@debian:~$ sudo passwd operador
Nova senha: 
Redigite a nova senha: 
passwd: senha atualizada com sucesso
```
### Criar um Usuário para Serviços (sem shell, sem home)
```bash
sysadmin@debian:~$ sudo useradd -r -s /usr/sbin/nologin webapp
```
### Criar um Usuário Temporário e mudar sua Senha
```bash
sysadmin@debian:~$ sudo useradd -m -s /bin/bash estagiario
sysadmin@debian:~$ sudo passwd estagiario 
Nova senha: 
Redigite a nova senha: 
passwd: senha atualizada com sucesso
```
### *getent*
```bash
sysadmin@debian:~$ getent passwd operador webapp estagiario
operador:x:1003:1006::/home/operador:/bin/bash
webapp:x:988:988::/home/webapp:/usr/sbin/nologin
estagiario:x:1004:1007::/home/estagiario:/bin/bash
```
