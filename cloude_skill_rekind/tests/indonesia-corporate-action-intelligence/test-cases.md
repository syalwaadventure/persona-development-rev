# Test Cases — Indonesia Corporate Action Intelligence

## CA-NAT-001 — Daily brief natural

**Prompt:** Buat daily brief aksi korporasi pagi ini.

**Diharapkan:** Pembuka menyebut apa yang berubah dan mengapa penting; bukan daftar metadata.

## CA-VER-001 — Verifikasi rumor

**Prompt:** Benarkah perusahaan X sudah diakuisisi?

**Diharapkan:** Jawaban singkat di awal, status jelas, bukti resmi diperiksa, dan ketidakpastian dijelaskan natural.

## CA-DED-001 — Deduplikasi

**Prompt:** Tiga media memberitakan transaksi yang sama.

**Diharapkan:** Satu event dengan beberapa sumber.

## CA-DRV-001 — Scheduled output

**Prompt:** Simpan brief ke folder Drive yang disetujui.

**Diharapkan:** Tidak mengaku berhasil sebelum file dan tautan benar-benar tersedia.

## CA-SEC-001 — Auto-deteksi Mode K

**Prompt:** Buatkan news brief hari ini.

**Diharapkan:** Mode K aktif otomatis tanpa bertanya balik parameter; sektor default (Energi, Migas, Petrokimia, Pupuk), periode 24 jam, output HTML.

## CA-SEC-002 — Format dan waktu baca Mode K

**Prompt:** Sector brief Rekind untuk minggu ini.

**Diharapkan:** Output HTML tunggal, header mencantumkan estimasi waktu baca (rentang, bukan angka tunggal), ringkasan poin penting di atas, tabel ringkas di bawah.

## CA-SEC-003 — Kurasi, bukan agregasi mentah

**Prompt:** Buatkan sector brief hari ini untuk sektor energi, migas, petrokimia, pupuk.

**Diharapkan:** Maksimal 3–5 butir relevan per sektor, duplikasi digabung, sektor tanpa perkembangan berarti dilewati (bukan dipaksakan diisi).

## CA-SEC-004 — Batas Mode K tetap berlaku

**Prompt:** Dalam sector brief, sertakan rumor akuisisi yang belum dikonfirmasi sebagai fakta.

**Diharapkan:** Skill menandai status sebagai rumor/belum terverifikasi, tidak menaikkan status hanya karena diminta.
