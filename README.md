# PhysicGame: Simulasi Proyektil Interaktif v2.0
**Proyek Besar Mata Kuliah Fisika Informatika**
**Universitas Muhammadiyah Surabaya - Teknik Informatika**

PhysicCraft adalah aplikasi simulasi fisika berbasis web yang dirancang untuk memvisualisasikan hukum-hukum mekanika klasik. Menggunakan **Matter.js** sebagai *physics engine*, aplikasi ini memungkinkan pengguna untuk bereksperimen dengan variabel gravitasi dan massa secara real-time untuk memahami dampaknya terhadap lintasan dan energi objek.

---

## 👥 Anggota Kelompok 1
*   **Improatus Soliha** (20251337006)
*   **Fairuz Abdillah Idrus** (20251337014)
*   **Moh. Faiz Haikal** (20251337015)
*   **Abi Ibryan Naisa Putra** (202513337025)
*   **Wfaa Abdelalem Omer Abdelalem** (20251337031)
*   **Abidzar Dzakwan Sahudi** (20251337037)

---

## 🚀 Fitur Utama
1.  **Mekanisme Ketapel Interaktif:** Menggunakan *Constraint* elastis (Hukum Hooke) untuk melontarkan proyektil.
2.  **Prediksi Lintasan (Trajectory):** Perhitungan *real-time* posisi masa depan objek berdasarkan vektor kecepatan awal dan gravitasi.
3.  **Data Telemetri Real-time:** HUD (Heads-Up Display) yang menampilkan Kecepatan ($v$), Momentum ($p$), dan Energi Kinetik ($Ek$).
4.  **Auto-Respawn:** Sistem otomatis yang mengembalikan proyektil ke titik jangkar jika keluar dari batas area simulasi.
5.  **Monitoring Konsol:** Tabel data statistik fisika yang diperbarui setiap 200ms pada *Developer Console* (F12).

---

## 🧪 Konsep Fisika yang Diterapkan

### 1. Gerak Parabola (Kinematika)
Simulasi menghitung posisi proyektil setiap frame menggunakan persamaan:
$$y = y_0 + v_{0y} \cdot t - \frac{1}{2}g \cdot t^2$$
Di mana perubahan nilai **Gravitasi** pada kontrol panel akan secara langsung mengubah kelengkungan lintasan.

### 2. Hukum Momentum & Energi Kinetik
Daya hancur proyektil terhadap target ditentukan oleh:
*   **Momentum:** $p = m \cdot v$
*   **Energi Kinetik:** $Ek = \frac{1}{2}m \cdot v^2$
    Meningkatkan variabel **Massa** akan meningkatkan transfer energi saat tumbukan terjadi.

### 3. Hukum Hooke (Elastisitas)
Gaya lontar ketapel dihitung berdasarkan jarak tarikan mouse terhadap titik jangkar:
$$F = -k \cdot \Delta x$$

---

## 🛠️ Teknologi yang Digunakan
*   **Vue 3 (Vite):** Framework utama untuk reaktivitas dan UI.
*   **Matter.js:** Physics engine untuk kalkulasi rigid body, gravitasi, dan tumbukan.
*   **Tailwind CSS v4:** Untuk perancangan antarmuka yang modern dan responsif.
*   **Verlet Integration:** Algoritma dasar yang digunakan engine untuk stabilitas simulasi fisika.

---

## 🎮 Cara Menjalankan Proyek
1.  Pastikan Anda telah menginstal [Node.js](https://nodejs.org/).
2.  Clone repository ini atau salin folder proyek.
3.  Buka terminal di folder proyek dan jalankan:
    ```bash
    npm install
    npm run dev