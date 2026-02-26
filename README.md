<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=F7F7F7&width=435&lines=Initializing+labontese.sys...;Loading+Architect+Modules...;System+Online.&center=true&vCenter=true" alt="Typing SVG" />
</div>

<p align="center">
  <em>Infrastructure architect & developer — building sovereign cloud platforms, accessibility tooling, and enterprise-grade homelab environments.</em>
</p>

<div align="center">
  <a href="https://github.com/labontese">
    <img src="https://img.shields.io/github/followers/labontese?label=Followers&style=flat-square&color=0d1117&labelColor=0d1117" alt="GitHub Followers" />
  </a>
</div>

<br/>

<table>
  <tr>
    <td valign="top" width="50%">
      <h3>🛠️ Core Modules (Tech Stack)</h3>
      <div align="center">
        <img src="https://skillicons.dev/icons?i=docker,kubernetes,linux,ansible,grafana,postgres,ts,python,cloudflare,git,nginx,react&perline=6" alt="Tech Stack: Docker, Kubernetes, Linux, Ansible, Grafana, PostgreSQL, TypeScript, Python, Cloudflare, Git, Nginx, React" />
      </div>
    </td>
    <td valign="top" width="50%">
      <h3>🔥 Contribution Integrity (Streak)</h3>
      <div align="center">
        <a href="https://github.com/labontese">
          <img src="https://github-readme-streak-stats.herokuapp.com/?user=labontese&theme=dark&hide_border=true&background=0d1117" alt="GitHub Streak Stats" height="135" />
        </a>
      </div>
    </td>
  </tr>
</table>

---

## 🏗️ Architected Ecosystem (@holmdigital)

*Lead Architect & Developer for the [HolmDigital A11y Suite](https://github.com/holmdigital/a11y-hd).*

| Package | Role | Tech Stack | Distribution |
| :--- | :--- | :--- | :--- |
| **[`@holmdigital/engine`](https://www.npmjs.com/package/@holmdigital/engine)** | 🧠 **Architect** | <img src="https://skillicons.dev/icons?i=ts,nodejs,docker" alt="TypeScript, Node.js, Docker" /> | ![NPM Version](https://img.shields.io/npm/v/@holmdigital/engine?style=flat-square&color=CB3837) |
| **[`@holmdigital/components`](https://www.npmjs.com/package/@holmdigital/components)** | 🎨 **Lead Dev** | <img src="https://skillicons.dev/icons?i=react,tailwind,ts" alt="React, Tailwind, TypeScript" /> | ![NPM Version](https://img.shields.io/npm/v/@holmdigital/components?style=flat-square&color=007ACC) |
| **[`@holmdigital/standards`](https://www.npmjs.com/package/@holmdigital/standards)** | ⚖️ **Maintainer** | <img src="https://skillicons.dev/icons?i=nodejs,npm" alt="Node.js, npm" /> | ![NPM Version](https://img.shields.io/npm/v/@holmdigital/standards?style=flat-square&color=black) |

---

## 🏛️ Governance & Operations

> **Lead Developer** @ [`github.com/holmdigital`](https://github.com/holmdigital)
> *Orchestrating the sovereign cloud initiative and open standards.*

<div align="center">
  <a href="https://github.com/holmdigital">
    <img src="https://img.shields.io/badge/HolmDigital-Sovereign_Cloud_%26_Open_Standards-007ACC?style=for-the-badge&logo=github&logoColor=white" alt="HolmDigital Org" />
  </a>
</div>

---

## 🌐 Enterprise Networking & Infrastructure

A comprehensive L2/L3 environment leveraging 10G SFP+ backbones and advanced 802.1Q segmentation.

### 🏗️ Global Architecture

![Global Architecture](assets/network_render_3d.png)

#### 🗺️ Logical Topology

```mermaid
graph TD
    %% Nodes
    WAN((☁️ Internet))
    FW[🔒 pfSense<br/>Dell R240]
    Core[⚡ Switch Stack<br/>Juniper EX4200/Quanta]

    subgraph Compute ["🔥 Compute Cluster"]
        Prox[Cluster<br/>Dell R730XD]
        K8s[Kubernetes<br/>K3s Nodes]
    end

    subgraph Storage ["💾 Storage Array"]
        NAS[Truenas<br/>Dell T430]
        PBS[Backup<br/>PBS]
    end

    %% Edge Connections
    WAN <==> FW
    FW <==> Core

    %% Infrastructure Connections
    Core == 10Gb Fiber ==> Prox
    Core == 10Gb Fiber ==> NAS

    %% Internal Links
    Prox -.-> K8s
    NAS -.-> PBS
```

### ⚡ Technical Specifications

- **Core Switching**: ![Juniper](https://img.shields.io/badge/Juniper-EX4200_VC-blue?style=flat-square&logo=junipernetworks&logoColor=white) ![Quanta](https://img.shields.io/badge/Quanta-LB6M-black?style=flat-square) (24x 10GbE SFP+)
- **Virtualization**: ![Proxmox](https://img.shields.io/badge/Proxmox_VE-Cluster-E57000?style=flat-square&logo=proxmox&logoColor=white) with ![PBS](https://img.shields.io/badge/Proxmox_Backup-Server-E57000?style=flat-square&logo=proxmox&logoColor=white)
- **VLAN Matrix**:
    - `VLAN 10`: Management
    - `VLAN 20`: Enterprise Servers (Proxmox, TrueNAS)
    - `VLAN 30/40/50`: Segmented Client & Service Tiers
    - `VLAN 60/70/80`: Infrastructure & Lab Scopes
    - `VLAN 85/86`: Secure Trusted Users & Guest Access
    - `VLAN 90`: Isolated Corporate Infra (HolmDigital)
- **Compute Stack**: ![K3s](https://img.shields.io/badge/Kubernetes-K3s-326CE5?style=flat-square&logo=kubernetes&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-Swarm/Compose-2496ED?style=flat-square&logo=docker&logoColor=white)

## 🛠️ Enterprise Software Stack

- **Observability**: ![Grafana](https://img.shields.io/badge/Grafana-Stack-F46800?style=flat-square&logo=grafana&logoColor=white) (VictoriaMetrics, Loki, Alloy)
- **Security & IAM**: ![Wazuh](https://img.shields.io/badge/Wazuh-SIEM/XDR-blue?style=flat-square) ![OpenLDAP](https://img.shields.io/badge/OpenLDAP-Directory-black?style=flat-square)
- **Automation**: ![Ansible](https://img.shields.io/badge/Ansible-IaC-EE0000?style=flat-square&logo=ansible&logoColor=white) ![PowerShell](https://img.shields.io/badge/PowerShell-Automation-5391FE?style=flat-square&logo=powershell&logoColor=white)
- **IPAM**: ![phpIPAM](https://img.shields.io/badge/phpIPAM-Management-green?style=flat-square)
- **Version Control**: ![Forgejo](https://img.shields.io/badge/Forgejo-Self_Hosted-F05032?style=flat-square&logo=gitea&logoColor=white)

---

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=labontese&style=flat-square&color=0d1117&label=Profile+Views" alt="Profile Views" />
</div>
