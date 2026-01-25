# tech-visionary @ labontese <!-- 👋 -->

Chief Innovation Architect and Developer focused on high-availability, hybrid-infrastructure environments, and regulatory-compliant software ecosystems. I manage a geo-redundant infrastructure across Hetzner (Production) and a sophisticated Homelab (Hot-Standby).

## Tech Stack
<div align="center">
  <img src="https://skillicons.dev/icons?i=docker,kubernetes,linux,ansible,grafana,postgres,ts,python,cloudflare,git,nginx,react" />
</div>

## Enterprise Networking & Infrastructure
A comprehensive L2/L3 environment leveraging 10G SFP+ backbones and advanced 802.1Q segmentation.

### 🏗️ Global Architecture
```mermaid
graph TD
    subgraph "External Scopes"
        CF["Cloudflare (WAF/CDN/Tunnel)"]
    end

    subgraph "Production (Hetzner)"
        HZ["Primary Docker Node (i5-13500, 64GB)"]
    end

    subgraph "Hot-Standby (Homelab)"
        PF["pfSense Gateway"]
        JN["Juniper EX4200 Virtual Chassis (VC Core)"]
        PV["Proxmox Cluster (R730xd | T430 | R240)"]
        OW["OpenWrt WAP (VLAN Bridging)"]
    end

    CF --> HZ
    CF --> PF
    PF --> JN
    JN --- LB6["Quanta LB6M (10GbE Core)"]
    LB6 --- PV
    JN --- OW
    HZ -. "Streaming Replication (PostgreSQL)" .-> PV
```

### ⚡ Technical Specifications
- **Core Switching**: ![Juniper](https://img.shields.io/badge/Juniper-EX4200_VC-blue?style=flat-square&logo=junipernetworks&logoColor=white) ![Quanta](https://img.shields.io/badge/Quanta-LB6M-black?style=flat-square) (24x 10GbE SFP+)
- **Virtualization**: ![Proxmox](https://img.shields.io/badge/Proxmox_VE-Cluster-E57000?style=flat-square&logo=proxmox&logoColor=white) with ![PBS](https://img.shields.io/badge/Proxmox_Backup-Server-E57000?style=flat-square&logo=proxmox&logoColor=white)
- **VLAN Matrix**:
    - `VLAN 1`: Management (Native)
    - `VLAN 10`: Enterprise Servers (Proxmox, TrueNAS)
    - `VLAN 20/30/40`: Segmented Client & Service Tiers
    - `VLAN 50/70/80`: Infrastructure & Lab Scopes
    - `VLAN 60/65`: Secure Trusted Users & Guest Access
    - `VLAN 90`: Isolated Corporate Infra (HolmDigital)
- **Compute Stack**: ![K3s](https://img.shields.io/badge/Kubernetes-K3s-326CE5?style=flat-square&logo=kubernetes&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-Swarm/Compose-2496ED?style=flat-square&logo=docker&logoColor=white)

## 🛠️ Enterprise Software Stack
- **Observability**: ![Grafana](https://img.shields.io/badge/Grafana-Stack-F46800?style=flat-square&logo=grafana&logoColor=white) (VictoriaMetrics, Loki, Alloy)
- **Security & IAM**: ![Wazuh](https://img.shields.io/badge/Wazuh-SIEM/XDR-blue?style=flat-square) ![OpenLDAP](https://img.shields.io/badge/OpenLDAP-Directory-black?style=flat-square)
- **Automation**: ![Ansible](https://img.shields.io/badge/Ansible-IaC-EE0000?style=flat-square&logo=ansible&logoColor=white) ![PowerShell](https://img.shields.io/badge/PowerShell-Automation-5391FE?style=flat-square&logo=powershell&logoColor=white)
- **IPAM**: ![phpIPAM](https://img.shields.io/badge/phpIPAM-Management-green?style=flat-square)
- **Version Control**: ![Forgejo](https://img.shields.io/badge/Forgejo-Self_Hosted-F05032?style=flat-square&logo=gitea&logoColor=white)

<div align="center">
  <a href="https://github.com/labontese">
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=labontese&layout=compact&theme=radical&card_width=400" alt="Top Languages" width="48%" />
  </a>
  <a href="https://github.com/labontese">
    <img src="https://github-readme-stats.vercel.app/api?username=labontese&show_icons=true&theme=radical&card_width=400" alt="GitHub Stats" width="48%" />
  </a>
</div>

---
