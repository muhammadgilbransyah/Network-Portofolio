Network Portfolio — Muhammad Gibran Syah

Portofolio Lab Jaringan Multi-Vendor dan Protokol Routing Dinamis Cisco

Implementasi Secure SD-WAN, Route Redistribution, dan Routing Cisco (OSPF, BGP, RIPv2)

Selamat datang di repositori portofolio teknik jaringan saya. Repository ini mendokumentasikan serangkaian hands-on lab menggunakan PNetLab, dengan fokus pada routing dinamis, route redistribution, recursive static routing, serta implementasi jaringan multi-vendor.

Lab dalam repository ini dibuat sebagai bagian dari proses pembelajaran dan eksplorasi teknis untuk memahami cara kerja berbagai protokol routing, pertukaran informasi antar-routing domain, serta konektivitas antar-perangkat dari vendor yang berbeda dalam lingkungan simulasi.

---

Ringkasan Portfolio

Proyek 1 — Multi-Vendor Secure SD-WAN

Wilayah Folder: "01-multi-vendor-secure-sdwan/"

Teknologi Inti: Fortinet FortiOS, MikroTik RouterOS, Cisco IOS, GRE Tunnel, Firewall Policy

Analisis Masalah

Proyek ini mengeksplorasi konektivitas antar-site menggunakan perangkat dari beberapa vendor dalam lingkungan simulasi PNetLab.

Pada tahap awal, proyek dirancang menggunakan IPsec VPN. Namun, terdapat kendala kompatibilitas pada image FortiGate trial yang digunakan, di mana proposal Phase 1 yang tersedia terbatas pada algoritma DES, sedangkan MikroTik RouterOS v7 yang digunakan sudah tidak mendukung DES.

Setelah menganalisis kendala tersebut, pendekatan tunneling dialihkan menggunakan GRE Tunnel untuk membangun konektivitas antar-site.

Arsitektur Topologi

"Topology 1" (Topology%201.png)

---

Proyek 2 — Multi-Protocol Dynamic Route Redistribution

Wilayah Folder: "02-multi-protocol-route-redistribution/"

Teknologi Inti: Cisco IOSv, OSPF, EIGRP, eBGP, Route Redistribution

Analisis Masalah

Lab ini mensimulasikan kondisi ketika beberapa routing protocol digunakan dalam satu lingkungan jaringan dan membutuhkan pertukaran informasi routing.

Fokus utama berada pada implementasi mutual route redistribution antara OSPF, EIGRP, dan eBGP, serta pemahaman terhadap perbedaan karakteristik routing protocol ketika informasi route dipertukarkan antar-domain.

Arsitektur Topologi

"Topology 2" (Topology%202.png)

---

Proyek 3 — Skenario Recursive Static Routing Jarak Jauh

Wilayah Folder: "03-recursive-static-routing/"

Teknologi Inti: Cisco IOSv, Recursive Static Routing, Next-Hop, RIB Lookup, VLSM

Analisis Masalah

Lab ini dibuat untuk memahami perilaku router ketika sebuah static route menggunakan alamat next-hop yang tidak terhubung secara langsung.

Router perlu melakukan pencarian tambahan pada routing table untuk menentukan bagaimana mencapai alamat next-hop tersebut sebelum menentukan interface keluar yang digunakan untuk meneruskan paket.

Lab ini digunakan untuk mengeksplorasi konsep recursive route lookup pada lingkungan jaringan dengan beberapa segment.

Arsitektur Topologi

"Topology 3" (Topology%203.png)

---

Proyek 4 — Implementasi Arsitektur OSPF Area 0

Wilayah Folder: "04-enterprise-ospf-architecture/"

Teknologi Inti: Cisco IOL L3, OSPF Area 0, Neighbor Adjacency, VLSM

Analisis Masalah

Lab ini digunakan untuk memahami proses pembentukan OSPF neighbor adjacency pada backbone Area 0.

Fokus implementasi meliputi konfigurasi IP addressing dan wildcard mask, pembentukan hubungan neighbor, serta validasi status adjacency hingga mencapai FULL state.

Arsitektur Topologi

"Topology 4" (Topology%204.png)

---

Proyek 5 — Eksplorasi External BGP Multi-AS

Wilayah Folder: "05-bgp-autonomous-system/"

Teknologi Inti: Cisco IOL L3, eBGP, Multi-AS, AS-Path, TCP 179

Analisis Masalah

Lab ini mengeksplorasi pembentukan eBGP peering antar beberapa Autonomous System.

Fokus utama berada pada proses pembentukan sesi BGP hingga mencapai status Established, serta pemahaman terhadap atribut AS-Path yang digunakan dalam proses pemilihan jalur dan membantu mencegah routing loop antar-AS.

Arsitektur Topologi

"Topology 5" (Topology%205.png)

---

Proyek 6 — Implementasi Dinamis RIPv2 dengan Classless Subnetting

Wilayah Folder: "06-dynamic-routing-ripv2/"

Teknologi Inti: Cisco vIOS L3, RIPv2, VLSM, No Auto-Summary, Split Horizon

Analisis Masalah

Lab ini dirancang untuk memahami penggunaan RIPv2 pada jaringan dengan VLSM serta bagaimana informasi subnet dapat dipertukarkan secara classless.

Fokus utama berada pada penggunaan "no auto-summary" untuk mencegah proses automatic summarization pada batas major network sehingga informasi subnet dapat dipertahankan sesuai konfigurasi jaringan.

Arsitektur Topologi

"Topology 6" (Topology%206.png)

---

Kapabilitas Teknis

Routing & Switching

- OSPFv2
- OSPF Multi-Area
- EIGRP
- eBGP / iBGP
- RIPv2
- Static & Recursive Static Routing
- Route Redistribution
- VLAN & Inter-VLAN Routing
- ACL
- DHCP
- VLSM & Subnetting

Multi-Vendor Networking

- Cisco IOS / IOSv / IOL
- MikroTik RouterOS
- FortiGate / FortiOS

Network Security

- GRE Tunnel
- Basic IPsec VPN Architecture
- Firewall Policy

Tools & Simulator

- PNetLab
- Cisco Packet Tracer
- Winbox
- FortiGate GUI
- Cisco CLI
- PuTTY
- WinSCP

---

Environment

Seluruh project dalam repository ini dibuat menggunakan lingkungan simulasi PNetLab dan digunakan sebagai sarana praktik untuk memperdalam pemahaman terhadap konsep jaringan.

Beberapa lab merupakan pengembangan dari materi pelatihan, sementara beberapa lainnya dieksplorasi secara mandiri untuk memperdalam pemahaman teknis.

Repository ini akan terus dikembangkan seiring bertambahnya pengalaman dan pembelajaran di bidang Network Engineering, Linux, Network Security, dan SOC.

---

Author

Muhammad Gibran Syah

Fresh Graduate — Teknik Komputer dan Jaringan
Bekasi, Indonesia
