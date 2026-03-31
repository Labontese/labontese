# Monitoring Stack Playbook

Ansible playbook that deploys a complete Prometheus + Grafana + Node Exporter
monitoring stack using Docker Compose.

## What it does

1. Installs Docker and dependencies
2. Creates directory structure
3. Deploys Prometheus with scrape targets
4. Deploys Grafana with auto-provisioned datasource and dashboards
5. Deploys Node Exporter for host metrics
6. Opens firewall ports (UFW)
7. Starts the stack via Docker Compose

## Stack

| Service        | Port | Purpose                    |
|----------------|------|----------------------------|
| Prometheus     | 9090 | Metrics collection         |
| Grafana        | 3000 | Dashboards and alerting    |
| Node Exporter  | 9100 | Host metrics (CPU/RAM/disk)|

## Pre-provisioned dashboard

The playbook includes a Node Exporter Overview dashboard with:
- CPU usage per instance
- Memory usage per instance
- Disk usage (root filesystem)
- Network traffic (rx/tx)

## Usage

```bash
# Edit inventory with your server details
vim inventory.yml

# Edit prometheus_targets in site.yml to add your scrape targets
vim site.yml

# Run the playbook
ansible-playbook -i inventory.yml site.yml

# With vault password (if using encrypted grafana password)
ansible-playbook -i inventory.yml site.yml --ask-vault-pass
```

## Customization

### Add scrape targets

Edit `prometheus_targets` in `site.yml`:

```yaml
prometheus_targets:
  - name: localhost
    address: "localhost:9100"
  - name: my-new-server
    address: "10.0.1.30:9100"
```

### Change Grafana password

For production, encrypt the password with Ansible Vault:

```bash
ansible-vault encrypt_string 'your-secure-password' --name 'vault_grafana_password'
```

Add the output to `group_vars/monitoring/vault.yml`.

### Change retention

```yaml
prometheus_retention: "90d"  # default is 30d
```

## Requirements

- Ansible 2.15+
- Target: Ubuntu 22.04/24.04
- `community.docker` collection (`ansible-galaxy collection install community.docker`)

## File structure

```
monitoring-stack/
  site.yml              # Main playbook
  inventory.yml         # Server inventory
  README.md             # This file
```
