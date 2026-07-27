# IRR dan Cash Flow Guide

> **Catatan gaya:** Tulis hasil dengan bahasa yang langsung, natural, dan sesuai konteks. Gunakan struktur ini sebagai panduan, bukan formulir yang harus diisi secara kaku.

Panduan ini dipakai untuk dua analysis mode: **Cash Flow Analysis** (`assets/cash-flow-template.md`) dan **Investment Return / IRR Matrix** (`assets/irr-matrix-template.md`). Keduanya biasanya dipakai berurutan: arus kas dulu, baru IRR/NPV dihitung dari arus kas itu.

---

## 1. Kenapa Cash Flow Terpisah dari Profit Model

`references/profit-mechanism-guide.md` menjelaskan **profit** (accrual: revenue dikurangi biaya, termasuk item non-tunai seperti depresiasi). **Cash flow** menjelaskan **uang yang benar-benar masuk dan keluar**. Dua perusahaan dengan profit sama bisa punya posisi kas yang sangat berbeda karena piutang, utang, capex, atau pembayaran utang.

Jembatan dari profit ke kas:

```
Net Profit
+ Depresiasi & Amortisasi (item non-tunai)
− Kenaikan modal kerja (piutang, persediaan naik → kas keluar)
+ Penurunan modal kerja
= Arus Kas Operasi

Arus Kas Operasi
− Belanja modal (capex)
+ Penjualan aset
= Arus Kas Investasi (digabung ke atas untuk Free Cash Flow)

Free Cash Flow
± Penerbitan/pelunasan utang
± Penerbitan saham/dividen
= Arus Kas Pendanaan → Perubahan Kas Bersih
```

## 2. Struktur Tiga Bagian Arus Kas

| Bagian | Isi | Contoh pos |
|---|---|---|
| **Operasi** | Kas dari kegiatan usaha inti | Penerimaan dari pelanggan, pembayaran pemasok, gaji, pajak |
| **Investasi** | Kas untuk aset jangka panjang | Belanja modal (capex), akuisisi, penjualan aset |
| **Pendanaan** | Kas dari/ke pemilik modal dan kreditur | Pinjaman baru, pelunasan utang, dividen, penerbitan saham |

Setiap angka wajib dilabeli sesuai `references/source-and-confidence-guide.md`: **Verified financial fact** (dari laporan keuangan resmi/laporan arus kas), **Company statement**, **Agent estimate** (`AGENT INFERENCE`), atau **Information gap**.

## 3. IRR (Internal Rate of Return)

**Definisi:** tingkat diskonto yang membuat Net Present Value (NPV) dari serangkaian arus kas proyek sama dengan nol.

```
NPV = Σ [ CFₜ / (1 + r)ᵗ ]  untuk t = 0 sampai n
IRR = nilai r di mana NPV = 0
```

- `CF₀` biasanya negatif (investasi awal/capex).
- `CFₜ` untuk t = 1..n adalah arus kas bersih tahunan proyek (bukan profit akuntansi).
- IRR dibandingkan dengan **hurdle rate/cost of capital** perusahaan untuk menilai kelayakan: IRR > hurdle rate → secara teori layak; IRR < hurdle rate → tidak.

**Jangan menghitung IRR dari angka yang tidak disebutkan pengguna atau sumber.** Bila arus kas proyeksi belum tersedia, nyatakan sebagai Information Gap dan tawarkan untuk menyusun estimasi berlabel `AGENT INFERENCE` HANYA bila pengguna memberi asumsi dasar (mis. estimasi capex, estimasi pendapatan tahunan, umur proyek).

## 4. Metrik Pendamping

| Metrik | Formula/Definisi | Kegunaan |
|---|---|---|
| NPV | Σ CFₜ/(1+r)ᵗ pada discount rate tertentu | Nilai proyek dalam rupiah saat ini |
| Payback Period | Waktu sampai kumulatif arus kas menutup investasi awal | Kecepatan balik modal (tidak mempertimbangkan nilai waktu uang) |
| Discounted Payback Period | Sama seperti di atas, tapi arus kas didiskon dulu | Lebih realistis dari payback period biasa |
| Profitability Index (PI) | NPV / Investasi awal | Efisiensi modal, berguna saat membandingkan proyek dengan skala berbeda |

## 5. Matriks IRR (Sensitivity Matrix)

Matriks yang diminta pengguna adalah tabel dua dimensi yang menunjukkan bagaimana IRR/NPV berubah terhadap variabel kunci. Format standar:

- **Sumbu baris:** skenario (mis. Pesimis / Moderat / Optimis, atau variasi volume/harga).
- **Sumbu kolom:** discount rate/hurdle rate (mis. 8%, 10%, 12%, 15%).
- **Isi sel:** IRR atau NPV hasil skenario tersebut.

Contoh bentuk (isi dengan angka nyata, bukan placeholder):

| Skenario | Discount Rate 8% | 10% | 12% | 15% |
|---|---:|---:|---:|---:|
| Pesimis | NPV = [—] | | | |
| Moderat | NPV = [—] | | | |
| Optimis | NPV = [—] | | | |

Setiap skenario harus menyebut **asumsi yang membedakannya** (mis. volume produksi, harga komoditas, eskalasi biaya) — jangan menampilkan angka tanpa menjelaskan apa yang berubah antar-skenario.

## 6. Prinsip Penyusunan

- Semua asumsi (discount rate, umur proyek, tingkat pertumbuhan, capex) wajib disebutkan eksplisit dan sumbernya jelas (dari pengguna, dokumen, atau estimasi industri berlabel).
- Jangan mengarang discount rate — bila pengguna tidak menyebutkan, tanyakan atau gunakan rentang umum WACC industri Indonesia sebagai **ilustrasi berlabel** (`GENERAL INDUSTRY PRACTICE`), bukan angka pasti.
- Sensitivitas selalu lebih berguna daripada satu angka tunggal — dorong penyajian matriks/rentang, bukan satu IRR "pasti benar".
- Skill tidak menyimpulkan "proyek ini layak dijalankan" secara final; skill menyajikan angka, bandingkan dengan hurdle rate bila diketahui, dan serahkan keputusan ke pengguna.
- Uang harus konsisten: sebutkan mata uang, apakah nominal atau riil (memperhitungkan inflasi), dan periode (tahunan/bulanan).
