# Desafio do Dia 02
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
