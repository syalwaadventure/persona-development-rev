# Changelog — Indonesia Corporate Action Intelligence

## [0.2.0-draft] — 2026-07-24

### Ditambahkan
- **Mode K — Rekind Sector News Brief**: ringkasan berita harian sektor
  Energi & Ketenagalistrikan, Migas (Oil & Gas), Petrokimia, dan
  Pupuk/Fertilizer, output HTML tunggal siap baca.
- `references/rekind-sector-brief-guide.md` — sektor default dan kata
  kunci pencarian, parameter default Mode K, cara menghitung estimasi
  waktu baca, prinsip kurasi/segmentasi, dan aturan alat bantu visual
  tanpa library eksternal.
- `assets/rekind-sector-news-brief-template.html` — template HTML tema
  gelap dengan header (judul, tanggal, estimasi waktu baca 6–8 menit),
  kotak ringkasan poin penting, bar jumlah berita per sektor, kartu
  berita per sektor dengan badge relevansi, dan tabel ringkas.
- Auto-deteksi Mode K dari frasa pemicu di Fase 1 (§4 `SKILL.md`),
  supaya skill bisa langsung menjalankan brief harian tanpa pengguna
  menuliskan parameter lengkap setiap kali.
- Perluasan cakupan terbatas (§2a) yang menjelaskan mengapa Mode K boleh
  memuat berita sektor umum, bukan hanya aksi korporasi, sambil tetap
  mempertahankan pemisahan fakta/rumor dan atribusi sumber.
- CNBC Indonesia ditandai sebagai sumber media prioritas untuk berita
  sektor energi, migas, petrokimia, dan pupuk (`references/source-guide.md`).

### Status
Masih **draft — siap diuji**. Mode K belum melalui eksekusi test case;
tambahkan skenario pengujian di
`tests/indonesia-corporate-action-intelligence/test-cases.md` sebelum
dipakai sebagai proses harian yang diandalkan.

## [0.1.0-draft] — 2026-07-22

Rilis awal skill, digabungkan ke dalam paket `cloude_skill_rekind` versi
0.3.0-draft.
