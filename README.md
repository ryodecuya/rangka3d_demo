# Rangka 3D — Demo (GitHub Pages)

Folder ini adalah **versi demo Rangka 3D** untuk dipasang di GitHub Pages sebagai halaman coba gratis.
Pengunjung bisa mencoba semua alat desain (denah 2D, ruangan otomatis, pintu/jendela/tangga/atap, furnitur, AC & elektrikal, plumbing/MEP, mode 3D, gambar teknik CAD, dan render fotorealistis), tetapi **menyimpan proyek dan semua ekspor/unduhan (file .rk3, PNG/JPG, PDF, DXF, DAE/GLB/OBJ/STL, CSV)** dikunci. Setiap fitur yang dikunci memunculkan
dialog *Fitur versi lengkap* dengan tombol **Beli versi lengkap** yang mengarah ke halaman produk Mayar Anda.
Badge **DEMO** dengan tombol beli juga selalu tampil di layar.

Demo ini berjalan sepenuhnya di browser tanpa server dan tanpa koneksi ke layanan lain: semua pustaka (Three.js, fflate) dan font sudah ada di folder `lib/` dan `fonts/`. Resolusi render dibatasi 1280 px. Membuka file `.rk3` dan mengimpor model (DAE/OBJ/GLB/STL) tetap bisa dicoba.

## 1. Atur link pembelian (wajib)
Buka `config.js`, ganti `buyUrl` dengan link halaman produk Mayar Anda (link yang dibagikan ke pembeli), misalnya:
```js
buyUrl: "https://ISI-LINK-PRODUK-MAYAR-ANDA",
buyLabel: "Beli versi lengkap",
```

## 2. Publikasikan di GitHub Pages
1. Masuk ke https://github.com → **New repository** → nama mis. `rangka3d-demo` → pilih **Public** (GitHub Pages gratis untuk repo publik) → **Create repository**.
2. Klik **uploading an existing file** → seret **seluruh isi folder ini** (bukan foldernya) — `index.html`, `config.js`, `.nojekyll`, folder `lib/` dan `fonts/` → **Commit changes**.
   File `.nojekyll` ikut diunggah (file tersembunyi; di Windows aktifkan *View › Hidden items*, di Mac tekan Cmd+Shift+. ). Bila terlewat, buat file kosong bernama `.nojekyll` lewat **Add file › Create new file**.
3. Buka **Settings → Pages** → *Build and deployment* → Source: **Deploy from a branch** → Branch: **main**, folder **/ (root)** → **Save**.
4. Tunggu 1–3 menit, lalu demo tampil di `https://USERNAME.github.io/rangka3d-demo/` (alamatnya tertulis di halaman Settings → Pages).
5. Pasang link itu di halaman produk Mayar, media sosial, atau marketplace sebagai tombol "Coba demo".

**Domain sendiri (opsional):** Settings → Pages → *Custom domain* → isi mis. `demo.domainanda.com`, lalu di pengelola DNS buat record **CNAME** `demo` → `USERNAME.github.io`. Centang *Enforce HTTPS* setelah aktif.

**Memperbarui demo:** unggah ulang `index.html` (dan folder lain bila berubah) ke repo yang sama; GitHub Pages memperbarui otomatis dalam beberapa menit. `config.js` tidak perlu diunggah ulang.

## 3. Mencoba di komputer sebelum diunggah
Klik dua kali `index.html` (Chrome/Edge), atau jalankan server kecil di folder ini: `python -m http.server 8080` lalu buka `http://localhost:8080`.

## 4. Seberapa aman demo ini?
- Mode demo **ditanam saat build**: mengubah `config.js` tidak membuka versi lengkap, dan fungsi simpan/unduh di dalam kode sudah dimatikan (bukan sekadar disembunyikan).
- Kode JavaScript diperkecil (minify) sehingga sulit dibaca dan diubah.
- Tetap perlu diingat: semua aplikasi web yang berjalan di browser bisa dilihat kodenya oleh pengunjung. Demo ini sengaja dibuat **tidak bisa menyimpan dan tidak bisa mengekspor**, sehingga tidak berguna untuk pekerjaan nyata — itu perlindungan utamanya. File versi lengkap hanya ada di zip yang dijual lewat Mayar; jangan unggah zip itu ke GitHub.
