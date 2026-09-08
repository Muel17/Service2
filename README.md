# 🌸 Bloom — Habit & Goal Tracker (Clone)

Sebuah clone lengkap dan fungsional dari aplikasi web **Bloom — Habit & Goal Tracker** (`https://bloom-habit-barenglisa.vercel.app/`).

## 🚀 Cara Menjalankan Secara Lokal

Aplikasi ini dapat dijalankan menggunakan Node.js bawaan tanpa perlu menginstall package eksternal apapun:

```bash
npm start
# atau
node server.js
```

Akses di browser Anda melalui:
👉 **`http://localhost:3000`**

---

## 🔐 Kredensial & Akses

1. **Kode Akses Awal**: `BLOOM2026`
2. **Email Akun**: `itsidkwhy12@gmail.com`
3. **PIN**: `1234`

---

## 🌟 Fitur Utama

- **Otentikasi & Keamanan Klien**:
  - Layar kode akses (`BLOOM2026`) untuk proteksi awal.
  - Keypad PIN numerik 4-digit interaktif dengan mode Setup (pembuatan PIN + konfirmasi) dan Login.
  - Enkripsi client-side menggunakan derivasi kunci **PBKDF2 SHA-256** (100.000 iterasi) + **AES-GCM 256-bit**.
  - Sinkronisasi awan via Firebase Auth & Cloud Firestore dengan fallback penyimpanan lokal terenkripsi di `localStorage`.
  - Perlindungan kebocoran data antar-akun pada perangkat bersama.
  - Tombol cepat **Kunci Akun (🔒)** di sidebar dan topbar.

- **🗓️ Periode (Grid Habit Harian)**:
  - Pemilihan tahun dan bulan secara dinamis (multi-tahun, bukan sekadar tahun statis).
  - Setup habit hingga 10 slot habit dengan input real-time debounce dan pembukaan slot progresif.
  - Grid tabel ganda (kolom judul habit tetap / frozen column, dan tabel tanggal horizontal-scroll).
  - Checkbox harian per tanggal dengan perhitungan otomatis:
    - **Total**: Jumlah hari berhasil dicentang.
    - **% Comp.**: Persentase kelulusan habit terhadap jumlah hari dalam bulan.
    - **Rank**: Peringkat antar habit dengan tie-breaker otomatis berdasarkan streak beruntun terpanjang.
  - **🏆 Beat the Day**: Persentase pemenuhan seluruh habit pada hari tersebut.
  - **🎭 Mood Harian**: Selector 6 mood harian (😔 Empty, 🤯 Stressful, 😫 Drained, 😌 Fine, 🥰 Happy, 🏆 Win the day).
  - **🌱 Pertumbuhan Tanaman Habit**: Visualisasi ikon tanaman SVG interaktif per minggu (Minggu 1 s/d Minggu 5) yang berevolusi sesuai konsistensi:
    - `0–19%`: Benih
    - `20–39%`: Tunas
    - `40–59%`: Berdaun
    - `60–79%`: Berbunga
    - `80–100%`: Mekar
  - **📌 Weekly Trend**: Bar chart SVG ringkas yang merefleksikan rata-rata mingguan.
  - **🗓️ Tombol Hari Ini**: Lompat cepat ke tanggal hari ini atau kembali ke awal bulan.

- **📊 Analytics**:
  - Filter tahun dan bulan untuk melihat analitik periode manapun.
  - 5 Kartu KPI Statistik Keseluruhan:
    - Total Completed
    - % Completed
    - Total Hari Beat the Day
    - Rata-rata Beat the Day
    - Mood Dominan
  - Distribusi Mood: Persentase sebaran mood yang tercatat.
  - Top 3 Habit bulan terpilih dengan ranking badge.
  - Trend % Complete: Area chart harian halus (smooth Catmull-Rom spline to Bezier) dengan skala 0–100%.
  - Recap bulan ini ✨: Narasi pintar 4-slot otomatis yang merangkum pencapaian habit dan mood.

- **📖 Panduan (Onboarding)**:
  - Tata cara penggunaan 7 langkah.
  - Penjelasan metrik dan simbol.
  - Keterangan tingkat pertumbuhan tanaman.
  - Edukasi keamanan data dan enkripsi email + PIN.

- **🎨 Desain & Responsivitas**:
  - Palet warna pastel yang nyaman dilihat (`--lavender`, `--mint`, `--peach`, `--pink`, `--yellow`, `--gold`, `--ink`).
  - Layout dual-mode:
    - Desktop (≥900px): Sidebar vertikal dengan stepper tahun, daftar bulan, navigasi, dan tombol kunci.
    - Mobile (<900px): Sticky topbar dengan header brand, navigasi pill, dan stepper tahun + dropdown bulan.
