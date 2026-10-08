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

*   **Wilayah Folder:** `04-enterprise-ospf
