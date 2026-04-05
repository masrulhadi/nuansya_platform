# NUANSYA — Intelligence API Bridge for ZISWAF Ecosystem

> **Menjembatani operasional ZISWAF tingkat desa dengan ekosistem nasional melalui analitik berbasis AI dan Single Source of Truth.**

[![Status](https://img.shields.io/badge/Status-High--Fidelity%20Mockup-blue)](.)
[![Platform](https://img.shields.io/badge/Platform-Mobile%20%7C%20Web-green)](.)
[![License](https://img.shields.io/badge/License-MIT-lightgrey)](.)
[![Institution](https://img.shields.io/badge/Institution-UIN%20Ar--Raniry-teal)](.)

---

## 📋 Daftar Isi

- [Tentang Proyek](#-tentang-proyek)
- [Latar Belakang Masalah](#-latar-belakang-masalah)
- [Solusi](#-solusi)
- [Arsitektur Sistem](#-arsitektur-sistem)
- [Teknologi](#-teknologi)
- [Algoritma & AI](#-algoritma--ai)
- [Alur Sistem](#-alur-sistem)
- [Dampak yang Diharapkan](#-dampak-yang-diharapkan)
- [Roadmap Pengembangan](#-roadmap-pengembangan)
- [Model Bisnis](#-model-bisnis)
- [Tim](#-tim)
- [Referensi](#-referensi)

---

## 🌟 Tentang Proyek

**NUANSYA** adalah *Intelligence API Bridge* yang dirancang untuk mengintegrasikan data operasional ZISWAF (Zakat, Infak, Sedekah, dan Wakaf) di tingkat desa dengan sistem ekosistem nasional — utamanya **SiMBA** (Sistem Informasi Manajemen BAZNAS) dan **SiWAK** (Sistem Informasi Wakaf).

Proyek ini dikembangkan sebagai respons terhadap fragmentasi data ZISWAF yang menyebabkan potensi ekonomi umat tidak optimal, dengan realisasi zakat nasional baru mencapai **12% dari total potensi Rp327 triliun** (BAZNAS, 2023).

| Atribut | Detail |
|---|---|
| Nama Proyek | NUANSYA |
| Tim | Nuansya Team |
| Institusi | Universitas Islam Negeri Ar-Raniry |
| Status | High-Fidelity Mockup |
| Kompetisi | Hackathon Nasional BI/OJK — Penguatan Ketahanan dan Inovasi Keuangan |
| Sub-tema | Digitalisasi Keuangan Syariah — Analitik ZISWAF |

---

## 🔍 Latar Belakang Masalah

Ekosistem ZISWAF Indonesia menghadapi **diskoneksi fungsional** antara operasional pendataan di desa dengan sistem nasional. Meskipun infrastruktur digital tersedia, alur data dari lapangan masih terperangkap dalam pencatatan manual dan silo data.

Fragmentasi ini mengakibatkan tiga kegagalan spesifik:

### 1. Inefisiensi Interoperabilitas & Bantuan Ganda
Ketiadaan jembatan data *real-time* menyebabkan mustahik dapat menerima dana dari berbagai lembaga secara tidak terdeteksi, sementara warga lain justru terlewatkan.

### 2. Subjektivitas Penilaian Mustahik
Penentuan kelayakan di desa masih mengandalkan intuisi amil tanpa parameter objektif berbasis **Had Kifayah**, sehingga distribusi rentan terhadap bias personal.

### 3. Absennya Jejak Audit Mikro
Ketiadaan audit digital di tingkat operasional memutus rantai transparansi bagi muzakki, mengikis kepercayaan publik terhadap lembaga ZISWAF.

### Data & Bukti

| Indikator | Data |
|---|---|
| Realisasi zakat nasional | Rp41 triliun / tahun |
| Potensi zakat nasional | Rp327 triliun / tahun |
| Gap realisasi | **~88% belum terealisasi** |
| Potensi kas wakaf | Rp180 triliun |
| Aset tanah wakaf tersertifikasi | 42% dari 900 ribu aset |

> *Observasi lapangan di Gampong Ateuk Jawoe, Aceh, mengonfirmasi bahwa pencatatan ZIS masih dilakukan secara manual sehingga data operasional terputus dari ekosistem nasional.*

---

## 💡 Solusi

NUANSYA hadir sebagai lapisan penghubung (*intelligence layer*) yang menjembatani operasional desa dengan sistem nasional melalui **3 pilar inovasi terintegrasi**:

### Pilar 1 — Identitas Digital Terpadu
Setiap penerima manfaat diberikan **Unique ID** berbasis kriptografi (SHA-256 + Salt) untuk mendeteksi dan mencegah bantuan ganda lintas lembaga secara otomatis.

### Pilar 2 — Sistem Penilaian Objektif Berbasis AI
Implementasi AI membantu amil menentukan kelayakan penerima berdasarkan parameter **Had Kifayah** yang terukur, menggantikan penilaian subjektif dengan klasifikasi berbasis data.

### Pilar 3 — Otomasi Laporan Keuangan
Transformasi pencatatan manual menjadi laporan standar **PSAK 109/409** yang tersinkronisasi otomatis ke sistem nasional melalui API.

---

## 🏗 Arsitektur Sistem

```
┌─────────────────────────────────────────────────────────────┐
│                    NUANSYA ECOSYSTEM                        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐  │
│  │  Mobile App  │    │  Web Dashboard│   │  API Bridge  │  │
│  │  (Flutter)   │    │  (React.js)  │    │  (FastAPI)   │  │
│  │  Amil Desa   │    │  Institusi   │    │              │  │
│  └──────┬───────┘    └──────┬───────┘    └──────┬───────┘  │
│         │                  │                    │           │
│         └──────────────────┴────────────────────┘           │
│                            │                                │
│                   ┌────────▼────────┐                       │
│                   │   PostgreSQL    │                       │
│                   │   + Cloud AI    │                       │
│                   │   Analytics     │                       │
│                   └────────┬────────┘                       │
│                            │                                │
├────────────────────────────┼────────────────────────────────┤
│         NATIONAL ECOSYSTEM │                                │
│  ┌──────────────┐  ┌───────▼──────┐  ┌──────────────────┐  │
│  │    SiMBA     │  │    SiWAK     │  │  Data Kependuduk │  │
│  │   (BAZNAS)   │  │    (BWI)     │  │  an & Sosial     │  │
│  └──────────────┘  └──────────────┘  └──────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

### Komponen Utama

| Komponen | Teknologi | Fungsi |
|---|---|---|
| Mobile App | Flutter (offline-first) | Input data mustahik oleh amil lapangan |
| Web Dashboard | React.js | Monitoring distribusi & analitik untuk institusi |
| API Bridge | FastAPI | Interoperabilitas dengan sistem nasional |
| Database | PostgreSQL | Penyimpanan data ZISWAF yang scalable |
| Local Rule-Engine | Logika deterministik | Validasi Had Kifayah offline di perangkat |
| Cloud AI Analytics | Isolation Forest + Random Forest | Deteksi anomali & analitik prediktif |
| Automation Engine | Script otomasi | Standarisasi laporan PSAK 409 |

---

## 🛠 Teknologi

### Frontend
```
Flutter        — Mobile app lintas platform dengan kapabilitas offline-sync
React.js       — Dashboard web analitik untuk institusi
```

### Backend
```
FastAPI        — API ringan, cepat, dan mudah diintegrasikan dengan sistem eksternal
PostgreSQL     — Database relasional untuk integritas transaksi ZISWAF
```

### AI & Analytics
```
Isolation Forest     — Deteksi anomali bantuan ganda (cloud)
Random Forest        — Predictive analytics graduasi mustahik
Local Rule-Engine    — Klasifikasi Had Kifayah offline (on-device)
```

### Keamanan
```
SHA-256 + Salt       — Kriptografi Unique ID anonim
Enkripsi TLS         — Komunikasi data terenkripsi
Audit Trail          — Pencatatan setiap aktivitas bertimestamp
UU PDP No. 27/2022   — Kepatuhan regulasi perlindungan data pribadi
```

---

## 🤖 Algoritma & AI

### 1. Local Rule-Engine (On-Device)
Menggunakan logika deterministik berbasis parameter Had Kifayah BAZNAS untuk klasifikasi mustahik secara instan di perangkat tanpa memerlukan koneksi internet.

```
Input  : Profil demografi (pendapatan, tanggungan, kondisi hunian, pengeluaran)
Proses : Komparasi terhadap threshold Had Kifayah per wilayah
Output : Klasifikasi kelayakan mustahik (Eligible / Not Eligible / Borderline)
```

### 2. Isolation Forest (Cloud — Anomaly Detection)
Mendeteksi pola distribusi tidak wajar dan potensi bantuan ganda lintas lembaga secara proaktif.

```
Input  : Data transaksi ZISWAF dengan Unique ID
Proses : Identifikasi outlier pada pola distribusi
Output : Alert anomali + laporan potensi duplikasi
```

### 3. Random Forest Regressor (Cloud — Predictive Analytics)
Memproyeksi tren kemakmuran dan potensi **graduasi mustahik** berdasarkan riwayat bantuan (time-series).

```
Input  : Riwayat bantuan, data profil mustahik, data kontekstual wilayah
Proses : Pemodelan prediktif multi-variabel
Output : Proyeksi graduasi + rekomendasi distribusi adaptif
```

### Identitas Digital
```
Unique ID = SHA-256(data_identitas + salt_wilayah)
```
Menghasilkan identitas anonim yang unik, tidak dapat dibalik, namun tetap dapat dilacak lintas sistem.

---

## 🔄 Alur Sistem

```
INPUT
  │
  ├─ Amil menginput profil mustahik via Mobile App (Flutter)
  ├─ Transaksi masuk melalui: Amil / QRIS / Transfer Digital
  └─ Setiap entitas mendapatkan Unique ID otomatis (SHA-256)
  │
  ▼
PROSES
  │
  ├─ [LOCAL] Validasi Had Kifayah & IKB via Rule-Engine (offline)
  ├─ [LOCAL] Sinkronisasi ke server saat koneksi tersedia
  ├─ [CLOUD] Isolation Forest → Deteksi bantuan ganda & anomali
  ├─ [CLOUD] Pemetaan dana sesuai standar akuntansi syariah
  └─ [CLOUD] Random Forest → Proyeksi graduasi mustahik
  │
  ▼
OUTPUT
  │
  ├─ Laporan keuangan PSAK 109/409 otomatis
  ├─ Dashboard distribusi real-time untuk pengelola
  ├─ Alert anomali untuk tim compliance
  └─ Sinkronisasi ke SiMBA / SiWAK via API
```

---

## 📊 Dampak yang Diharapkan

### Level Amil (Operasional)
- Eliminasi rekap manual yang memakan waktu berhari-hari
- Penilaian mustahik yang objektif dan konsisten berbasis data

### Level Muzakki & Donatur
- Transparansi pelacakan dana end-to-end via Unique ID
- Peningkatan kepercayaan yang mendorong partisipasi melalui lembaga resmi

### Level Institusi (BAZNAS, BWI, Lembaga Amil)
- Basis data mikro mustahik yang valid dan terpadu
- Mitigasi bantuan ganda secara sistemik
- Otomasi audit berstandar PSAK 109/409

### Level Negara
- Instrumen fiskal strategis berbasis data untuk pengentasan kemiskinan
- Dukungan Asta Cita dan agenda Indonesia Emas 2045
- Peningkatan coverage realisasi dari 12% menuju target nasional

---

## 🗺 Roadmap Pengembangan

Pengembangan NUANSYA menggunakan pendekatan **Agile Scrum** dalam beberapa sprint iteratif:

```
Sprint 1 — Foundation
├─ Product backlog & desain arsitektur sistem
├─ Perancangan skema database PostgreSQL
└─ Wireframe aplikasi pendataan mustahik

Sprint 2 — Backend Core
├─ Pengembangan API FastAPI
├─ Sistem Manajemen Unique ID
└─ Struktur pencatatan transaksi ZISWAF

Sprint 3 — Frontend & Internal Testing
├─ Aplikasi mobile amil (Flutter)
├─ Dashboard web dasar (React.js)
└─ Pengujian integrasi internal

Sprint 4 — Pilot Deployment
├─ Deploy terbatas di 1–2 gampong
├─ Validasi alur operasional lapangan
└─ Pengujian kualitas data & UX

Sprint 5 — MVP Refinement
├─ Iterasi berbasis feedback lapangan
├─ Penyempurnaan fitur analitik AI
└─ Minimum Viable Product (MVP) final
```

**Target Jangka Pendek:** Implementasi di 3–4 desa / 1 kecamatan, validasi basis data mustahik, dan visualisasi distribusi yang akurat.

**Target Jangka Menengah:** Evaluasi efektivitas program, peningkatan presisi deteksi anomali, dan ekspansi analitik kemiskinan skala kabupaten/kota.

---

## 💼 Model Bisnis

| Elemen BMC | Detail |
|---|---|
| **Customer Segments** | Lembaga pengelola zakat/wakaf, pemerintah daerah, regulator, amil desa (operator) |
| **Value Proposition** | Integrasi data ZISWAF terpadu, validasi mustahik berbasis data, transparansi distribusi, analitik AI |
| **Channels** | Aplikasi mobile amil, dashboard web institusi, integrasi API nasional |
| **Customer Relationships** | Pendampingan implementasi, pelatihan amil, dukungan sistem berkelanjutan |
| **Revenue Streams** | Institutional subscription, layanan integrasi API, kemitraan program sosial-digital |
| **Key Resources** | Platform teknologi, model analitik, infrastruktur cloud, tim pengembang |
| **Key Activities** | Pengelolaan platform, analisis data, integrasi sistem, pengembangan fitur |
| **Key Partners** | BAZNAS, BWI, pemerintah daerah, lembaga filantropi, komunitas desa |
| **Cost Structure** | Infrastruktur cloud, pengembangan sistem, operasional teknis, pelatihan pengguna |

---

## 👥 Tim

**Nuansya Team** — Mahasiswa Teknologi Informasi UIN Ar-Raniry dengan latar belakang pendidikan pesantren, memberikan pemahaman langsung terhadap praktik ZISWAF di masyarakat.

| Nama | Peran |
|---|---|
| **Masrul Hadi** | Team Lead / System Design / Domain Research ZISWAF |
| **M Pasha** | Frontend Developer / UI-UX (Mobile App) |
| **M Ihsan** | Backend Developer / System Design |
| **Imam Al Khalish** | Data Analyst / Data Processing |

📧 Contact: simasrolhadi@gmail.com
📞 085362159603

---

## 📚 Referensi

- BAZNAS. (2023). *Outlook Zakat Indonesia 2023*. Pusat Kajian Strategis BAZNAS (PUSKAS BAZNAS).
- BWI. (2023). *Laporan Perkembangan Wakaf Nasional*. Badan Wakaf Indonesia.
- BAZNAS. (2022). *Statistik Zakat Nasional 2022*. BAZNAS RI.
- Ikatan Akuntan Indonesia. (2021). *PSAK 109: Akuntansi Zakat dan Infak/Sedekah*. IAI.
- AAOIFI. (2017). *Zakat Core Principles*. Accounting and Auditing Organization for Islamic Financial Institutions.
- Undang-Undang Nomor 27 Tahun 2022 tentang *Perlindungan Data Pribadi*. Republik Indonesia.
- Undang-Undang Nomor 23 Tahun 2011 tentang *Pengelolaan Zakat*. Republik Indonesia.

---

## ⚖️ Kepatuhan & Regulasi

Solusi NUANSYA dirancang dengan memperhatikan kerangka regulasi berikut:

- **UU PDP No. 27/2022** — Perlindungan data pribadi dan privasi warga
- **PSAK 109 & 409** — Standar akuntansi zakat, infak, sedekah, dan wakaf
- **Zakat Core Principles (ZCP)** — Prinsip tata kelola zakat internasional
- **UU No. 23/2011** — Pengelolaan zakat nasional

---

<div align="center">

**NUANSYA** — *Dari Data Desa, Untuk Keadilan Umat.*

Dikembangkan dengan ❤️ oleh Nuansya Team | UIN Ar-Raniry | 2025

</div>
