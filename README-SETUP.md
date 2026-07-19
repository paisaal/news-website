# Portal Berita — Hugo + Blowfish

## Yang sudah disiapkan
- Theme **Blowfish** sudah terpasang di `themes/blowfish`
- Bahasa default: Indonesia (`id`), bahasa lain sudah dinonaktifkan
- 4 kategori contoh: **Politik, Ekonomi, Olahraga, Teknologi** (`content/articles/<kategori>/`)
- 4 artikel contoh dengan front matter siap pakai (title, tags, categories, authors)
- 2 profil penulis di `content/authors/` (`nurfaisal` dan `penulis2` — ganti nama & bio di `penulis2`)
- Homepage menampilkan daftar berita terbaru otomatis
- Menu navigasi sudah diarahkan ke tiap kategori

## Langkah pertama di komputer kamu

1. **Install Hugo Extended** (minimal v0.158, disarankan versi terbaru):
   https://gohugo.io/installation/

2. **Jalankan lokal:**
   ```bash
   cd berita-site
   hugo server -D
   ```
   Buka `http://localhost:1313`

3. **Sebelum publish, wajib ganti:**
   - `baseURL` di `config/_default/hugo.toml` → domain asli kamu
   - `title` di `config/_default/languages.id.toml` → nama portal berita kamu
   - Isi bio penulis kedua di `content/authors/penulis2/_index.md`
   - `googleAnalytics` di `config/_default/hugo.toml` kalau mau pasang GA4

## Menulis berita baru

Buat file baru di folder kategori yang sesuai, contoh:
```bash
hugo new content articles/politik/judul-berita-baru.md
```
Isi front matter (lihat contoh artikel yang sudah ada) lalu tulis isinya di bawah `---`.

## Deploy ke Netlify

1. Push project ini ke GitHub (`git init`, `git add .`, `git commit`, `git push`)
2. Di Netlify: **New site from Git** → pilih repo ini
3. Build command: `hugo --minify`
4. Publish directory: `public`
5. Set environment variable `HUGO_VERSION` = `0.164.0` (atau versi terbaru) di Netlify site settings

## Langkah selanjutnya (opsional)
- Setup **Decap CMS** biar temenmu bisa nulis tanpa Git — bilang aja kalau mau lanjut ke sini
- Tambah slot iklan di partial theme
- Tambah schema markup Article/NewsArticle buat SEO berita
