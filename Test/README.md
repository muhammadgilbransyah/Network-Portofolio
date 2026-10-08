# Portofolio Lab Jaringan Multi-Vendor dan Routing

### Hands-on Networking Labs menggunakan PNETLab

Selamat datang di repositori portofolio saya.

Repositori ini berisi kumpulan **hands-on networking labs** yang saya kerjakan menggunakan **PNETLab** untuk memperdalam pemahaman mengenai networking, routing, troubleshooting, dan konektivitas antar perangkat.

Project di dalam repositori ini mencakup implementasi **Static Routing, RIPv2, OSPF, EIGRP, eBGP, Route Redistribution**, serta satu project **multi-vendor** yang menggunakan FortiGate, MikroTik, dan Cisco.

Setiap project dilengkapi dengan topologi, konfigurasi utama, proses pengujian, dan hasil verifikasi.

---

## Project Portfolio

### 01. Multi-Vendor Secure SDWAN Branch Office Tunneling

**Folder:** `01-multi-vendor-secure-sdwan/`

Project multi-vendor yang menghubungkan **FortiGate, MikroTik, dan Cisco** dalam simulasi koneksi antara Head Office dan Branch Office melalui jaringan ISP.

**Teknologi yang digunakan:**
- FortiGate
- MikroTik RouterOS
- Cisco IOL
- GRE Tunnel
- IPsec VPN
- Static Routing
- DHCP

**Highlight:**

Pada awalnya saya mencoba menggunakan **IPsec VPN**, tetapi menemukan kendala kompatibilitas algoritma enkripsi antara FortiGate Trial yang digunakan dan MikroTik RouterOS v7.

Setelah menganalisis masalah tersebut, saya mengganti metode tunneling menjadi **GRE** agar konektivitas antar-site tetap dapat diuji.

Project ini menjadi salah satu latihan troubleshooting dan multi-vendor yang paling kompleks dalam repositori ini.

![Topology 1](Topology%201.png)

---

### 02. Multi-Protocol Dynamic Route Redistribution

**Folder:** `02-multi-protocol-route-redistribution/`

Project untuk mempelajari pertukaran informasi routing antara beberapa routing protocol dalam satu jaringan.

**Routing protocol yang digunakan:**
- EIGRP
- OSPF
- eBGP
- Route Redistribution

Project ini berfokus pada bagaimana route dari satu routing protocol dapat didistribusikan ke routing domain lainnya.

Saya juga mempelajari penggunaan **seed metric pada EIGRP** dan penggunaan parameter `subnets` pada OSPF saat melakukan redistribution.

![Topology 2](Topology%202.png)

---

### 03. Recursive Static Routing

**Folder:** `03-recursive-static-routing/`

Project untuk memahami bagaimana router menentukan jalur forwarding ketika static route menggunakan alamat **next-hop** yang tidak terhubung langsung ke interface tujuan.

**Teknologi yang digunakan:**
- Cisco IOSv
- Static Routing
- Recursive Routing
- Next-Hop Resolution
- VLSM
- DHCP

Fokus utama project ini adalah memahami proses **recursive lookup**, yaitu ketika router perlu mencari kembali jalur menuju alamat next-hop sebelum dapat meneruskan packet ke jaringan tujuan.

![Topology 3](Topology%203.png)

---

### 04. Enterprise OSPF Area 0

**Folder:** `04-enterprise-ospf-architecture/`

Project untuk mempraktikkan **OSPF Single-Area** menggunakan Cisco IOL.

Topology terdiri dari beberapa router yang saling terhubung melalui jaringan point-to-point dan beberapa jaringan LAN.

**Teknologi yang digunakan:**
- Cisco IOL
- OSPFv2
- Area 0
- OSPF Neighbor Adjacency
- VLSM
- DHCP

Project ini membantu saya memahami proses pembentukan **OSPF neighbor adjacency**, pertukaran informasi routing, hingga status neighbor mencapai **FULL**.

![Topology 4](Topology%204.png)

---

### 05. External BGP Multi-AS

**Folder:** `05-bgp-autonomous-system/`

Project untuk mempelajari dasar **External BGP (eBGP)** dan komunikasi routing antar Autonomous System.

Topology menggunakan beberapa AS yang merepresentasikan jaringan enterprise dan provider.

**Teknologi yang digunakan:**
- Cisco IOL
- eBGP
- Autonomous System
- BGP Neighbor
- TCP Port 179
- AS-Path
- Network Advertisement

Fokus project ini adalah memahami proses pembentukan BGP peering, advertisement prefix, serta penggunaan **AS-Path** dalam proses routing antar-AS.

![Topology 5](Topology%205.png)

---

### 06. Dynamic RIPv2 with VLSM

**Folder:** `06-dynamic-routing-ripv2/`

Project untuk mempraktikkan routing dinamis menggunakan **RIPv2** pada jaringan dengan subnet yang berbeda-beda.

**Teknologi yang digunakan:**
- Cisco IOSv
- RIPv2
- VLSM
- `no auto-summary`
- Split Horizon
- Hop Count

Project ini membantu saya memahami perbedaan perilaku routing classful dan classless serta pentingnya `no auto-summary` ketika menggunakan VLSM.

![Topology 6](Topology%206.png)

---

## Technical Skills Practiced

### Routing

- Static Routing
- Recursive Static Routing
- RIPv2
- OSPFv2
- EIGRP
- eBGP
- Route Redistribution
- VLSM / Subnetting

### Networking

- TCP/IP
- IP Addressing
- DHCP
- LAN / WAN
- Next-Hop Resolution
- Routing Table Analysis
- Network Connectivity Testing

### Security & Tunneling

- Basic FortiGate Configuration
- Basic Firewall Policy
- IPsec VPN Concepts
- GRE Tunnel
- Multi-Vendor Connectivity

### Network Platforms

- Cisco IOSv
- Cisco IOL
- MikroTik RouterOS
- FortiGate

---

## Tools

- **PNETLab** — Network emulation and lab environment
- **Winbox** — MikroTik management
- **FortiGate GUI** — FortiGate configuration
- **Cisco CLI** — Cisco device configuration
- **Cisco Packet Tracer** — Network simulation and practice

---

## How I Approach Each Lab

Setiap project saya kerjakan dengan alur sederhana:

```text
Design
  ↓
Build Topology
  ↓
Configure Devices
  ↓
Test Connectivity
  ↓
Troubleshoot
  ↓
Verify Result
  ↓
Document
