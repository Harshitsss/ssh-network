# 🔐 SSH Configuration in Cisco Packet Tracer

This repository demonstrates how to configure **SSH (Secure Shell)** on Cisco routers and access them securely from PCs over a routed network.

---

## 🌐 Objective

To enable secure remote access to a router using **SSH** instead of unsecured protocols like Telnet. This is useful for managing routers over a network while protecting login credentials and session data.

---

## 🧱 Network Setup

- At least **one Cisco router** connected to **one or more PCs**
- **Routing (Static/OSPF)** must be configured so that the PC can reach the router's IP
- PCs must use the **Terminal** or **Command Prompt** to access the router via SSH

---

## 🔧 SSH Configuration on Router

Follow these steps in the CLI of the router:

```bash
hostname R1
ip domain-name harshit.local
username admin password cisco123
crypto key generate rsa
ip ssh version 2
line vty 0 4
 login local
 transport input ssh
```

### ✅ Explanation:

| Command | Description |
|--------|-------------|
| `hostname R1` | Sets the router's name (important for key generation) |
| `ip domain-name harshit.local` | Defines domain name required for RSA key |
| `username admin password cisco123` | Creates login user |
| `crypto key generate rsa` | Generates RSA encryption keys |
| `ip ssh version 2` | Enables SSH version 2 |
| `line vty 0 4` | Accesses virtual terminal lines |
| `login local` | Uses local user credentials |
| `transport input ssh` | Restricts access to SSH only |

---

## 💻 SSH Access from PC

Open the **Command Prompt** in the PC (Desktop > Command Prompt):

```bash
ssh -l admin <router-ip>
```

Replace `<router-ip>` with the actual IP of the router interface connected to the network.

---

## 🧪 Verification Commands (on Router)

Use the following to verify SSH setup and connected users:

```bash
show ip ssh
show users
```

---

## 👨‍💻 Author

**Harshit **  
📧 06harshit7230@gmail.com  
🌐 [GitHub Profile](https://github.com/Harshitsss)

🕒 Generated on August 05, 2025
