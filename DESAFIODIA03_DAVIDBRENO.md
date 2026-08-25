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
## Nível 3
### Port Forwarding
O Port Forwarding (encaminhamento de portas) no contexto de Máquinas Virtuais é o ato de encominhar o sistema da máquina virtual para dentro da rede LAN da fonte de conexão com a utilização do NAT.
### Bridge + Host-Only
Sim, é possível utilizar Bridge + Host-Only na mesma VM conectando dois adaptadores de rede nas configurações da Máquina Virtual. Um em modo Bridge e outro em Host-Only.
### O que acontece com os Programas que estao rodando dentro da VM quando voce volta a um Snapshot anterior
As aplicações são encerradas tudo aquilo que foi feito depois da criação da Snapshot, poderá ser perdido.
### Lista de Snapshots de uma VM
```bash
david@SDA-D-COTIN-51:~/Downloads/linuxtemp$ VBoxManage snapshot "debain-server" list
   Name: snapshot_16h_24/08/26 (UUID: 6f456be7-1b46-4c1a-a913-f7a85547ea68) *
```
