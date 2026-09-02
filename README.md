<div align="center">

  <!-- Header Banner Animado -->
  <img src="https://capsule-render.vercel.app/api?type=waving&color=A81D33&height=220&section=header&text=Desafios%20Linux%20Server&fontSize=48&fontColor=ffffff&animation=twinkling&desc=Debian%2013%20(Trixie)%20%E2%80%A2%20SysAdmin%20%26%20Infraestrutura&descSize=18&descAlignY=72" width="100%" alt="Header Banner"/>

  <!-- Typing SVG Animado -->
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=D32F2F&center=true&vCenter=true&width=600&height=50&lines=Laborat%C3%B3rios+Pr%C3%A1ticos+de+Servidores;Configura%C3%A7%C3%A3o+de+Servi%C3%A7os+de+Rede;Hardening+%26+Seguran%C3%A7a+no+Debian+13;Automa%C3%A7%C3%A3o+com+Shell+Scripting" alt="Typing SVG" />
  </a>

  <br/><br/>

  <!-- Badges Animados e Estáticos -->
  <img src="https://img.shields.io/badge/OS-Debian%2013%20(Trixie)-A81D33?style=for-the-badge&logo=debian&logoColor=white" alt="Debian Badge" />
  <img src="https://img.shields.io/badge/Kernel-Linux%206.x-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux Badge" />
  <img src="https://img.shields.io/badge/Shell-Bash Script-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white" alt="Bash Badge" />
  <img src="https://img.shields.io/badge/Status-Em%20Desenvolvimento-2E7D32?style=for-the-badge&logo=git&logoColor=white" alt="Status Badge" />

</div>

---

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-8408-46876c201700.gif" width="100%" alt="Divisor Animado">

## 📌 Sobre o Repositório

Este repositório reúne **desafios práticos, laboratórios, scripts e anotações** desenvolvidos ao longo do curso de **Administração de Servidores Linux**, utilizando como distribuição base o **Debian 13 (Trixie)**.

O objetivo principal é documentar a implantação, administração, manutenção e segurança de serviços essenciais de infraestrutura corporativa, servindo como guia prático e portfólio de Engenharia de Sistemas e SysAdmin.

<br/>

<div align="center">

┌────────────────────────────────────────────────────────────────────────┐
│                        DEBIAN 13 SERVER STACK                          │
├──────────────┬──────────────┬──────────────┬─────────────┬─────────────┤
│   SSH / PAM  │ NGINX / HTTP │  BIND9 / DNS │ KEA / DHCP  │ SAMBA / NFS │
├──────────────┴──────────────┴──────────────┴─────────────┴─────────────┤
│                   NFTables Firewall & Fail2ban                         │
├────────────────────────────────────────────────────────────────────────┤
│                    Debian 13 GNU/Linux Core System                     │
└────────────────────────────────────────────────────────────────────────┘


</div>

---

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-8408-46876c201700.gif" width="100%" alt="Divisor Animado">

## 🚀 Tecnologias & Ferramentas Utilizadas

| Categoria | Tecnologias / Pacotes |
| :--- | :--- |
| **Sistema Operacional** | Debian 13 (Trixie) Server (Netinst / Headless) |
| **Servidores Web & DB** | Nginx, Apache2, MariaDB / MySQL, PHP-FPM |
| **Serviços de Rede** | BIND9 (DNS), Kea DHCP / ISC-DHCP, OpenSSH |
| **Armazenamento & Redes**| Samba 4 (AD/NAS), NFS, FTP (VSFTPD) |
| **Segurança & Firewall** | NFTables, UFW, Fail2ban, AppArmor, TLS/SSL (Certbot) |
| **Automação & Shell** | Bash Scripting, Cron, Systemd Timers, Git |
| **Virtualização / Lab** | Proxmox VE, VirtualBox, KVM/QEMU |

---

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-8408-46876c201700.gif" width="100%" alt="Divisor Animado">

## 📂 Módulos e Desafios

<details>
<summary><b>🔹 Módulo 01: Instalação, Particionamento e Pós-Instalação</b></summary>

<br/>

- [x] Instalação Mínima (Netinst) sem interface gráfica.
- [ ] Particionamento avançado LVM (Logical Volume Manager) + SWAP.
- [x] Configuração de repositórios `/etc/apt/sources.list` no Debian 13.
- [ ] Configuração de interfaces de rede estáticas (`/etc/network/interfaces` e `systemd-networkd`).
- [x] Atualização e limpeza do sistema com `apt update && apt full-upgrade`.

</details>

<details>
<summary><b>🔹 Módulo 02: Gestão de Usuários, Permissões e Processos</b></summary>

<br/>

- [x] Criação e gerenciamento de usuários (`useradd`, `usermod`, `chage`).
- [x] Políticas de grupos, permissões Especiais (SUID, SGID, Sticky Bit) e ACLs (`setfacl`).
- [ ] Gerenciamento de serviços com `systemctl` e criação de Units personalizadas (`/etc/systemd/system/`).
- [ ] Monitoramento de processos (`top`, `htop`, `ps`, `kill`, `nice/renice`).

</details>

<details>
<summary><b>🔹 Módulo 03: Serviços de Rede Essenciais (DHCP, DNS e SSH)</b></summary>

<br/>

- [ ] **SSH Hardening:** Alteração de porta padrão, desativação do login root, autenticação via chave pública (Ed25519) e integração com Fail2ban.
- [ ] **DNS (BIND9):** Configuração de zonas diretas, reversas, forwarders e chaves de segurança.
- [ ] **DHCP (Kea / ISC-DHCP):** Atribuição de IPs dinâmicos, reserva por endereço MAC e escopos de rede.

</details>

<details>
<summary><b>🔹 Módulo 04: Servidores Web e Banco de Dados (LAMP/LEMP)</b></summary>

<br/>

- [ ] Instalação e otimização do **Nginx** e **Apache2**.
- [ ] Configuração de **Virtual Hosts** e blocos `server`.
- [ ] Instalação do **MariaDB Server** com hardening (`mariadb-secure-installation`).
- [ ] Implementação de **Certificados SSL/TLS** gratuitos via Let's Encrypt / Certbot.

</details>

<details>
<summary><b>🔹 Módulo 05: Compartilhamento de Arquivos e Armazenamento</b></summary>

<br/>

- [ ] Configuração de **Samba Server** para integração com clientes Windows/Linux.
- [ ] Criação de compartilhamentos de rede com permissões por grupo.
- [ ] Montagem de volumes via **NFSv4** (Network File System).
- [ ] Configuração do **VSFTPD** com restrição de chroot para usuários.

</details>

<details>
<summary><b>🔹 Módulo 06: Segurança, Firewall e Hardening</b></summary>

<br/>

- [ ] Regras avançadas de filtragem com **NFTables** (Substituto do IPTables no Debian 13).
- [ ] Proteção contra ataques de força bruta com **Fail2ban**.
- [ ] Auditoria de sistema com **Lynis** e **AIDE**.
- [ ] Configuração de Logs centralizados via `rsyslog` / `journalctl`.

</details>

---

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-8408-46876c201700.gif" width="100%" alt="Divisor Animado">

## 📊 Progresso dos Desafios

```text
Módulo 01: Instalação & Pós-Instalação [████████████████████] 100%
Módulo 02: Usuários & Systemd          [████████████████░░░░] 100%
Módulo 03: SSH, DNS & DHCP             [░░░░░░░░░░░░░░░░░░░░] 100%
Módulo 04: Web LEMP / LAMP Stack       [░░░░░░░░░░░░░░░░░░░░]  50%
Módulo 05: Samba & NFS Storage         [░░░░░░░░░░░░░░░░░░░░]  25%
Módulo 06: NFTables & Hardening        [░░░░░░░░░░░░░░░░░░░░]  10%
🌲 Estrutura de Diretórios do Repositório
Bash
Desafios_Linux_Server/
├── 📁 modulos/
│   ├── 📁 mod01-instalacao-pos/
│   │   ├── 📄 sources.list
│   │   ├── 📄 interfaces-network
│   │   └── 📄 README.md
│   ├── 📁 mod02-usuarios-systemd/
│   │   ├── 📄 meu-servico.service
│   │   └── 📄 scripts-permissoes.sh
│   ├── 📁 mod03-servicos-rede/
│   │   ├── 📁 bind9/
│   │   ├── 📁 kea-dhcp/
│   │   └── 📁 ssh/
│   └── ...
├── 📁 scripts/
│   ├── 📄 auto-update.sh
│   ├── 📄 backup-configs.sh
│   └── 📄 firewall-nftables.sh
├── 📁 docs/
│   └── 📄 anotacoes-debian13.md
├── 📄 .gitignore
├── 📄 LICENSE
└── 📄 README.md
💻 Como Reproduzir os Labs
Pré-requisitos
Software de Virtualização (VirtualBox, VMware ou Proxmox)

ISO do Debian 13 (Trixie) Netinst

Conexão de rede em modo Bridge ou Host-Only para testes

1. Clonar o repositório
```bash
git clone [https://github.com/SEU-USUARIO/Desafios_Linux_Server.git](https://github.com/SEU-USUARIO/Desafios_Linux_Server.git)
cd Desafios_Linux_Server
```
2. Tornar os scripts executáveis
```bash
chmod +x scripts/*.sh
```
3. Exemplo: Executar o script de atualização do Debian 13
```bash
sudo ./scripts/auto-update.sh
```
⚡ Comandos Rápidos do Debian 13
# Atualização completa do sistema
sudo apt update && sudo apt full-upgrade -y && sudo apt autoremove -y

# Verificar logs do sistema em tempo real
sudo journalctl -xfu nginx.service

# Checar portas abertas e conexões ativas
sudo ss -tulpn

# Aplicar regras do NFTables
sudo nft -f /etc/nftables.conf
🤝 Contribuição & Sugestões
Contribuições, correções de scripts ou melhorias na documentação são super vindas!

Faça um Fork do projeto

Crie uma Branch para sua feature (git checkout -b feature/NovaFeature)

Faça o Commit das suas alterações (git commit -m 'Add: Nova feature')

Faça o Push para a Branch (git push origin feature/NovaFeature)

Abra um Pull Request

Desenvolvido com ☕ e muito Shell Script no Debian Linux.
