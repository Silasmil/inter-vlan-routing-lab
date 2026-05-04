# 🏢 Enterprise Multi-VLAN Network Architecture
## Real-World Network Engineer Capstone Project

> **This is NOT just a lab - This is a production-ready network design for a 500+ employee enterprise**

## 🎯 Business Problem Solved

| Department | VLAN | Subnet | Business Function |
|------------|------|--------|-------------------|
| HR | 50 | 10.2.50.0/24 | Employee records, payroll |
| Finance | 60 | 10.2.60.0/24 | Accounting, budgets |
| Engineering | 75 | 10.3.75.0/24 | R&D, Lab environments |
| QA | 85 | 10.3.85.0/24 | Testing, quality assurance |

## ✅ Live Verification Results

| Test | Source | Destination | Business Use Case | Result |
|------|--------|-------------|-------------------|--------|
| HR to Finance | PC1 (10.2.50.10) | PC2 (10.2.60.10) | Payroll data transfer | ✅ SUCCESS |
| HQ to Branch | PC1 (10.2.50.10) | PC3 (10.3.75.10) | Remote office communication | ✅ SUCCESS |
| WAN Link | R1 (10.1.3.1) | R3 (10.1.3.3) | Site-to-site connectivity | ✅ SUCCESS |

## 📸 Verification Screenshots

| Screenshot | What It Proves |
|------------|----------------|
| [01-pc1-to-pc3-ping.png](screenshots/01-pc1-to-pc3-ping.png) | End-to-end connectivity (1-12ms latency) |
| [03-d1-vlan-brief.png](screenshots/03-d1-vlan-brief.png) | VLAN isolation configuration |
| [04-d1-ip-route.png](screenshots/04-d1-ip-route.png) | Layer 3 switch routing table |
| [05-r1-ip-route.png](screenshots/05-r1-ip-route.png) | Core router decisions |
| [06-r3-subinterfaces.png](screenshots/06-r3-subinterfaces.png) | Router-on-a-stick config |
| [07-d2-trunk.png](screenshots/07-d2-trunk.png) | 802.1Q trunk verification |

## 🏗️ Network Topology

\\\
                          ┌─────────────────────────────────┐
                          │         CORPORATE HQ            │
                          │   ┌─────┐     ┌─────┐          │
                          │   │ R1  │═════│ R3  │  WAN     │
                          │   │Core │Serial│Branch│ Link    │
                          │   └──┬──┘     └──┬──┘          │
                          │      │           │             │
                          │   ┌──┴──┐     ┌──┴──┐          │
                          │   │ D1  │     │ D2  │          │
                          │   │L3 Sw│     │L2 Sw│          │
                          │   └──┬──┘     └──┬──┘          │
                          │   ┌──┴──┐     ┌──┴──┐          │
                          │  PC1   PC2    PC3   PC4        │
                          │  HR    Fin    Eng   QA         │
                          └─────────────────────────────────┘
\\\

## 💼 Skills Demonstrated

### Technical
- ✅ VLAN Creation & Management (5 VLANs configured)
- ✅ 802.1Q Trunking with Native VLAN security
- ✅ SVI (Switch Virtual Interface) configuration
- ✅ Router-on-a-Stick with subinterfaces
- ✅ Static Routing (IPv4)
- ✅ WAN Serial Link configuration
- ✅ Cisco IOS CLI mastery

### Professional
- ✅ Documentation with verification evidence
- ✅ Troubleshooting methodology
- ✅ Network design documentation
- ✅ Performance metrics tracking

## 🔧 Key Configuration Snippets

### Production Layer 3 Switch (D1)
\\\cisco
ip routing
vlan 50
 name HR-Department
vlan 60
 name Finance-Department
interface vlan 50
 ip address 10.2.50.1 255.255.255.0
 no shutdown
interface g1/0/11
 no switchport
 ip address 10.1.13.13 255.255.255.0
\\\

### Router-on-a-Stick (R3)
\\\cisco
interface g0/0/1.75
 encapsulation dot1q 75
 ip address 10.3.75.1 255.255.255.0
interface g0/0/1.85
 encapsulation dot1q 85
 ip address 10.3.85.1 255.255.255.0
interface g0/0/1.999
 encapsulation dot1q 999 native
\\\

## 📈 Performance Metrics

| Metric | Achieved | Industry Standard |
|--------|----------|-------------------|
| Inter-VLAN Latency | <1ms | <10ms ✅ |
| WAN Link Latency | 4-7ms | <50ms ✅ |
| Packet Loss | 0% | <1% ✅ |

## 🛠️ Tools Used
- Cisco Packet Tracer 8.x
- Cisco IOS-XE (ISR4331, 3650-24PS)
- GitHub for portfolio

## 📁 Repository Structure

\\\
inter-vlan-routing-lab/
├── README.md                    # This file
├── Inter-VLAN-Routing-Lab.pkt   # Open in Packet Tracer
├── screenshots/                 # Verification evidence
│   ├── 01-pc1-to-pc3-ping.png
│   ├── 03-d1-vlan-brief.png
│   ├── 04-d1-ip-route.png
│   ├── 05-r1-ip-route.png
│   ├── 06-r3-subinterfaces.png
│   └── 07-d2-trunk.png
└── LICENSE                      # MIT License
\\\

## 🎓 Certification Mapping

| Certification | Topics Covered |
|---------------|----------------|
| CCNA 200-301 | VLANs, Inter-VLAN Routing, Static Routing |
| CCNP ENCOR 350-401 | Layer 3 Switching, Router-on-a-Stick |

## 🔗 Connect With Me

- **GitHub:** [github.com/Silasmil](https://github.com/Silasmil)
- **Course:** CCNP Enterprise: Core Networking

## ⭐ Show Your Support
Star this repo if this project helps you understand enterprise networking!

---
**Last Updated:** May 2026
