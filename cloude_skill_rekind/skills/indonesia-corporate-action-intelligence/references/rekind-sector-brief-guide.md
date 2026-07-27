# Rekind Sector News Brief — Panduan Mode K

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.

Panduan ini khusus untuk Mode K (§6a di `SKILL.md`). Dipakai pada Fase 1 (deteksi otomatis dan default), Fase 2 (strategi pencarian per sektor), dan Fase 8 (format output HTML).

---

## 1. Sektor default dan kata kunci pencarian

Empat sektor ini otomatis aktif setiap Mode K dijalankan, kecuali pengguna secara eksplisit meminta sektor lain atau mempersempit ke satu sektor saja.

| Sektor | Kata kunci pencarian inti | Contoh yang relevan untuk Rekind |
|---|---|---|
| Energi & Ketenagalistrikan | PLN, pembangkit, EBT, transisi energi, harga listrik, IPP | Proyek pembangkit, kebijakan tarif, EPC kelistrikan |
| Migas (Oil & Gas) | SKK Migas, Pertamina, hulu migas, kilang, LNG, LPG | Proyek kilang/LNG/LPG, kontrak EPC migas, harga minyak |
| Petrokimia | petrokimia, nafta, olefin, polimer, kawasan industri kimia | Proyek petrokimia baru, ekspansi kawasan industri |
| Pupuk / Fertilizer | Pupuk Indonesia, pupuk bersubsidi, urea, NPK, amonia | Kebijakan subsidi pupuk, proyek pabrik pupuk/amonia |

Susun kueri pendek (3–6 kata) per sektor, sertakan tahun berjalan, dan jangan menggabungkan dua sektor dalam satu kueri — mengikuti aturan umum di `references/source-guide.md` §3.

Bila pengguna menambahkan sektor lain di luar empat ini (misalnya konstruksi, infrastruktur), tambahkan sebagai sektor tambahan pada brief hari itu, jangan menolaknya — sektor default hanyalah baseline, bukan batas kaku.

---

## 2. Parameter default Mode K

Dipakai begitu Fase 1 mendeteksi Mode K (lihat pola pemicu di `SKILL.md` §4), tanpa perlu ditanyakan ke pengguna:

| Parameter | Default |
|---|---|
| Periode | 24 jam terakhir |
| Sektor | Energi & Ketenagalistrikan, Migas, Petrokimia, Pupuk |
| Sumber | Tier 1–2 di `references/source-guide.md`, dengan CNBC Indonesia, Kontan, Bisnis Indonesia, Katadata sebagai prioritas media sektor |
| Jumlah butir per sektor | Maksimal 3–5, hanya yang relevan dengan bisnis Rekind |
| Format output | HTML tunggal, `assets/rekind-sector-news-brief-template.html` |
| Bahasa | Indonesia profesional, natural |

Pengguna cukup bilang "buatkan news brief hari ini" atau "sector brief Rekind" — skill tidak perlu menanyakan periode, sektor, atau format setiap kali. Klarifikasi hanya untuk kasus di `SKILL.md` §4 (Auto-deteksi Mode K).

---

## 3. Estimasi waktu baca

Hitung dari perkiraan jumlah kata pada isi brief (di luar HTML/CSS), memakai kecepatan baca ~200 kata/menit untuk teks bahasa Indonesia profesional. Target isi brief adalah **1.200–1.600 kata**, yang secara alami menghasilkan estimasi 6–8 menit.

- Bila draf melebihi ~1.600 kata, pangkas butir berita yang relevansinya paling rendah dulu, bukan memotong semua bagian secara merata.
- Bila draf kurang dari ~1.200 kata (hari sepi berita), jangan dipaksakan mengisi — tampilkan waktu baca yang sesuai apa adanya (mis. "3–4 menit") dan sebutkan bahwa hari itu memang minim perkembangan material.
- Tampilkan angka waktu baca sebagai rentang (mis. "6–8 menit"), bukan angka tunggal yang terkesan presisi palsu.

---

## 4. Kurasi dan segmentasi

Prinsip pembeda Mode K dari sekadar agregasi berita:

1. **Saring dulu, baru tulis.** Buang berita yang tidak menyentuh salah satu dari empat sektor atau tidak punya keterkaitan jelas dengan bisnis Rekind (EPC, energi, migas, petrokimia, pupuk).
2. **Gabungkan duplikasi.** Bila beberapa portal memberitakan isu yang sama, jadikan satu butir dengan beberapa sumber, mengikuti prinsip deduplication di `references/verification-and-dedup.md`.
3. **Beri tag relevansi.** Setiap butir diberi label LOW/MEDIUM/HIGH untuk seberapa relevan terhadap operasi atau lini bisnis Rekind — bukan sekadar seberapa besar beritanya secara umum.
4. **Pisahkan fakta dan analisis.** Sebutkan darimana berita berasal, lalu bila ada catatan dampak terhadap Rekind, tandai jelas sebagai "Catatan Analisis" — bukan seolah-olah bagian dari berita aslinya.
5. **Rumor tetap rumor.** Bila sebuah item masih berupa rencana/wacana yang belum dikonfirmasi resmi, sebutkan statusnya apa adanya (lihat `references/event-status-guide.md`).
6. **Jangan memaksakan empat sektor tiap hari.** Bila salah satu sektor tidak ada perkembangan berarti, lewati sektor itu — jangan mengisi dengan berita generik supaya tampak lengkap.

---

## 5. Alat bantu visual (tanpa library eksternal)

Karena output adalah satu file HTML mandiri, semua visual dibuat dengan CSS/SVG murni:

- **Bar jumlah berita per sektor** — `<div>` dengan lebar proporsional (`width: %`) sebagai pengganti bar chart.
- **Badge relevansi** — warna berbeda untuk LOW/MEDIUM/HIGH (lihat variabel warna di template).
- **Kotak ringkasan poin penting** — kartu di bagian atas, bukan daftar bullet biasa, supaya pembaca cepat menangkap inti sebelum membaca detail.

Jangan memuat chart.js, d3, atau library grafik lain dari CDN eksternal — tujuannya file tetap bisa dibuka offline dan cepat dimuat.

---

## 6. Yang tetap tidak berubah dari mode lain

- Tidak boleh mengarang nilai, tanggal, nama pihak, atau status.
- Tidak boleh menyalin artikel secara penuh — parafrase, kutipan sangat terbatas dengan atribusi.
- Tidak boleh memberi rekomendasi investasi.
- Sumber yang tidak dapat diakses dinyatakan apa adanya, mengikuti `references/source-guide.md` §5.
