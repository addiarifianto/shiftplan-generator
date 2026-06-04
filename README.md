# ShiftPlan Generator — Sistem Jadwal Security

Aplikasi web untuk mengelola dan menghasilkan jadwal shift 12 jam (Pagi & Malam) Security Yayasan Ganesa Satria Temanggung / SMK Ganesa Satria 4 Kedu.

## Fitur

- **Generate Jadwal Otomatis** — Algoritma cerdas untuk penjadwalan shift pagi & malam dengan aturan operasional (max hari beruntun, preferensi shift, dll)
- **Aturan Khusus Hari** — Kuota pagi berkurang di akhir pekan, pembagian shift pendek/penuh di hari Jumat
- **Panel Dashboard** — Widget informasi karyawan, status pengamanan pos, arsip bulan
- **Edit Manual** — Klik sel jadwal untuk mengubah shift secara manual
- **Manajemen Karyawan** — Tambah, edit, dan hapus data personil
- **Ekspor PDF** — Download jadwal ke PDF siap cetak
- **Penyimpanan Lokal** — Data tersimpan otomatis di browser (localStorage)

## Teknologi

- React 18 (CDN via UMD)
- Tailwind CSS (CDN)
- Lucide Icons
- jsPDF + jspdf-autotable
- Babel Standalone

## Cara Pakai

1. Buka `index.html` di browser (atau jalankan via live server)
2. Tambah data karyawan di tab **Kelola Karyawan**
3. Pilih bulan/tahun, klik **Generate Jadwal**
4. Edit shift manual jika perlu (klik sel jadwal)
5. Ekspor ke PDF atau cetak langsung

## Struktur

```
index.html        — Aplikasi single-page (semua dalam satu file)
opencode.json     — Konfigurasi OpenCode
.cac/             — Auto-commit hooks (code-agent-auto-commit)
README.md         — Dokumentasi ini
```

## Lisensi

MIT
