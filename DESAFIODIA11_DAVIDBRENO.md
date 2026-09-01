# Desafio do Dia 11
## Nível 1
### Criar 20 Arquivos com *touch arquivo{01..20}.txt* e Remover apenas os Pares usando *wildcards*
```bash
sysadmin@debian:~/desafio11$ touch arquivo{01..20}.txt
sysadmin@debian:~/desafio11$ ls
arquivo01.txt  arquivo05.txt  arquivo09.txt  arquivo13.txt  arquivo17.txt
arquivo02.txt  arquivo06.txt  arquivo10.txt  arquivo14.txt  arquivo18.txt
arquivo03.txt  arquivo07.txt  arquivo11.txt  arquivo15.txt  arquivo19.txt
arquivo04.txt  arquivo08.txt  arquivo12.txt  arquivo16.txt  arquivo20.txt
sysadmin@debian:~/desafio11$ rm arquivo*{2,4,6,8,0}.txt
sysadmin@debian:~/desafio11$ ls
arquivo01.txt  arquivo05.txt  arquivo09.txt  arquivo13.txt  arquivo17.txt
arquivo03.txt  arquivo07.txt  arquivo11.txt  arquivo15.txt  arquivo19.txt
```
## Nível 2
```bash
sysadmin@debian:~/desafio11,2$ touch dado-{001..030}.csv
sysadmin@debian:~/desafio11,2$ ls
dado-001.csv  dado-006.csv  dado-011.csv  dado-016.csv  dado-021.csv  dado-026.csv
dado-002.csv  dado-007.csv  dado-012.csv  dado-017.csv  dado-022.csv  dado-027.csv
dado-003.csv  dado-008.csv  dado-013.csv  dado-018.csv  dado-023.csv  dado-028.csv
dado-004.csv  dado-009.csv  dado-014.csv  dado-019.csv  dado-024.csv  dado-029.csv
dado-005.csv  dado-010.csv  dado-015.csv  dado-020.csv  dado-025.csv  dado-030.csv
sysadmin@debian:~/desafio11,2$ ln dado-030.csv ultimo.csv
sysadmin@debian:~/desafio11,2$ ln -s dado-030.csv atual.csv
sysadmin@debian:~/desafio11,2$ ls -li
total 0
783501 lrwxrwxrwx 1 sysadmin sysadmin 12 set  1 16:21 atual.csv -> dado-030.csv
783463 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-001.csv
783465 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-002.csv
783467 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-003.csv
783469 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-004.csv
783471 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-005.csv
783473 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-006.csv
783475 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-007.csv
783477 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-008.csv
783479 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-009.csv
783480 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-010.csv
783481 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-011.csv
783482 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-012.csv
783483 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-013.csv
783484 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-014.csv
783485 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-015.csv
783486 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-016.csv
783487 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-017.csv
783488 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-018.csv
783489 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-019.csv
783490 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-020.csv
783491 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-021.csv
783492 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-022.csv
783493 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-023.csv
783494 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-024.csv
783495 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-025.csv
783496 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-026.csv
783497 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-027.csv
783498 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-028.csv
783499 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-029.csv
783500 -rw-rw-r-- 2 sysadmin sysadmin  0 set  1 16:19 dado-030.csv
783500 -rw-rw-r-- 2 sysadmin sysadmin  0 set  1 16:19 ultimo.csv
sysadmin@debian:~/desafio11,2$ rm dado-030.csv 
sysadmin@debian:~/desafio11,2$ ls -li
total 0
783501 lrwxrwxrwx 1 sysadmin sysadmin 12 set  1 16:21 atual.csv -> dado-030.csv
783463 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-001.csv
783465 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-002.csv
783467 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-003.csv
783469 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-004.csv
783471 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-005.csv
783473 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-006.csv
783475 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-007.csv
783477 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-008.csv
783479 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-009.csv
783480 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-010.csv
783481 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-011.csv
783482 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-012.csv
783483 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-013.csv
783484 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-014.csv
783485 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-015.csv
783486 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-016.csv
783487 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-017.csv
783488 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-018.csv
783489 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-019.csv
783490 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-020.csv
783491 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-021.csv
783492 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-022.csv
783493 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-023.csv
783494 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-024.csv
783495 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-025.csv
783496 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-026.csv
783497 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-027.csv
783498 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-028.csv
783499 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 dado-029.csv
783500 -rw-rw-r-- 1 sysadmin sysadmin  0 set  1 16:19 ultimo.csv
```
O Hard Link continua funcionando pois ele é como se fosse uma cópia do arquivo. Os dois tinham o mesmo conteúdo, o mesmo id e apenas nomes diferentes. Já o SymLink parou de funcionar pois ele era apenas um atalho para o arquivo que foi apagado. Assim, ficando sem destino existente.
## Nível 3
```bash
sysadmin@debian:~/desafio11,3$ touch registro-{0000..0099}.log
sysadmin@debian:~/desafio11,3$ rm registro-*{0,5}.log
sysadmin@debian:~/desafio11,3$ ls registro-*{1,3,5,7,9}.log
ls: não foi possível acessar 'registro-*5.log': Arquivo ou diretório inexistente
 registro-0001.log   registro-0027.log   registro-0051.log   registro-0077.log
 registro-0003.log   registro-0029.log   registro-0053.log   registro-0079.log
 registro-0007.log   registro-0031.log   registro-0057.log   registro-0081.log
 registro-0009.log   registro-0033.log   registro-0059.log   registro-0083.log
 registro-0011.log   registro-0037.log   registro-0061.log   registro-0087.log
 registro-0013.log   registro-0039.log   registro-0063.log   registro-0089.log
 registro-0017.log   registro-0041.log   registro-0067.log   registro-0091.log
 registro-0019.log   registro-0043.log   registro-0069.log   registro-0093.log
 registro-0021.log   registro-0047.log   registro-0071.log   registro-0097.log
 registro-0023.log   registro-0049.log   registro-0073.log   registro-0099.log
```
