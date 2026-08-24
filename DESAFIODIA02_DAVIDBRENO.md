# Desafio do Dia 02
### Criando as 15 sub-pastas
```bash
david@SDA-D-COTIN-51:~/Downloads/linuxtemp$ ls
dia02
david@SDA-D-COTIN-51:~/Downloads/linuxtemp$ mkdir -p {dia01,dia03,dia04,dia05,dia06,dia07,dia08,dia09,dia10,dia11,dia12,dia13,dia14,dia15}
david@SDA-D-COTIN-51:~/Downloads/linuxtemp$ ls
dia01  dia02  dia03  dia04  dia05  dia06  dia07  dia08  dia09  dia10  dia11  dia12  dia13  dia14  dia15
```
### Criação do README.md e seu conteúdo
```bash
david@SDA-D-COTIN-51:~/Downloads/linuxtemp$ nano README.txt
david@SDA-D-COTIN-51:~/Downloads/linuxtemp$ ls
README.txt  dia01  dia02  dia03  dia04  dia05  dia06  dia07  dia08  dia09  dia10  dia11  dia12  dia13  dia14  dia15
david@SDA-D-COTIN-51:~/Downloads/linuxtemp$ cat README.txt 
O curso sobre linux no contexto de servidores ns ensina a saber lidar com uma falha em um servidor sem precisar 
de interface gráfica para conseguir solucionar, a estar preparados para conseguir solucionar ao invés de criar 
mais problemas. Este curso é para aquela pessoa que quer trabalhar ou até mesmo apenas estudar o funcionamento 
de servidores, como eles podem apresentar problemas e como solucionar estes problemas sem necessitar do uso de 
interfaces gráficas. Eu espero aprender tudo isso que foi falado embora entenda que não é possível saber de tudo 
e que, ás vezes, a única forma de aprender seja fazendo.
``` 
### Pegando as informações do sistema e as escrevendo e salvando em info-sistema.txt
```bash
david@SDA-D-COTIN-51:~/Downloads/linuxtemp/dia02$ uname -a > info-sistema.txt
david@SDA-D-COTIN-51:~/Downloads/linuxtemp/dia02$ ls
info-sistema.txt
david@SDA-D-COTIN-51:~/Downloads/linuxtemp/dia02$ cat info-sistema.txt 
Linux SDA-D-COTIN-51 7.0.0-30-generic #30-Ubuntu SMP PREEMPT_DYNAMIC Fri Jul 31 18:22:54 UTC 2026 x86_64 GNU/Linux
```
### Pegando as informações da distribuição (ubuntu) e as escrevendo e salvando em info-distro.txt
```bash
david@SDA-D-COTIN-51:~/Downloads/linuxtemp/dia02$ cat /etc/os-release > info-distro.txt
david@SDA-D-COTIN-51:~/Downloads/linuxtemp/dia02$ ls
info-distro.txt  info-sistema.txt
david@SDA-D-COTIN-51:~/Downloads/linuxtemp/dia02$ cat info-distro.txt 
PRETTY_NAME="Ubuntu 26.04 LTS"
NAME="Ubuntu"
VERSION_ID="26.04"
VERSION="26.04 LTS (Resolute Raccoon)"
VERSION_CODENAME=resolute
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=resolute
LOGO=ubuntu-logo
```
### Versão do Kernel
```bash
david@SDA-D-COTIN-51:~/Downloads/linuxtemp/dia02$ uname -r
7.0.0-30-generic
```
### Explicação do nominação das versões do Kernel do Linux 7.1.10-generic
- O primeiro número *7* representa a versão príncipal.
- O segundo número *1* representa o número da versão revisada principal.
- O terceiro número *10* representa o nível de correção/correções menores (como pequenos ajustes).
