# Portofolio Lab Jaringan Multi-Vendor dan Protokol Routing Dinamis Cisco
### Implementasi Secure SD-WAN, Route Redistribution, dan Routing Cisco (OSPF, BGP, RIPv2)


Selamat datang di repositori portofolio teknik jaringan saya. Repositori ini mendokumentasikan serangkaian implementasi laboratorium taktis (hands-on labs) skala hibrida dan enterprise menggunakan simulator PNetLab. Seluruh proyek di bawah ini dirancang untuk menyelesaikan tantangan industri nyata terkait interoperabilitas multi-vendor, optimalisasi jalur penerusan data (forwarding), kebijakan interdomain routing, serta mitigasi risiko keamanan perimeter.

---

## Ringkasan Eksekutif Repositori Portofolio

### Proyek 1: Multi-Vendor Hybrid Secure Networking Lab
*   **Wilayah Folder:** `01-multi-vendor-secure-sdwan/`
*   **Teknologi Inti:** Fortinet FortiOS, MikroTik RouterOS, Cisco IOS, GRE Enkapsulasi, IPsec VPN Handshake, Business Continuity.
*   **Analisis Masalah:** Proyek ini menonjolkan kemampuan analisis akar masalah (Root Cause Analysis) saat menangani kegagalan handshake IPsec VPN akibat restriksi ekspor kriptografi pada FortiGate Trial (Trial non-LENC) yang mengunci proposal Phase 1 pada algoritma DES, sementara kernel MikroTik v7 telah menghapus total biner DES demi standar keamanan modern. Isu ini diselesaikan secara taktis melalui pengalihan jalur menggunakan GRE Tunnel guna menjaga kelangsungan operasional data antar-site.
*   **Arsitektur Topologi:**
    ![Topology 1](Topology%201.png)

---

### Proyek 2: Multi-Protocol Dynamic Route Redistribution Lab
*   **Wilayah Folder:** `02-multi-protocol-route-redistribution/`
*   **Teknologi Inti:** Cisco IOSv, Multiprotocol Mutual Redistribution, Seed Metrics Rekayasa, OSPF Area 0, EIGRP DUAL, eBGP Peer.
*   **Analisis Masalah:** Simulasi skenario penggabungan dua infrastruktur korporasi yang berbeda (merger) sehingga menuntut pertukaran informasi rute hibrida. Fokus pada rekayasa metrik benih (seed metrics) pada EIGRP (Bandwidth, Delay, Reliability, Load, MTU) serta optimalisasi argumen subnets pada OSPF Link-State Database (LSA Type 5) untuk mencegah terjadinya routing loops dan sub-optimal routing lintas batas administratif Autonomous System.
*   **Arsitektur Topologi:**
    ![Topology 2](Topology%202.png)

---

### Proyek 3: Skenario Recursive Static Routing Jarak Jauh
*   **Wilayah Folder:** `03-recursive-static-routing/`
*   **Teknologi Inti:** Cisco IOSv, Recursive Route Forwarding, Double RIB Lookup, Classless VLSM Segment, Static-to-Dynamic Gateway.
*   **Analisis Masalah:** Implementasi dan analisis perilaku pencarian rute ganda (double lookup) di dalam tabel Routing Information Base (RIB) router penengah. Paket data tujuan jarak jauh dipetakan melewati IP next-hop yang tidak terhubung langsung secara fisik, memaksa router melakukan pencarian rekursif untuk menentukan exit interface yang valid. Skenario memisahkan segmen dinamis (DHCP) dan segmen statis untuk menguji efisiensi performa tabel routing.
*   **Arsitektur Topologi:**
    ![Topology 3](Topology%203.png)

---

### Proyek 4: Implementasi Arsitektur Enterprise OSPF Area 0
*   **Wilayah Folder:** `04-enterprise-ospf-architecture/`
*   **Teknologi Inti:** Cisco IOL L3, OSPF Neighbor Adjacency, Multicast Address 224.0.0.5, VLSM Classless Distribution, FULL State Status.
*   **Analisis Masalah:** Perancangan backbone Area 0 skala korporat menggunakan tiga router Cisco IOL yang terhubung via tautan Point-to-Point /30. Validasi teknis dipusatkan pada ketepatan konfigurasi Wildcard Mask pada proses Hello Packet untuk mengawal siklus pembentukan adjacency (fase Init, Two-Way, hingga FULL/DR dan FULL/BDR State) guna menjamin konvergensi link-state global yang stabil tanpa tumpang tindih rute.
*   **Arsitektur Topologi:**
    ![Topology 4](Topology%204.png)

---

### Proyek 5: Implementasi Eksplorasi External BGP (eBGP) Multi-AS
*   **Wilayah Folder:** `05-bgp-autonomous-system/`
*   **Teknologi Inti:** Cisco IOL L3, eBGP Peer Session, Port TCP 179 handshakes, Path Attributes, Loop Prevention, AS-Path Attribute.
*   **Analisis Masalah:** Simulasi kebijakan interdomain routing skala Service Provider yang menghubungkan jaringan Enterprise Edge (AS 300) menuju dua penyedia jalur transit berbeda (AS 100 dan AS 200). Fokus pada deklarasi eBGP peer manual, pemantauan status jabat tangan BGP Established, serta analisis mekanisme pencegahan loop antar-domain memanfaatkan atribut jalur AS-Path.
*   **Arsitektur Topologi:**
    ![Topology 5](Topology%205.png)

---

### Proyek 6: Implementasi Dinamis RIPv2 dengan Optimasi Classless Subnetting
*   **Wilayah Folder:** `06-dynamic-routing-ripv2/`
*   **Teknologi Inti:** Cisco vIOS L3, RIPv2 Classless Protocol, No Auto-Summary Argument, Split Horizon, Hop-Count Metrics.
*   **Analisis Masalah:** Lab ini dirancang untuk mengevaluasi kapabilitas protokol routing RIPv2 dalam mendistribusikan informasi subnet mask bervariasi (VLSM). Fokus pada penanganan isu auto-summary bawaan RIP yang cenderung merangkum rute rincian menjadi rute kelas penuh (major network boundary). Masalah diselesaikan melalui instruksi `no auto-summary` untuk mencegah diskoneksi dan salah akumulasi rute pada perimeter luar jaringan internal.
*   **Arsitektur Topologi:**
    ![Topology 6](Topology%206.png)

---

## Kapabilitas Teknis dan Spesifikasi Sistem Simulator

*   **Vendor Network Operating Systems:** Fortinet FortiOS (v6.4), MikroTik RouterOS (v7), Cisco IOSv (L3/L2), Cisco IOL (L3/L2).
*   **Core Routing Protocols:** OSPFv2 Single-Area, EIGRP Enterprise, eBGP Multi-AS, RIPv2 Classless, Recursive Static Route.
*   **Security & Network Services:** GRE Enkapsulasi, IPsec VPN Architecture, Firewall Policy, DHCP Server Architecture, Classless VLSM/Subnetting Engineering.
*   **Simulator Environments:** PNetLab Emulator Infrastructure, Winbox Management, FortiGate GUI Dashboard, Cisco CLI Core Terminal.
