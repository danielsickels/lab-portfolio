# Dell PowerEdge R730 + Rancher RKE2 Kubernetes

## Single‑node lab cluster on bare metal

## Table of Contents

1. [Overview](#overview)
2. [Pre‑Installation Checklist](#pre-installation-checklist)
3. [Step‑by‑Step Installation](#step-by-step-installation)
4. [Core Cluster Add‑ons](#core-cluster-add-ons)
5. [Monitoring & Alerting](#monitoring--alerting)
6. [Maintenance Tips](#maintenance-tips)

---

## Pre‑Installation Checklist

- Firmware up‑to‑date (**BIOS**, **PERC**, **iDRAC**).  
  _Lifecycle Controller ➜ Firmware Update_
- One NIC cabled for iDRAC, another for cluster traffic.
- Ubuntu Server ISO downloaded (e.g. `ubuntu-24.04-live-server-amd64.iso`).
- Java **OpenWebStart** installed on your laptop to launch `viewer.jnlp`.
- SSH key pair ready (`~/.ssh/id_ed25519.pub`).

---

## Step‑by‑Step Installation

### 1 . Access the Virtual Console

```text
Lifecycle Controller ➜ Remote Access ➜ Launch Console
# Downloads viewer.jnlp
```

> **Java tip:** If the console hangs or shows _ClassNotFound_, re‑download the `.jnlp` and whitelist the iDRAC host in `~/.config/icedtea-web/security`.

### 2 . Switch PERC from RAID to HBA/JBOD

1. Reboot ➜ `Ctrl+R` to enter **PERC H730** config.
2. **F2 ➜ Controller Management ➜ Convert to Non‑RAID**.

### 3 . Boot & Install Ubuntu

- In the installer:
  - Disable **Secure Boot** if you see “invalid signature”.
  - Select the **main NIC** and give it a static IP (e.g. `192.168.1.50`).
  - Check **openssh‑server** so SSH works on first boot.

### 4 . Base System Hardening

### 5 . Install RKE2 (server mode)

### 6 . Remote kubectl Access

### 7 . Registry Credentials (GitHub Container Registry)
Reference it with `imagePullSecrets` in your manifests.

### 8 . DNS Tweak
Some internal DNS resolvers choke on long search domains:

---

## Core Cluster Add‑ons

| Add‑on | Install (Helm) | Purpose |
|--------|----------------|---------|
| **Argo CD** | `helm repo add argo https://argoproj.github.io/argo-helm`<br>`helm install argocd argo/argo-cd` | GitOps sync of charts/kustomize |
| **cloudflared** | `kubectl apply -f cloudflared-tunnel.yaml` | Private ingress via Cloudflare Tunnel |
| **Istio** | `helm install istio-base istio/base -n istio-system`<br>`helm install istiod istio/istiod -n istio-system` | Service mesh, mTLS, traffic splits |

---

## Monitoring & Alerting

### Stack
- **Prometheus Operator** (bundled charts)
- **Grafana** dashboards
- **Alertmanager** (email / Slack)
