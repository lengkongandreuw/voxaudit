# voxaudit

Duplikat **Vox Social Score** (voxaudit.voxlumedia.com) untuk perbaikan, berbasis kode `voxsocial`.

**Live:** https://lengkongandreuw.github.io/voxaudit/

Satu file `index.html` (React 18 + Tailwind CDN), tanpa build step. Buka langsung di browser atau sajikan folder ini lewat server statis / GitHub Pages.

## Yang diperbaiki dibanding versi live

- Layar login konsisten dengan produknya (Social Media Audit, bukan SEO Audit).
- Kartu "AI-Powered Insights" tidak lagi menimpa maskot di layar ponsel.
- Placeholder input tidak terpotong; tidak ada scroll horizontal di 375px.
- Tombol "Get My Score" dengan input kosong kini menampilkan pesan error yang jelas.
- Aksesibilitas: label untuk input, `aria-label` pada tombol logout & form lead, `aria-pressed` pada toggle, error diumumkan (`role="alert"`), animasi menghormati `prefers-reduced-motion`.
- Aset dimuat dari folder `assets/` lokal; favicon memakai logo Voxlumedia.
- Satu `AudioContext` dipakai ulang (sebelumnya dibuat baru di setiap ketukan tombol).

## Catatan

- **Login masih demo.** "Continue with Google/Email" hanya menyimpan sesi di `localStorage`. Untuk produksi, hubungkan ke penyedia auth (mis. Firebase Auth / Google Identity Services).
- **Skor masih simulasi** kecuali `apiKey` Gemini diisi. Jangan menaruh API key di kode frontend publik; panggil lewat backend/proxy.
- Form "Get Your Complete PDF Report" belum mengirim data ke mana pun.
- Angka "50+ Businesses", "4.9/5", "5M+" masih teks statis; perlu dikonfirmasi sumbernya.
