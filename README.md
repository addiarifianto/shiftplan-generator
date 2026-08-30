# ShiftPlan Generator — Sistem Jadwal Security

Aplikasi web untuk mengelola dan menghasilkan jadwal shift 12 jam (Pagi & Malam) Security Yayasan Ganesa Satria Temanggung / SMK Ganesa Satria 4 Kedu.

## Fitur

- **Generate Jadwal Otomatis 100% Legal** — menghasilkan jadwal pagi & malam dengan aturan operasional (kuota per hari, max hari beruntun, preferensi shift, tanpa 2 hari libur beruntun). Jika ada hari yang secara matematis mustahil ditutup tanpa melanggar aturan, sistem melaporkannya secara jujur — tidak ada pelonggaran/pengecualian manual.
- **Pemerataan Beban Otomatis** — total hari kerja & libur diratakan antar personil (selisih ≤ 2 hari/bulan), termasuk pegawai khusus shift malam; porsi pagi/malam pegawai BOTH ikut seimbang lintas bulan via riwayat bulan sebelumnya.
- **Aturan Khusus Hari** — kuota pagi berkurang di akhir pekan, pembagian shift pendek/penuh di hari Jumat.
- **Panel Dashboard** — status pengamanan pos, hari yang kekurangan personil, klaster libur beruntun yang tak bisa dihindari, arsip bulan.
- **Edit Manual** — klik sel jadwal untuk mengubah shift & request (S1/S2/OFF).
- **Manajemen Karyawan** — tambah, edit, hapus personil (Full-Time/Part-Time, maxConsecutive, preferensi shift).
- **Statistik per Bulan** — tab Statistik & Riwayat dengan pemilih bulan/tahun; kartu jam kerja & beban per personil.
- **Ekspor PDF** — download jadwal ke PDF siap cetak.
- **Penyimpanan Lokal + Sinkronisasi Cloud** — data tersimpan di browser (localStorage) dan tersinkron ke Firebase Firestore saat login Google (dokumen tunggal `global/data`).

## Teknologi

- React 18 (CDN via UMD)
- Tailwind CSS (CDN)
- Lucide Icons
- jsPDF + jspdf-autotable
- Babel Standalone
- Firebase 11 (App, Auth Google, Firestore)

## Cara Pakai

1. Buka halaman aplikasi yang sudah di-deploy (Vercel) — untuk pengembangan lokal cukup buka `index.html` di browser / live server.
2. (Opsional) Login dengan Google untuk sinkronisasi data antar perangkat.
3. Tambah/kelola data karyawan di tab **Kelola Karyawan**.
4. Pilih bulan/tahun, klik **Generate Jadwal** — status pengamanan & pelanggaran tampil otomatis.
5. Atur request bila perlu (klik sel jadwal), lalu Generate ulang.
6. Analisis beban tiap bulan di tab **Statistik & Riwayat**, atau ekspor ke PDF.

## Deployment

Hosting statik di **Vercel** (`vercel.json`). Setiap push ke branch `master` otomatis memicu deploy produksi (Vercel auto-deploy). Data jadwal tidak disimpan di dalam file statik, sehingga proses deploy tidak menghapus arsip bulan — semuanya tersimpan di localStorage browser & Firestore.

## Struktur

```
index.html        — Aplikasi single-page (semua dalam satu file)
vercel.json       — Konfigurasi hosting Vercel
opencode.json     — Konfigurasi OpenCode
.cac/             — Auto-commit hooks (code-agent-auto-commit)
README.md         — Dokumentasi ini
```

## Lisensi

MIT