# Desafio do Dia 03
## Nível 1
```bash
david@SDA-D-COTIN-51:~/Downloads/linuxtemp$ nano expnatbridgehostonly.txt
david@SDA-D-COTIN-51:~/Downloads/linuxtemp$ cat expnatbridgehostonly.txt 
Em NAT, a VM se conecta à rede mas é invisível nela. Tem acesso à internet.
Em Bridge, a VM se conecta á rede e ganha um IP próprio, se conectando à internet.
Em Host-Only, a VM não se conecta à rede de forma alguma, sem acesso à internet (mais seguro)
```
## Nível 2
### Teste Prático utilizando a VM em modo NAT
O IP da VM mudou para *10.0.2.15* e o comando de ping para o Google (8.8.8.8) resultou em êxito.
