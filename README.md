# Jurnal Dokumentasi: Menjinakkan AI Lokal Tanpa Sensor

Catatan harian dan dokumentasi perjuangan gua (Avii) dari nol dalam mempelajari, mengulik, dan mendeploy AI lokal pribadi di PC rumah tanpa kuota, gratis, dan tanpa sensor.

--- 3 jam gua ngulik wkwk

## 🛠️ SPESIFIKASI HARDWARE (PC DEWA SEPUH)
* **CPU:** AMD Ryzen 3 2200G
* **RAM:** 16 GB DDR4 (Lega tur tumpah-tumpah)
* **VGA:** NVIDIA GeForce GTX 750 Ti 4GB GDDR5 (VGA Legendaris)

---

## 📘 BAB 1: Mimpi Punya AI Sendiri (The Origin)

Gua bosan sama aplikasi chat karakter AI yang ada di Play Store (kayak Chai, PolyBuzz, atau Emochi). Tiap kali mau chat seru kudu mikirin kuota token, nonton iklan video 30 detik, atau bayar langganan premium bulanan yang mahal. Plus, chat-nya penuh sensor.

Akhirnya gua memutuskan buat belajar jalan gerilya: **Ngerun AI sendiri di PC rumah.**
Gua nemu kombinasi tools dewa:
1. **Jan AI:** Buat jadi "otak" server AI lokal di localhost.
2. **SillyTavern:** Buat jadi UI/UX interface chat-nya biar bisa nge-load karakter bikinan gua sendiri (Karakter pertama gua: **Vira**, si *tsundere* sekelas yang suka ngomel).

---

## 🟥 BAB 2: Tragedi Layar Hitam & PC Pingsan (The GPU Layers Trap)

Ini bagian paling kocak sekaligus menegangkan selama eksperimen. Pas pertama kali install Jan AI (versi 0.7.9) dan download model `Jan-v3.5-4B-Q4_K_XL` (ukuran 2.8GB), gua langsung tes ketik *"halo"*.

**BOOM! PC GUA LANGSUNG FREEZE TOTAL!**
* Mouse gak bisa digerakin sama sekali.
* Lagu yang lagi disetel mendadak mati.
* Sistem Windows nge-lock demi menyelamatkan hardware dari Overheat/Crash.
* Terpaksa gua tekan tombol power di casing PC buat shutdown paksa.

### Analisis Penyakit (Biang Kerok):
Ternyata di dalam pengaturan internal Jan AI, kolom **`GPU Layers`** bawaannya terset ke angka **`100`**. Artinya, Jan AI dipaksa melempar 100% beban mikir model ke kartu grafis. 

Meskipun GTX 750 Ti gua versinya 4GB GDDR5, arsitekturnya (Maxwell) udah terlalu berumur buat baca instruksi teknologi AI modern (CUDA/Vulkan versi terbaru) di Jan AI. VGA-nya kaget, langsung pingsan di tempat!

### Solusi Fix Total:
Gua masuk ke settingan roda gigi Jan AI, lalu mengubah **`GPU Layers` menjadi `0`**. 
Dengan mengubah ke `0`, beban mikir AI dialihkan penuh ke **CPU Ryzen 3 + RAM 16GB** gua yang luas banget. Hasilnya? PC adem ayem, lancar jaya, dan gak bakal pernah freeze lagi!







![Chat AI] <img width="485" height="595" alt="Screenshot 2026-05-19 122040" src="https://github.com/user-attachments/assets/8324e98f-fa04-4ffc-a4b1-6147c05c007e" />









![System CMD] <img width="994" height="622" alt="Screenshot 2026-05-19 122056" src="https://github.com/user-attachments/assets/0300e92f-febd-4ead-bdc9-674e704fbb9d" />




![Layar Freeze Karena tidak sengaja 100 Layer di GPU] <img width="365" height="123" alt="Screenshot 2026-05-19 122549" src="https://github.com/user-attachments/assets/24646a02-baa5-4da5-b378-33bf6968222b" />




![Ternyata GTX 750 TI Memang ga kuat. Lalu Saya Set Ke 0 agar lancar] <img width="374" height="115" alt="Screenshot 2026-05-19 122559" src="https://github.com/user-attachments/assets/d662f1b5-88cb-436b-8a82-ced184e806d7" />


