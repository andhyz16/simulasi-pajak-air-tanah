# 🌊 Kalkulator & Simulasi Pajak Air Tanah (PAT) Progresif (A1 - D5)

Aplikasi web modern, interaktif, dan responsif untuk menghitung dan mensimulasikan **Nilai Perolehan Air (NPA)** dan **Pajak Air Tanah (PAT)** menggunakan sistem **Tarif Blok Progresif** dari Golongan **A1 hingga D5**.

Dibangun murni dengan HTML5, Tailwind CSS, dan JavaScript tanpa *build tools* (*zero dependencies*), sehingga **siap di-deploy langsung ke GitHub Pages hanya dalam 1 menit**.

---

## ✨ Fitur Utama

1. **📌 Simulator Interaktif Cepat (Real-time Calculator)**
   * Pilih **Kriteria Sumber Daya Alam** (4 kriteria) & **Kelompok Pengguna** (1 s/d 5).
   * Golongan Air Tanah (A1 s/d D5) terhitung otomatis.
   * Input manual tarif pajak (% Tarif) dan volume air (m³).
   * Rincian meteran blok volume, bobot SDA, NPA per blok, dan Pajak Terutang dihitung secara *live*.

2. **📋 Tabel Simulasi 20 Golongan Wajib Pajak (A1 s/d D5)**
   * Disusun berurutan dari Golongan **A1 sampai D5** dengan jenis Wajib Pajak yang representatif.
   * Nilai **% Tarif** dan **Volume (m³)** dapat diedit langsung per baris di tabel.
   * Rincian kolom volume: `Volume (0-50)`, `Volume (51-500)`, `Volume (501-1000)`, `Volume (1001-2500)`, `Volume (>2500)`.
   * Rincian NPA rupiah per blok: `NPA (0-50)`, `NPA (51-500)`, dst.
   * Fitur pencarian instan (search) dan tombol Reset nilai default.

3. **📊 Matriks Bobot Komponen Sumber Daya Alam**
   * Tab khusus yang menampilkan tabel referensi matriks bobot resmi untuk ke-20 Golongan (A1 s/d D5) berdasarkan Harga Dasar Air (HDA) **Rp 3.079 / m³**.

4. **📖 Panduan Edukasi Blok Progresif**
   * Penjelasan rumus matematis per blok dan alasan mengapa Blok 4 berkapasitas maksimal 1.500 m³.

5. **💾 Ekspor & Cetak**
   * Tombol **Ekspor CSV** untuk mengunduh hasil simulasi ke format spreadsheet/Excel.
   * Tombol **Cetak / PDF** dengan styling ramah cetak (*print-friendly*).

---

## 🚀 Cara Publikasi ke GitHub & Mengaktifkan GitHub Pages

Ikuti 3 langkah mudah ini untuk meng-online-kan aplikasi ke GitHub:

### Langkah 1: Buat Repositori Baru di GitHub
1. Buka [github.com/new](https://github.com/new).
2. Beri nama repositori, misalnya: `simulasi-pajak-air-tanah`.
3. Pilih opsi **Public**, lalu klik **Create repository**.

### Langkah 2: Hubungkan & Push dari Komputer Anda
Buka Terminal / PowerShell di folder ini, lalu jalankan perintah berikut:

```bash
# Hubungkan ke repositori GitHub Anda (ganti USERNAME dan REPO_NAME)
git remote add origin https://github.com/USERNAME/simulasi-pajak-air-tanah.git

# Pastikan branch utama bernama main
git branch -M main

# Upload (push) kode ke GitHub
git push -u origin main
```

### Langkah 3: Aktifkan GitHub Pages (1 Klik Selesai!)
1. Di halaman repositori GitHub Anda, klik tab **Settings** (di bagian atas).
2. Pada menu samping kiri, klik **Pages**.
3. Pada bagian **Build and deployment** > **Branch**:
   * Pilih branch: **`main`**
   * Pilih folder: **`/(root)`**
   * Klik tombol **Save**.
4. Tunggu sekitar 1 menit, website Anda akan langsung aktif di:
   `https://USERNAME.github.io/simulasi-pajak-air-tanah/`

---

## 📐 Rumus Perhitungan Blok Progresif

| Blok Volume | Rentang Kumulatif | Kapasitas Blok | Rumus Excel / JavaScript |
| :--- | :---: | :---: | :--- |
| **Volume (0-50)** | $0 - 50 \text{ m³}$ | $50 \text{ m³}$ | `MIN(Volume, 50)` |
| **Volume (51-500)** | $51 - 500 \text{ m³}$ | $450 \text{ m³}$ | `MAX(0, MIN(Volume, 500) - 50)` |
| **Volume (501-1000)** | $501 - 1.000 \text{ m³}$ | $500 \text{ m³}$ | `MAX(0, MIN(Volume, 1000) - 500)` |
| **Volume (1001-2500)** | $1.001 - 2.500 \text{ m³}$ | $1.500 \text{ m³}$ | `MAX(0, MIN(Volume, 2500) - 1000)` |
| **Volume (>2500)** | $> 2.500 \text{ m³}$ | Sisa volume | `MAX(0, Volume - 2500)` |

$$\text{NPA Blok}_i = \text{Volume Blok}_i \times \text{Bobot SDA}_i \times 3.079$$
$$\text{Total Pajak Terutang} = \left(\sum_{i=1}^5 \text{NPA Blok}_i\right) \times \% \text{ Tarif}$$

---

## 📁 Struktur File
* `index.html` : Aplikasi web utama (UI, Interaktivitas, dan Rumus Matematika Progresif).
* `Simulasi NPA Progresif (A1-D5).xlsx` : Spreadsheet Excel dengan master table A1-D5 dan rumus progresif.
* `README.md` : Dokumentasi teknis & panduan deployment.
