# Changelog — Indonesia Business Modeler

## [0.3.0-draft] — 2026-07-24

### Ditambahkan
- Tiga analysis mode baru: **Cash Flow Analysis**, **Investment Return /
  IRR Matrix**, dan **Business Opportunity Analysis**.
- `references/irr-cashflow-guide.md` — struktur arus kas, jembatan
  profit-ke-kas, formula IRR/NPV/payback, dan format matriks
  sensitivitas (skenario × discount rate).
- `references/business-opportunity-guide.md` — lima dimensi penilaian
  peluang bisnis baru (daya tarik pasar, kelayakan operasional,
  kesesuaian strategis, risiko, indikasi return) dengan skor 1–5.
- `assets/cash-flow-template.md`, `assets/irr-matrix-template.md`,
  `assets/business-opportunity-template.md`.
- Auto-deteksi analysis mode dari kata kunci pengguna (§6a `SKILL.md`)
  supaya skill tidak lagi bergantung pada pengguna menyebut nama mode
  secara eksplisit di setiap prompt.

### Diubah
- Scope (§4), daftar trigger (§2), non-trigger (§3), larangan (§14), dan
  indeks referensi/asset (§15–16) diperbarui untuk mode baru.
- Frontmatter description diperluas untuk mencakup cash flow, IRR, dan
  business opportunity analysis.

### Status
Masih **draft — siap diuji**. Tiga mode baru belum melalui eksekusi test
case; lihat `tests/indonesia-business-modeler/test-cases.md` untuk
menambah skenario pengujian sebelum dianggap stabil.

## [0.2.0-draft] — 2026-07-22

- Menambahkan standar bahasa natural.
- Menulis ulang Company Business Model Card dan Company Deep Dive agar lebih mengalir.
- Menambahkan pengujian gaya bahasa.


Format mengikuti semantic versioning (MAJOR.MINOR.PATCH) sesuai aturan
Project "Persona Development".

## [0.1.0-draft] — 2026-07-22

### Status
Prototype awal, status **draft — siap diuji**. Belum melalui eksekusi
testing plan; belum divalidasi sebagai release candidate.

### Ditambahkan
- `SKILL.md` — definisi lengkap skill: tujuan, trigger, non-trigger,
  scope, exclusions, input, source hierarchy, workflow analisis,
  14 analysis mode, output standard, confidence model, continuous
  improvement, keamanan, batas kewenangan, larangan.
- 12 file `references/`: business-model-framework,
  business-process-framework, organization-function-guide,
  job-desk-analysis-guide, revenue-model-taxonomy, cost-structure-guide,
  profit-mechanism-guide, industry-business-models,
  process-role-matrix-guide, source-and-confidence-guide,
  continuous-improvement-guide, testing-guide.
- 11 file `assets/`: business-model-canvas-template,
  company-business-model-card, business-process-map-template,
  value-chain-template, organization-job-desk-template,
  revenue-model-template, profit-model-template,
  process-role-matrix-template, company-deep-dive-template,
  industry-comparison-template, learning-record-template.
- `tests/test-cases.md` — 22 rancangan test case (trigger, non-trigger,
  8 analysis-mode test, missing-information, inference-labeling,
  conflicting-source, hallucination, investment-advice boundary,
  continuous-improvement, regression). Belum ada hasil eksekusi.

### Diketahui Belum Lengkap / Risiko Terbuka
- Testing plan belum dijalankan — semua test case berstatus BLOCKED.
- `references/industry-business-models.md` baru mencakup pola umum
  tingkat tinggi per kelompok industri; perlu diperluas melalui
  continuous improvement seiring bertambahnya kasus nyata.
- Belum ada validasi lapangan (uji ke pengguna Business Excellence/
  Strategy/BD sesungguhnya).
