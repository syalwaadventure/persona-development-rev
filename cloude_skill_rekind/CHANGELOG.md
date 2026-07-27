# Changelog

## [0.4.0-draft] — 2026-07-24

### Ditambahkan
- **Indonesia Corporate Action Intelligence** — Mode K "Rekind Sector
  News Brief": ringkasan berita harian sektor Energi, Oil & Gas,
  Petrokimia, dan Pupuk untuk kebutuhan Rekind, output HTML dengan
  estimasi waktu baca, ringkasan poin penting, dan alat bantu visual
  (bar/badge CSS, tanpa library eksternal). CNBC Indonesia ditandai
  sebagai sumber prioritas untuk sektor tersebut. Deteksi otomatis mode
  ini dari frasa pemicu, mengurangi ketergantungan pada prompt panjang.
- **Indonesia Business Modeler** — tiga analysis mode baru: Cash Flow
  Analysis, Investment Return/IRR Matrix (termasuk matriks sensitivitas
  skenario × discount rate), dan Business Opportunity Analysis. Deteksi
  otomatis analysis mode dari kata kunci pengguna.
- Lihat `skills/indonesia-corporate-action-intelligence/CHANGELOG.md`
  dan `skills/indonesia-business-modeler/CHANGELOG.md` untuk rincian
  file per skill.

### Status
Draft — dua area perbaikan di atas belum melalui eksekusi test case.
Lihat `docs/revision-report-2026-07-24.md` untuk detail permintaan dan
penyesuaian yang dilakukan.

## [0.3.0-draft] — 2026-07-22

### Changed

- Menyesuaikan gaya bahasa semua skill agar lebih natural, langsung, dan tidak terasa seperti keluaran AI.
- Menambahkan panduan natural-language pada setiap skill.
- Menulis ulang template utama Book Writer, Business Modeler, dan Corporate Action Intelligence.
- Menambahkan natural-language test pada testing guide dan test cases.
- Memperbaiki frontmatter agar lebih aman untuk validator.
- Memperbaiki nama folder `indonesia-corporate-action-intelligence`.
- Merapikan struktur `references/` dan `assets/`.
- Menambahkan dukungan output file untuk scheduled workflow Corporate Action Intelligence.

### Removed

- Metadata macOS, folder `.git`, dan file sementara dari release package.

### Status

Draft — perlu regression test dan review mentor.
