# Desafio do Dia 4
## Nível 1
### Comando Find para ahar arquivos com base no nome
```bash
sysadmin@debian:/$ find /etc -name "*.conf" 2>/dev/null
/etc/adduser.conf
/etc/kernel-img.conf
/etc/host.conf
/etc/nftables.conf
/etc/locale.conf
/etc/debconf.conf
/etc/deluser.conf
/etc/modprobe.d/intel-microcode-blacklist.conf
/etc/gai.conf
/etc/systemd/pstore.conf
/etc/systemd/networkd.conf
/etc/systemd/user.conf
/etc/systemd/journald.conf
/etc/systemd/timesyncd.conf
/etc/systemd/logind.conf
/etc/systemd/system.conf
/etc/systemd/sleep.conf
/etc/selinux/semanage.conf
/etc/apt/listchanges.conf
/etc/nsswitch.conf
/etc/libaudit.conf
/etc/pam.conf
/etc/ssh/ssh_config.d/20-systemd-ssh-proxy.conf
/etc/mke2fs.conf
/etc/logrotate.conf
/etc/modules-load.d/modules.conf
/etc/e2scrub.conf
/etc/ca-certificates.conf
/etc/resolv.conf
/etc/ucf.conf
/etc/dhcpcd.conf
/etc/xattr.conf
/etc/vconsole.conf
/etc/security/access.conf
/etc/security/namespace.conf
/etc/security/group.conf
/etc/security/limits.d/10-coredump-debian.conf
/etc/security/faillock.conf
/etc/security/sepermit.conf
/etc/security/pwhistory.conf
/etc/security/limits.conf
/etc/security/time.conf
/etc/security/pam_env.conf
/etc/initramfs-tools/update-initramfs.conf
/etc/initramfs-tools/initramfs.conf
/etc/sudo.conf
/etc/sudo_logsrvd.conf
/etc/ld.so.conf
/etc/ld.so.conf.d/x86_64-linux-gnu.conf
/etc/ld.so.conf.d/libc.conf
/etc/apparmor/parser.conf
/etc/udev/iocost.conf
/etc/udev/udev.conf
/etc/reportbug.conf
sysadmin@debian:/$ find /var/log -name "*.log" 2>/dev/null
/var/log/apt/term.log
/var/log/apt/history.log
/var/log/alternatives.log
/var/log/installer/Xorg.0.log
/var/log/dpkg.log
sysadmin@debian:/$ find /usr -name "passwd" 2>/dev/null
/usr/bin/passwd
/usr/share/lintian/overrides/passwd
/usr/share/bash-completion/completions/passwd
/usr/share/doc/passwd
```
## Nível 2
### Todos os arquivos que terminam em .config de /etc/ssh
```bash
sysadmin@debian:/$ find /etc/ssh -name "*.conf" 2>/dev/null
/etc/ssh/ssh_config.d/20-systemd-ssh-proxy.conf
```
### Arquivos que pesam mais do que 1mb em /var
```bash
sysadmin@debian:/$ find /var -size +1M
/var/lib/ispell/brasileiro.hash
/var/lib/aspell/pt_BR.rws
/var/lib/dpkg/info/keyboard-configuration.config
/var/lib/apt/lists/deb.debian.org_debian_dists_trixie_main_i18n_Translation-en
/var/lib/apt/lists/deb.debian.org_debian_dists_trixie_main_i18n_Translation-pt%5fBR
find: ‘/var/lib/apt/lists/partial’: Permissão negada
/var/lib/apt/lists/deb.debian.org_debian_dists_trixie_main_binary-amd64_Packages
/var/lib/apt/lists/security.debian.org_debian-security_dists_trixie-security_main_binary-amd64_Packages
find: ‘/var/lib/private’: Permissão negada
find: ‘/var/spool/cron/crontabs’: Permissão negada
/var/cache/debconf/templates.dat
/var/cache/debconf/templates.dat-old
find: ‘/var/cache/apt/archives/partial’: Permissão negada
/var/cache/apt/srcpkgcache.bin
/var/cache/apt/pkgcache.bin
find: ‘/var/cache/private’: Permissão negada
find: ‘/var/cache/ldconfig’: Permissão negada
find: ‘/var/cache/apparmor/ac27e0ee.0’: Permissão negada
find: ‘/var/cache/apparmor/979b3ac6.0’: Permissão negada
find: ‘/var/tmp/systemd-private-0492c95209f04e4f92590ded19a3ed75-systemd-logind.service-ThIEFc’: Permissão negada
find: ‘/var/log/private’: Permissão negada
/var/log/journal/604c79dd1d714900a698b49962cc263f/system.journal
/var/log/journal/604c79dd1d714900a698b49962cc263f/system@000659cd0886ad9b-6c8bcd6571f5fa46.journal~
/var/log/journal/604c79dd1d714900a698b49962cc263f/user-1000.journal
/var/log/journal/604c79dd1d714900a698b49962cc263f/user-1000@0006597d0611dfdf-33f31e400a9b3b4f.journal~
/var/log/journal/604c79dd1d714900a698b49962cc263f/system@0006597d05429685-1f591696a45458ac.journal~
/var/log/installer/cdebconf/templates.dat
```
### Conteúdo de *usr/bin*
```bash
sysadmin@debian:/$ cd usr/bin
sysadmin@debian:/usr/bin$ ls
'['                                   getconf                 netcat                      ss
 aa-enabled                           getent                  networkctl                  ssh
 aa-exec                              getkeycodes             newgrp                      ssh-add
 aa-features-abi                      getopt                  ngettext                    ssh-agent
 acorn                                gettext                 nice                        ssh-argv0
 apropos                              gettext.sh              nisdomainname               ssh-copy-id
 apt                                  gpasswd                 nl                          ssh-keygen
 apt-cache                            gpic                    node                        ssh-keyscan
 apt-cdrom                            grep                    nodejs                      stat
 apt-config                           groff                   nohup                       stdbuf
 apt-extracttemplates                 grog                    normalizer                  streamzip
 apt-ftparchive                       grops                   nproc                       stty
 apt-get                              grotty                  nroff                       su
 apt-listchanges                      groups                  nsenter                     sudo
 apt-mark                             grub-editenv            nslookup                    sudoedit
 apt-sortpkgs                         grub-file               nstat                       sudoreplay
 arch                                 grub-fstest             nsupdate                    sum
 aspell                               grub-glue-efi           numfmt                      sync
 aspell-import                        grub-kbdcomp            od                          systemctl
 awk                                  grub-menulst2cfg        openssl                     systemd-ac-power
 b2sum                                grub-mkfont             openvt                      systemd-analyze
 base32                               grub-mkimage            os-prober                   systemd-ask-password
 base64                               grub-mklayout           pager                       systemd-cat
 basename                             grub-mknetdir           partx                       systemd-cgls
 basenc                               grub-mkpasswd-pbkdf2    passwd                      systemd-cgtop
 bash                                 grub-mkrelpath          paste                       systemd-confext
 bashbug                              grub-mkrescue           pathchk                     systemd-creds
 bits                                 grub-mkstandalone       pcilmr                      systemd-delta
 buildhash                            grub-mount              pdb3                        systemd-detect-virt
 bunzip2                              grub-ntldr-img          pdb3.13                     systemd-escape
 busctl                               grub-render-label       perl                        systemd-firstboot
 busybox                              grub-script-check       perl5.40.1                  systemd-hwdb
 bzcat                                grub-syslinux2cfg       perl5.40-x86_64-linux-gnu   systemd-id128
 bzcmp                                gtbl                    perlbug                     systemd-inhibit
 bzdiff                               gunzip                  perldoc                     systemd-machine-id-setup
 bzegrep                              gzexe                   perlivp                     systemd-mount
 bzexe                                gzip                    perlthanks                  systemd-notify
 bzfgrep                              h2ph                    pgrep                       systemd-path
 bzgrep                               h2xs                    pic                         systemd-run
 bzip2                                hardlink                pico                        systemd-socket-activate
 bzip2recover                         hd                      piconv                      systemd-stdio-bridge
 bzless                               head                    pidof                       systemd-sysext
 bzmore                               helpztags               pidwait                     systemd-sysusers
 captoinfo                            hexdump                 ping                        systemd-tmpfiles
 cat                                  host                    ping4                       systemd-tty-ask-password-agent
 catman                               hostid                  ping6                       systemd-umount
 chage                                hostname                pinky                       systemd-vpick
 chardet                              hostnamectl             pipesz                      tabs
 chardetect                           i386                    pkill                       tac
 chattr                               icombine                pl2pm                       tail
 chcon                                iconv                   pldd                        tar
 chfn                                 id                      pmap                        tasksel
 chgrp                                ijoin                   pod2html                    taskset
 chmod                                inetutils-telnet        pod2man                     tbl
 choom                                infocmp                 pod2text                    tee
 chown                                infotocap               pod2usage                   telnet
 chrt                                 install                 podchecker                  tempfile
 chsh                                 instmodsh               pr                          test
 chvt                                 ionice                  precat                      tic
 ckbcomp                              ip                      preconv                     timedatectl
 cksum                                ipcmk                   preunzip                    timeout
 clear                                ipcrm                   prezip                      tload
 clear_console                        ipcs                    prezip-bin                  toe
 cmp                                  ischroot                printenv                    top
 codepage                             ispell                  printf                      touch
 col                                  ispell-wrapper          prlimit                     tput
 colcrt                               join                    prove                       tr
 colrm                                journalctl              ps                          traceproto
 column                               js                      psfaddtable                 traceproto.db
 comm                                 json_pp                 psfgettable                 traceroute
 corelist                             kbdinfo                 psfstriptable               traceroute6
 corepack                             kbd_mode                psfxtable                   traceroute6.db
 coresched                            kernel-install          ptar                        traceroute.db
 cp                                   kill                    ptardiff                    traceroute-nanog
 cpan                                 kmod                    ptargrep                    troff
 cpan5.40-x86_64-linux-gnu            laptop-detect           ptx                         true
 cpio                                 last                    pwd                         truncate
 c_rehash                             ldd                     pwdx                        tryaffix
 crontab                              ld.so                   py3clean                    tset
 csplit                               less                    py3compile                  tsort
 ctstat                               lessecho                py3versions                 tty
 cut                                  lessfile                pydoc3                      tzselect
 cvtsudoers                           lesskey                 pydoc3.13                   ucf
 dash                                 lesspipe                pygettext3                  ucfq
 date                                 lexgrog                 pygettext3.13               ucfr
 dbus-cleanup-sockets                 lft                     python3                     uclampset
 dbus-daemon                          lft.db                  python3.13                  udevadm
 dbus-monitor                         libnetcfg               pzstd                       ul
 dbus-run-session                     link                    querybts                    umount
 dbus-send                            linux32                 rbash                       uname
 dbus-update-activation-environment   linux64                 rdma                        uncompress
 dbus-uuidgen                         linux-boot-prober       readlink                    unexpand
 dd                                   linux-check-removal     realpath                    unicode_start
 deallocvt                            linux-run-hooks         rename.ul                   unicode_stop
 debconf                              linux-update-symlinks   renice                      uniq
 debconf-apt-progress                 linux-version           reportbug                   unlink
 debconf-communicate                  ln                      report-hw                   unlzma
 debconf-copydb                       lnstat                  reset                       unmkinitramfs
 debconf-escape                       loadkeys                resizecons                  unshare
 debconf-set-selections               loadunimap              resizepart                  unxz
 debconf-show                         locale                  rev                         unzstd
 debianbts                            localectl               rgrep                       update-alternatives
 deb-systemd-helper                   localedef               rm                          uptime
 deb-systemd-invoke                   logger                  rmdir                       usb-devices
 defmt-c                              login                   rnano                       usbhid-dump
 defmt-sh                             loginctl                routel                      usbreset
 delv                                 logname                 rtstat                      users
 df                                   look                    run0                        varlinkctl
 dh_bash-completion                   ls                      runcon                      vdir
 diff                                 lsattr                  run-parts                   vi
 diff3                                lsblk                   run-with-aspell             view
 dig                                  lsb_release             rview                       vim.tiny
 dir                                  lscpu                   savelog                     vmstat
 dircolors                            lsfd                    scp                         w
 dirname                              lsinitramfs             screendump                  waitpid
 dmesg                                lsipc                   script                      wall
 dnsdomainname                        lsirq                   scriptlive                  watch
 dnstap-read                          lslocks                 scriptreplay                wc
 domainname                           lslogins                sdiff                       wdctl
 dotlockfile                          lsmem                   sed                         wget
 dpkg                                 lsmod                   select-default-iwrap        whatis
 dpkg-deb                             lsns                    select-editor               whereis
 dpkg-divert                          lsof                    sensible-browser            which
 dpkg-maintscript-helper              lspci                   sensible-editor             which.debianutils
 dpkg-query                           lsusb                   sensible-pager              whiptail
 dpkg-realpath                        lzcat                   sensible-terminal           who
 dpkg-split                           lzcmp                   seq                         whoami
 dpkg-statoverride                    lzdiff                  setarch                     word-list-compress
 dpkg-trigger                         lzegrep                 setfont                     wtmpdb
 du                                   lzfgrep                 setkeycodes                 x86_64
 dumpkeys                             lzgrep                  setleds                     xargs
 echo                                 lzless                  setlogcons                  xauth
 editor                               lzma                    setmetamode                 xsubpp
 egrep                                lzmainfo                setpci                      xz
 eject                                lzmore                  setpriv                     xzcat
 enc2xs                               man                     setsid                      xzcmp
 encguess                             mandb                   setterm                     xzdiff
 enosys                               manpath                 setupcon                    xzegrep
 env                                  man-recode              setvtrgb                    xzfgrep
 envsubst                             mapscrn                 sftp                        xzgrep
 eqn                                  mawk                    sg                          xzless
 ex                                   mcookie                 sh                          xzmore
 exch                                 md5sum                  sha1sum                     yes
 expand                               mdig                    sha224sum                   ypdomainname
 expiry                               mkdir                   sha256sum                   zcat
 expr                                 mkfifo                  sha384sum                   zcmp
 factor                               mk_modmap               sha512sum                   zdiff
 fadvise                              mknod                   shasum                      zdump
 fallocate                            mktemp                  showconsolefont             zegrep
 false                                more                    showkey                     zfgrep
 fgconsole                            mount                   shred                       zforce
 fgrep                                mountpoint              shuf                        zgrep
 file                                 mt                      skill                       zipdetails
 fincore                              mt-gnu                  slabtop                     zless
 find                                 munchlist               sleep                       zmore
 findaffix                            mv                      snice                       znew
 findmnt                              namei                   soelim                      zstd
 flock                                nano                    sort                        zstdcat
 fmt                                  nawk                    splain                      zstdgrep
 fold                                 nc                      split                       zstdless
 free                                 nc.traditional          splitfont                   zstdmt
 geqn                                 neqn                    sqv
```
