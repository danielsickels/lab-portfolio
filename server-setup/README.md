# Dell PowerEdge R730 + Rancher RKE2 Kubernetes

## Single‑node lab cluster on bare metal

---

## Pre‑Installation Checklist

- Firmware up‑to‑date (**BIOS**, **PERC**, **iDRAC**).  
  _Lifecycle Controller ➜ Firmware Update_
- One NIC cabled for iDRAC, another for cluster traffic.
- Ubuntu Server ISO downloaded (e.g. `ubuntu-24.04-live-server-amd64.iso`).
- Java **OpenWebStart** installed on your laptop to launch `viewer.jnlp`.
- SSH key pair ready.

---

## Step‑by‑Step Installation

### 1 . Access the Virtual Console

```text
Lifecycle Controller ➜ Remote Access ➜ Launch Console
# Downloads viewer.jnlp
```

> **Java tip:** If the console hangs or shows _ClassNotFound_, re‑download the `.jnlp` and whitelist the iDRAC host in `~/.config/icedtea-web/security`, if using icedtea.

### 2 . Switch PERC from RAID to HBA/JBOD

1. Reboot ➜ `Ctrl+R` to enter **PERC H730** config.
2. **F2 ➜ Controller Management ➜ Convert to Non‑RAID**.

### 3 . Boot & Install Ubuntu

- In the installer:
  - Disable **Secure Boot** if you see “invalid signature”.
  - Select the **main NIC** and give it a static IP (e.g. `192.168.1.50`).
  - Check **openssh‑server** so SSH works on first boot.

### 4 . Install RKE2 (server mode)
- Use the following:```https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-cluster-setup/rke2-for-rancher```
- The installer adds a kubeconfig at 
- ```/etc/rancher/rke2/rke2.yaml```, which you can copy and save to ```~/.kube/config```. 
- From here, make sure to point the config to your private IP of the server.

### 5 . Registry Credentials (GHCR: GitHub Container Registry)
- Using the following configuration file, this is set up at the node level to act as an auth for all ghcr image pulling.
```
mirrors:
  <REGISTRY>:
    endpoint:
      - https://<REGISTRY>/v2
configs:
  <REGISTRY>:
    auth:
      username: <BASIC AUTH USERNAME>
      password: <BASIC AUTH PASSWORD>
      token: <BEARER TOKEN>
    tls:
      ca_file: <PATH TO SERVER CA>
      cert_file: <PATH TO CLIENT CERT>
      key_file: <PATH TO CLIENT KEY>
      insecure_skip_verify: <SKIP TLS CERT VERIFICATION BOOLEAN>
```

### 6 . DNS Ndots
In order to avoid timeouts, set ndots: 1, to force the resolver to try the full domain first.
```
kubelet:
  resolvConf: /etc/rancher/rke2/resolv.conf
```

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
