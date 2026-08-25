# Desafio do Dia 04
## Nível 1
### Árvore de Arquivos Raíz do Linux com Explicações,
```bash
/              -> raiz de todo o sistema
/bin           -> armazena os binários/executáveis das aplicações
/dev           -> armazena as entidades de discos (nao montados)
/home          -> armazena os usuários e seus arquivos
/media         -> onde ficam os meios de armazenamento removíveis montados
/opt           -> binários podendo ou não ser aplicações (como scripts)
/root          -> armazena os arquivos do super usuário/administrador
/sys           -> armazena as informações do hardware
/usr           -> armazena a maior parte dos programas utilizados no dia a dia do sistema
/boot          -> armazena as principais informações necessárias para o sistema inicializar
/etc           -> armazena os arquivos de configurações
/lost+found    -> armazena pedaços de arquivos recuperados pelo utilitário fsck (ferramenta de verificação e reparo de erros) quando o sistema de arquivos sofre alguma inconsistência
/mnt           -> onde ficam os meios de armazenamento como hd e ssd montados
/proc          -> um sistema de arquivos virtual que serve como uma janela de comunicação entre o usuário e o kernel (Linux), mostrando informações em tempo real sobre o sistema e os programas em execução
/run           -> armazena dados de execução de curto prazo, como informações de processos ativos e arquivos de comunicação que os serviços do sistema precisam enquanto estão rodando (obs: seu conteúdo é armazenado na memória ram)
/srv           -> serve para armazenar dados gerados ou utilizados por serviços oferecidos pelo computador na rede
/tmp           -> armazena arquivos temporários que o sistema operacional e os aplicativos precisam apenas por um curto período
/var           -> onde as variáveis são armazenadas, também onde as logs de /usr/ são armazenadas
```
## Nível 2
### Pasta de Logs do Servidor
```bash
sysadmin@debian:/var/log$ ls
alternatives.log  apt  btmp  dpkg.log  installer  journal  lastlog  private  README  runit  wtmp  wtmp.db
```
### Pasta de Configurações
```bash
sysadmin@debian:/etc$ ls
adduser.conf            debconf.conf         hosts            manpath.config  python3         subgid
adjtime                 debian_version       hosts.allow      mime.types      python3.13      subgid-
alternatives            default              hosts.deny       mke2fs.conf     rc0.d           subuid
apparmor                deluser.conf         init.d           modprobe.d      rc1.d           subuid-
apparmor.d              depmod.d             initramfs-tools  modules         rc2.d           sudo.conf
apt                     dhcp                 inputrc          modules-load.d  rc3.d           sudoers
bash.bashrc             dhcpcd.conf          issue            motd            rc4.d           sudoers.d
bash_completion         dictionaries-common  issue.net        mtab            rc5.d           sudo_logsrvd.conf
bash_completion.d       dpkg                 kernel           nanorc          rc6.d           supercat
bindresvport.blacklist  e2scrub.conf         kernel-img.conf  netconfig       rcS.d           sv
binfmt.d                emacs                ld.so.cache      network         reportbug.conf  sysctl.d
ca-certificates         environment          ld.so.conf       networks        resolv.conf     systemd
ca-certificates.conf    ethertypes           ld.so.conf.d     nftables.conf   rmt             terminfo
console-setup           fstab                libaudit.conf    nsswitch.conf   rpc             tmpfiles.d
credstore               gai.conf             locale.alias     opt             runit           ucf.conf
credstore.encrypted     groff                locale.conf      os-release      security        udev
cron.d                  group                locale.gen       pam.conf        selinux         ufw
cron.daily              group-               localtime        pam.d           services        update-motd.d
cron.hourly             grub.d               login.defs       passwd          shadow          vconsole.conf
cron.monthly            gshadow              logrotate.conf   passwd-         shadow-         vim
crontab                 gshadow-             logrotate.d      perl            shells          wgetrc
cron.weekly             gss                  machine-id       profile         skel            X11
cron.yearly             host.conf            magic            profile.d       ssh             xattr.conf
dbus-1                  hostname             magic.mime       protocols       ssl             xdg
```
### O Serviço está Rodando?
```bash
sysadmin@debian:/etc$ systemctl
  UNIT                                                                                     LOAD   ACTIVE SUB       DESC>
  proc-sys-fs-binfmt_misc.automount                                                        loaded active running   Arbi>
  sys-devices-pci0000:00-0000:00:01.1-ata1-host0-target0:0:0-0:0:0:0-block-sr0.device      loaded active plugged   VBOX>
  sys-devices-pci0000:00-0000:00:03.0-net-enp0s3.device                                    loaded active plugged   8254>
  sys-devices-pci0000:00-0000:00:05.0-sound-card0-controlC0.device                         loaded active plugged   /sys>
  sys-devices-pci0000:00-0000:00:0d.0-ata3-host2-target2:0:0-2:0:0:0-block-sda-sda1.device loaded active plugged   VBOX>
  sys-devices-pci0000:00-0000:00:0d.0-ata3-host2-target2:0:0-2:0:0:0-block-sda-sda2.device loaded active plugged   VBOX>
  sys-devices-pci0000:00-0000:00:0d.0-ata3-host2-target2:0:0-2:0:0:0-block-sda-sda5.device loaded active plugged   VBOX>
  sys-devices-pci0000:00-0000:00:0d.0-ata3-host2-target2:0:0-2:0:0:0-block-sda.device      loaded active plugged   VBOX>
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.0-tty-ttyS0.device             loaded active plugged   /sys>
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.1-tty-ttyS1.device             loaded active plugged   /sys>
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.2-tty-ttyS2.device             loaded active plugged   /sys>
  sys-devices-platform-serial8250-serial8250:0-serial8250:0.3-tty-ttyS3.device             loaded active plugged   /sys>
  sys-devices-virtual-misc-rfkill.device                                                   loaded active plugged   /sys>
  sys-module-configfs.device                                                               loaded active plugged   /sys>
  sys-module-fuse.device                                                                   loaded active plugged   /sys>
  sys-subsystem-net-devices-enp0s3.device                                                  loaded active plugged   8254>
  -.mount                                                                                  loaded active mounted   Root>
  dev-hugepages.mount                                                                      loaded active mounted   Huge>
  dev-mqueue.mount                                                                         loaded active mounted   POSI>
  proc-sys-fs-binfmt_misc.mount                                                            loaded active mounted   Arbi>
  run-lock.mount                                                                           loaded active mounted   Lega>
  run-user-1000.mount                                                                      loaded active mounted   /run>
  sys-fs-fuse-connections.mount                                                            loaded active mounted   FUSE>
  sys-kernel-config.mount                                                                  loaded active mounted   Kern>
  sys-kernel-debug.mount                                                                   loaded active mounted   Kern>
  sys-kernel-tracing.mount                                                                 loaded active mounted   Kern>
  tmp.mount                                                                                loaded active mounted   Temp>
  systemd-ask-password-console.path                                                        loaded active waiting   Disp>
  systemd-ask-password-wall.path                                                           loaded active waiting   Forw>
  init.scope                                                                               loaded active running   Syst>
  session-1.scope                                                                          loaded active running   Sess>
  session-3.scope                                                                          loaded active running   Sess>
  apparmor.service                                                                         loaded active exited    Load>
  console-setup.service                                                                    loaded active exited    Set >
  cron.service                                                                             loaded active running   Regu>
  dbus.service                                                                             loaded active running   D-Bu>
  getty@tty1.service                                                                       loaded active running   Gett>
lines 1-38
```
### Há Espaço no Disco?
```bash
sysadmin@debian:/etc$ df -h
Sist. Arq.      Tam. Usado Disp. Uso% Montado em
udev            960M     0  960M   0% /dev
tmpfs           198M  536K  197M   1% /run
/dev/sda1        19G  1,3G   17G   8% /
tmpfs           987M     0  987M   0% /dev/shm
tmpfs           5,0M     0  5,0M   0% /run/lock
tmpfs           1,0M     0  1,0M   0% /run/credentials/systemd-journald.service
tmpfs           987M     0  987M   0% /tmp
tmpfs           1,0M     0  1,0M   0% /run/credentials/getty@tty1.service
tmpfs           198M  4,0K  198M   1% /run/user/1000
```
