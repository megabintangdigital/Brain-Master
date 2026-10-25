# Brain Master — Memory & Logic

Aplikasi Progressive Web App (PWA) pembelajaran dan latihan ketangkasan otak yang berfokus pada daya ingat (*memory*) dan logika bertahap dari level Basic hingga Master serta Latihan Olimpiade Sains & Matematika.

---

## 🚀 Fitur Utama
- **Aktivasi Lisensi Mandiri**: Layar aktivasi aman dengan verifikasi kode aktivasi (misal: `BRAIN-MASTER-2026`).
- **Materi & Konsep Logika**: Modul belajar terstruktur dari dasar deduksi hingga strategi olimpiade.
- **Latihan Bertingkat (Level 1–6)**: Tantangan memori dan logika adaptif dengan variasi mini-game interaktif.
- **Drill Latihan Olimpiade**: 8 kategori drill soal mendalam (Knight & Knave, Diophantine, Paritas, Pigeonhole, Conway Look-and-Say, dll.) dengan pembahasan langkah demi langkah dan strategi cepat.
- **Profil & Radar Statistik**: Pelacakan level, XP, streak latihan harian, dan grafik radar 6 dimensi kemampuan kognitif.
- **Dukungan PWA & Offline**: Dilengkapi Service Worker (`sw.js`) dan `manifest.webmanifest` untuk dapat diinstal di Android/iOS/Desktop dan diakses secara offline.

---

## 🛠️ Panduan Menjalankan di Lokal (Local Development)

1. **Clone repository:**
   ```bash
   git clone https://github.com/username-anda/brain-master.git
   cd brain-master
   ```

2. **Instal dependensi:**
   ```bash
   npm install
   ```

3. **Jalankan development server:**
   ```bash
   npm run dev
   ```
   Aplikasi akan berjalan di `http://localhost:3000`.

4. **Uji build produksi:**
   ```bash
   npm run build
   npm run preview
   ```

---

## 🌐 Panduan Deploy ke GitHub & Vercel

### Langkah 1: Push ke GitHub
1. Inisialisasi Git di folder proyek (jika belum):
   ```bash
   git init
   git add .
   git commit -m "feat: initial commit Brain Master PWA"
   ```
2. Buat repository baru di [GitHub](https://github.com/new) (misal: `brain-master`).
3. Hubungkan ke repository GitHub dan lakukan push:
   ```bash
   git remote add origin https://github.com/username-anda/brain-master.git
   git branch -M main
   git push -u origin main
   ```

### Langkah 2: Deploy ke Vercel (Otomatis & Gratis)
1. Buka [Vercel Dashboard](https://vercel.com/dashboard) dan klik **Add New...** -> **Project**.
2. Pilih repository GitHub `brain-master` yang baru Anda buat, lalu klik **Import**.
3. Vercel akan otomatis mendeteksi pengaturan:
   - **Framework Preset**: `Vite`
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
4. Konfigurasi `vercel.json` sudah disediakan di dalam repositori untuk menangani:
   - Header *Cache-Control* `sw.js` agar pembaruan PWA selalu segar (*instant update*).
   - Rewrite routing SPA agar tidak terjadi halaman 404 saat di-refresh.
5. Klik **Deploy**. Dalam beberapa detik aplikasi sudah aktif di URL publik Vercel (`https://brain-master-*.vercel.app`).

---

## 🔒 Keamanan & Verifikasi File
- File rahasia `.env*` telah dikecualikan di `.gitignore` (hanya `.env.example` yang diikutsertakan sebagai referensi template).
- Asset statis (`css/`, `js/`, `icon.svg`, `sw.js`, `manifest.webmanifest`) tersinkronisasi penuh antara root dan folder `public/`, memastikan build produksi di direktori `dist/` selalu lengkap dan identik.
