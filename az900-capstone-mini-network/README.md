
# 🌐 AZ-900 Capstone Project — Azure Mini Enterprise Network

This project simulates a small enterprise network using core Azure services. It was built as the capstone for completing the **Microsoft AZ-900 Learning Path**.

---

## 🚀 Project Objectives

- Design and deploy a virtual network with subnets
- Deploy Windows and Linux VMs with proper segmentation
- Apply NSG rules to isolate traffic
- Create a Storage Account for blob + file data
- Apply governance tools: locks, tags, and policies

---

## 🧱 Architecture Overview

```
Resource Group: DarkCap
    └── VNet: DarkVNet (10.0.0.0/16)
        ├── Subnet-Web (10.0.1.0/24) → VM-Web (Windows)
        └── Subnet-App (10.0.2.0/24) → VM-App (Linux)
```

![Architecture Diagram](screenshots/vnet-subnets.png)

---

## 🔧 Key Azure Components Used

| Component           | Description |
|--------------------|-------------|
| **VNet + Subnets** | DarkVNet with Web and App segmentation |
| **Virtual Machines** | VM-Web (Windows Server), VM-App (Ubuntu) |
| **NSGs** | NSG on VM-Web allowing RDP, internal traffic |
| **Storage Account** | darkstorageprod (LRS, blob + file enabled) |
| **Tags + Locks** | Tagging and delete-lock on DarkCap RG |
| **Azure Policy** | Compliance check on Azure subscription |

---

## 📸 Screenshots

> Screenshots of the VNet, VMs, NSGs, Storage, and Governance features can be found in the `/screenshots` folder:
- `vnet-subnets.png`
- `vm-web-summary.png`
- `vm-app-summary.png`
- `nsg-rules.png`
- `storage-overview.png`
- `tags-locks.png`
- `policy-summary.png`

---

## 🧠 Learnings & Highlights

- Built and secured a basic cloud network using IaaS
- Applied governance controls like locks, tags, and policies
- Configured NSGs to simulate real-world segmentation
- Reinforced all theoretical concepts from AZ-900 with real deployment

---

## 📈 Next Steps

- Expand to include load balancers, VPN gateway, and diagnostics
- Use this project as a template for client deployments or Fiverr offerings
- Upgrade to AZ-104 and implement RBAC, managed identities, etc.

---

## 🏅 Author

**Ayobamidele Adeniyi Aderosoye**  
Microsoft Azure Practitioner | Cloud Architect in Training  
[GitHub Profile](https://github.com/Aderosoye) | [Email](mailto:adroyphill@gmail.com)
