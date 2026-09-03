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
