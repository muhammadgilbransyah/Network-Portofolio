# Portofolio Lab Jaringan Multi-Vendor dan Protokol Routing Dinamis Cisco

### Implementasi Secure SD-WAN, Route Redistribution, dan Routing Cisco (OSPF, BGP, RIPv2)

Selamat datang di repositori portofolio teknik jaringan saya. Repositori ini mendokumentasikan serangkaian implementasi laboratorium hands-on menggunakan simulator **PNetLab**. Proyek-proyek di dalamnya berfokus pada routing dinamis, route redistribution, recursive static routing, interdomain routing, serta konektivitas jaringan multi-vendor.

---

## Ringkasan Eksekutif Repositori Portofolio

### Proyek 1: Multi-Vendor Secure SD-WAN Networking Lab

*   **Wilayah Folder:** `01-multi-vendor-secure-sdwan/`
*   **Teknologi Inti:** FortiGate, MikroTik RouterOS, Cisco IOS, GRE Tunnel, Firewall Policy.
*   **Analisis Masalah:** Proyek ini mensimulasikan konektivitas antar-site menggunakan perangkat dari beberapa vendor. Pada tahap awal, konektivitas antar-site direncanakan menggunakan IPsec VPN. Namun, terdapat keterbatasan pada image **FortiGate Trial** yang digunakan sehingga proposal Phase 1 hanya tersedia dengan algoritma DES, sedangkan **MikroTik RouterOS v7** yang digunakan tidak mendukung DES. Setelah menganalisis kendala interoperabilitas tersebut, metode tunneling dialihkan ke **GRE** untuk membangun konektivitas antar-site.
*   **Validasi:** Pengujian dilakukan dengan memeriksa status tunnel dan konektivitas antar jaringan melalui routing serta ping antar-site.
*   **Arsitektur Topologi:**

![Topology 1](Topology%201.png)

---

### Proyek 2: Multi-Protocol Dynamic Route Redistribution Lab

*   **Wilayah Folder:** `02-multi-protocol-route-redistribution/`
*   **Teknologi Inti:** Cisco IOSv, OSPF, EIGRP, eBGP, Mutual Route Redistribution, Seed Metrics.
*   **Analisis Masalah:** Lab ini mensimulasikan jaringan dengan beberapa routing protocol yang membutuhkan pertukaran informasi routing antar domain. Implementasi berfokus pada proses **mutual redistribution** antara OSPF, EIGRP, dan BGP serta pemahaman terhadap kebutuhan metric ketika sebuah route dipindahkan dari satu routing protocol ke protocol lainnya.
*   **Validasi:** Pengujian dilakukan dengan memeriksa routing table dan memastikan jaringan yang berasal dari routing protocol berbeda dapat dipelajari oleh router pada domain lainnya.
*   **Arsitektur Topologi:**

![Topology 2](Topology%202.png)

---

### Proyek 3: Skenario Recursive Static Routing Jarak Jauh

*   **Wilayah Folder:** `03-recursive-static-routing/`
*   **Teknologi Inti:** Cisco IOSv, Recursive Static Routing, Next-Hop Resolution, VLSM.
*   **Analisis Masalah:** Lab ini digunakan untuk memahami mekanisme **recursive route lookup**, ketika alamat next-hop pada static route tidak berada pada jaringan yang terhubung langsung. Router harus melakukan pencarian tambahan pada routing table untuk menentukan interface yang digunakan menuju next-hop tersebut.
*   **Validasi:** Pengujian dilakukan dengan memeriksa routing table dan melakukan konektivitas menuju jaringan tujuan untuk memastikan proses recursive lookup berjalan sesuai rancangan.
*   **Arsitektur Topologi:**

![Topology 3](Topology%203.png)

---

### Proyek 4: Implementasi Arsitektur OSPF Area 0

*   **Wilayah Folder:** `04-enterprise-ospf-architecture/`
*   **Teknologi Inti:** Cisco IOL, OSPF Area 0, Neighbor Adjacency, VLSM, Point-to-Point Link.
*   **Analisis Masalah:** Lab ini berfokus pada implementasi jaringan OSPF menggunakan **Area 0** sebagai backbone area. Tiga router Cisco IOL dikonfigurasi untuk membentuk OSPF neighbor adjacency dan bertukar informasi routing antar jaringan.
*   **Validasi:** Status adjacency diverifikasi menggunakan status neighbor hingga mencapai kondisi **FULL**, kemudian routing table diperiksa untuk memastikan jaringan remote berhasil dipelajari melalui OSPF.
*   **Arsitektur Topologi:**

![Topology 4](Topology%204.png)

---

### Proyek 5: Implementasi External BGP Multi-AS

*   **Wilayah Folder:** `05-bgp-autonomous-system/`
*   **Teknologi Inti:** Cisco IOL, eBGP, Autonomous System, TCP Port 179, AS-Path.
*   **Analisis Masalah:** Lab ini digunakan untuk memahami konsep **interdomain routing** menggunakan External BGP. Router dari Autonomous System yang berbeda dikonfigurasi untuk membentuk eBGP peering dan bertukar informasi jaringan.
*   **Validasi:** Status BGP peer diperiksa hingga mencapai kondisi **Established**. AS-Path juga diamati untuk memahami bagaimana BGP membawa informasi Autonomous System yang dilewati sebuah route serta membantu mencegah routing loop.
*   **Arsitektur Topologi:**

![Topology 5](Topology%205.png)

---

### Proyek 6: Implementasi Dinamis RIPv2 dengan VLSM

*   **Wilayah Folder:** `06-dynamic-routing-ripv2/`
*   **Teknologi Inti:** Cisco vIOS L3, RIPv2, VLSM, No Auto-Summary, Split Horizon, Hop Count.
*   **Analisis Masalah:** Lab ini digunakan untuk memahami kemampuan **RIPv2** dalam mendistribusikan informasi routing pada jaringan dengan subnet mask yang berbeda menggunakan VLSM. Konfigurasi `no auto-summary` digunakan agar informasi subnet tetap dipertahankan dan tidak diringkas berdasarkan classful network boundary.
*   **Validasi:** Routing table dan konektivitas antar jaringan diperiksa untuk memastikan subnet dengan prefix yang berbeda dapat dipelajari dan dijangkau melalui RIPv2.
*   **Arsitektur Topologi:**

![Topology 6](Topology%206.png)

---

## Kapabilitas Teknis dan Spesifikasi Sistem Simulator

*   **Network Operating Systems:** FortiOS, MikroTik RouterOS, Cisco IOSv, Cisco IOL.
*   **Core Routing Protocols:** OSPFv2, EIGRP, eBGP, RIPv2, Static Routing, Recursive Static Routing.
*   **Routing Technologies:** Route Redistribution, VLSM, Next-Hop Resolution, Multi-AS Routing.
*   **Security & Network Technologies:** GRE Tunnel, Firewall Policy, IPsec Architecture, DHCP.
*   **Simulator Environments:** PNetLab, Cisco Packet Tracer.
*   **Management Tools:** Winbox, Cisco CLI, FortiGate GUI.

---

## Catatan Portofolio

Seluruh proyek pada repositori ini merupakan **lab simulasi dan eksperimen pembelajaran**, bukan implementasi jaringan production.

Fokus utama portofolio adalah menunjukkan proses **perancangan topologi, konfigurasi perangkat, validasi konektivitas, troubleshooting, serta pemahaman terhadap perilaku routing protocol** dalam lingkungan simulasi.

### Repository Structure

```text
Network-Portofolio/
│
├── 01-multi-vendor-secure-sdwan/
├── 02-multi-protocol-route-redistribution/
├── 03-recursive-static-routing/
├── 04-enterprise-ospf-architecture/
├── 05-bgp-autonomous-system/
├── 06-dynamic-routing-ripv2/
│
├── Topology 1.png
├── Topology 2.png
├── Topology 3.png
├── Topology 4.png
├── Topology 5.png
└── Topology 6.png
