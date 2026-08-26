# Desafio do Dia 06
## Nível 1 & Nível 2
### Criar Sub-pastas em *linux-curso*
```bash
sysadmin@debian:~/linux-curso$ mkdir historia && mkdir fhs && mkdir navegacao && mkdir comandos
sysadmin@debian:~/linux-curso$ ls
comandos  fhs  historia  navegacao
```
### Criar Arquivos para cada Sub-pasta dentro de *linux-curso*
```bash
sysadmin@debian:~/linux-curso$ touch historia.txt && touch fhs.txt && touch navegacao.txt && touch comandos.txt
sysadmin@debian:~/linux-curso$ ls
comandos  comandos.txt  fhs  fhs.txt  historia  historia.txt  navegacao  navegacao.txt
```
### Copiar cada Arquivo para sua respectiva Sub-pasta
``` bash
sysadmin@debian:~/linux-curso$ cp comandos.txt comandos
sysadmin@debian:~/linux-curso$ cp fhs.txt fhs
sysadmin@debian:~/linux-curso$ cp historia.txt historia
sysadmin@debian:~/linux-curso$ cp navegacao.txt navegacao
sysadmin@debian:~/linux-curso$ ls -R
.:
comandos  comandos.txt  fhs  fhs.txt  historia  historia.txt  navegacao  navegacao.txt

./comandos:
comandos.txt

./fhs:
fhs.txt

./historia:
historia.txt

./navegacao:
navegacao.txt
```
## Nível 3
```bash
sysadmin@debian:~/linux-curso$ mkdir -p projeto-lab/src projeto-lab/docs projeto-lab/backup
sysadmin@debian:~/linux-curso$ ls
projeto-lab
sysadmin@debian:~/linux-curso$ touch projeto-lab/src/app.py projeto-lab/docs/especificacao.md
sysadmin@debian:~/linux-curso$ cp -r projeto-lab projeto-lab-backup
sysadmin@debian:~/linux-curso$ rm projeto-lab/docs/especificacao.md
sysadmin@debian:~/linux-curso$ cp projeto-lab-backup/docs/especificacao.md projeto-lab/docs/
sysadmin@debian:~/linux-curso$ ls -R projeto-lab
projeto-lab:
backup  docs  src

projeto-lab/backup:
especificacao.md

projeto-lab/docs:
especificacao.md

projeto-lab/src:
app.py
```
