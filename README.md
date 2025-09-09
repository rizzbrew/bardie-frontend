# Bardie Frontend

Bardie Frontend adalah aplikasi web sederhana untuk berinteraksi dengan **Bardie Backend (Google Gemini Reversed API)**.  
Dibangun dengan **HTML, TailwindCSS, dan JavaScript** tanpa framework tambahan, sehingga ringan dan mudah di-deploy.

## Fitur
- Input prompt text-only atau dengan gambar.
- Upload hingga 5 gambar (PNG, JPEG, WEBP).
- Loading state & tombol dengan animasi.
- Popup hasil (gambar atau teks) dengan tampilan modern.
- Toast notification untuk status sukses/gagal.
- Prompt populer otomatis bisa dicoba.
- Responsive design dengan **TailwindCSS**.

## Struktur File
```
index.html   # File utama (frontend UI)
```

## Konfigurasi
Secara default, frontend sudah diarahkan ke API demo di Hugging Face:
```
https://rizzlogy-bardie-api.hf.space/backend/conversation
```

Jika ingin pakai server backend milikmu sendiri:
1. Edit bagian `fetch` di dalam `<script>`:
   ```js
   const res = await fetch("https://your-backend-url/backend/conversation", {
     method: "POST",
     headers: { "Content-Type": "application/json" },
     body: JSON.stringify({ ...payload, preview: true }),
   });
   ```
2. Ganti `https://your-backend-url` dengan domain backend kamu.

## Menjalankan Secara Lokal
1. Clone repo:
   ```bash
   git clone https://github.com/yourusername/bardie-frontend.git
   cd bardie-frontend
   ```
2. Buka `index.html` langsung di browser, atau jalankan server statis:
   ```bash
   npx serve .
   ```
3. Akses di `http://localhost:3000` (atau port sesuai server).

## Deploy
Bisa di-deploy ke layanan hosting statis:
- **GitHub Pages**
- **Vercel**
- **Netlify**
- **Cloudflare Pages**

Cukup upload `index.html` ke platform pilihanmu.

## Integrasi dengan Bardie Backend
Pastikan backend [bardie-backend](https://github.com/rizzlydev/bardie-backend) sudah jalan di Hugging Face atau server pribadi.  
Kemudian ubah URL fetch di frontend sesuai backend tersebut.

---

## Author
- **RizzyFuzz**  
   [https://www.rizzy.eu.org/](https://www.rizzy.eu.org/)  
   support@rizzy.eu.org

## License
MIT License
