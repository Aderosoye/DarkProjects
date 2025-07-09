# 🌐 Azure Enterprise Network Design (Capstone Project)

**Author:** Ayobamidele Adeniyi Aderosoye  
**Date:** July 9, 2025  
**Project:** AZ-900 Capstone for Azure Fundamentals Mastery  
**Objective:** Design a secure, scalable, and enterprise-ready Azure network for future automation and cloud deployments.

---

## 🧱 1. Core Infrastructure (East US Region)

### 🔹 Virtual Network
- **Name:** `CoreVNET-EastUS`
- **Address Space:** `10.0.0.0/16`

### 🔹 Subnets
| Name       | Address Prefix | Purpose              |
|------------|----------------|----------------------|
| WebSubnet  | 10.0.1.0/24    | Hosts public-facing web server |
| AppSubnet  | 10.0.2.0/24    | Hosts internal app server      |

### 🔹 Network Security Groups (NSG)
| NSG Name     | Attached To | Rules Summary                               |
|--------------|-------------|---------------------------------------------|
| WebNSG       | WebSubnet   | Allow HTTP (80), HTTPS (443), block others  |
| AppNSG       | AppSubnet   | Allow internal traffic, block public access |

---

## 🧠 2. Hub Network & Security (West Europe Region)

### 🔹 Virtual Network
- **Name:** `HubVNET-WestEurope`
- **Address Space:** `10.1.0.0/16`

### 🔹 Components
| Resource         | Purpose                                        |
|------------------|------------------------------------------------|
| VPN Gateway      | Enables site-to-site or hybrid connectivity    |
| Azure Firewall   | Central traffic filtering and logging          |
| Route Table (UDR)| Directs outbound traffic through firewall      |
| Bastion Host     | Provides secure browser-based RDP/SSH access   |

---

## 🌉 3. VNET Peering

| Connection            | Purpose                               |
|-----------------------|----------------------------------------|
| CoreVNET ↔ HubVNET    | Enables secure communication between core and hub networks |

- **Use Remote Gateway:** Yes  
- **Allow Forwarded Traffic:** Yes  
- **Allow Gateway Transit:** Enabled from Hub → Core

---

## 📁 4. Resource Group Structure

| Resource Group       | Contents                              |
|----------------------|----------------------------------------|
| RG-CoreInfra         | CoreVNET, subnets, NSGs                |
| RG-VMs               | VMs for Web & App layers               |
| RG-NetworkSecurity   | Azure Firewall, VPN Gateway, Bastion   |
| RG-Monitoring        | Logs, Diagnostics, Network Watcher     |

---

## 🧰 5. Naming Conventions

| Resource Type | Naming Pattern                 | Example                      |
|---------------|--------------------------------|------------------------------|
| VNET          | `dark-vnet-[region]`           | `dark-vnet-eastus`           |
| Subnet        | `subnet-[function]`            | `subnet-web`, `subnet-app`   |
| VM            | `vm-[region]-[role]-[number]`  | `vm-eastus-web01`            |
| NSG           | `nsg-[subnet]`                 | `nsg-web`, `nsg-app`         |
| RG            | `rg-[function]`                | `rg-coreinfra`               |

---

## 💡 Use Case Scenarios

- Host scalable web applications with internal backend  
- Enforce strict security segmentation via NSG and Firewall  
- Prepare for hybrid cloud extensions using VPN Gateway  
- Allow remote troubleshooting via Bastion without exposing public IPs  
- Centralize logging and diagnostics for audit compliance

---

## 🚀 Next Steps

- Deploy using PowerShell (Az module or Bicep template)  
- Add monitoring via Azure Monitor + Network Watcher  
- Simulate traffic and test failover paths  
- Add automation for onboarding new VMs or services via ARM

---

## 🏁 Capstone Complete

This design forms the foundational architecture for future enterprise-grade Azure projects and serves as a sandbox for learning Azure IaaS, hybrid networking, governance, and automation at scale.
