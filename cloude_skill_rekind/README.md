# Claude Skill Rekind

Repository ini berisi empat custom skill yang dikembangkan untuk kebutuhan pembelajaran dan eksperimen kerja:

- `persona` — merancang dan menguji persona agen AI;
- `book-writer` — menyusun buku, handbook, dan HTML;
- `indonesia-corporate-action-intelligence` — memantau dan menjelaskan aksi korporasi Indonesia;
- `indonesia-business-modeler` — membedah proses bisnis, organisasi, pendapatan, biaya, dan laba.

## Prinsip penulisan

Semua skill memakai bahasa Indonesia yang profesional tetapi natural. Hasil harus terdengar seperti penjelasan rekan kerja yang memahami konteks, bukan seperti template otomatis. Standar lengkap ada di `docs/natural-language-standard.md`.

## Struktur

```text
skills/     source setiap skill
tests/      test case dan hasil aktual
docs/       panduan pengembangan dan instalasi
feedback/   koreksi dan pembelajaran mentah
learning/   pembelajaran yang sudah ditinjau
```

## Status

Paket ini masih berstatus **draft** dan perlu diuji di Claude sebelum disebut stabil.
