# SIPAT - Simulasi Pajak Air Tanah Provinsi Sulawesi Barat

**SIPAT (Simulasi Pajak Air Tanah)** adalah aplikasi web interaktif untuk simulasi, perhitungan progresif 5 blok, dan rekapitulasi penerimaan Pajak Air Tanah (PAT) dan Nilai Perolehan Air (NPA) di 6 Kabupaten se-Provinsi Sulawesi Barat berdasarkan **Peraturan Gubernur Sulawesi Barat Nomor 3 Tahun 2025**.

🌐 **Akses Aplikasi Online:** [https://andhyz16.github.io/simulasi-pajak-air-tanah/](https://andhyz16.github.io/simulasi-pajak-air-tanah/)

---

## 🚀 Fitur Utama SIPAT
1. **Input Dinamis Wajib Pajak**:
   - Pilih Kabupaten (Polewali Mandar, Majene, Mamuju, Mamuju Tengah, Mamasa, Pasangkayu).
   - Input manual Nama Wajib Pajak / Badan Usaha.
   - Pilihan Dropdown Kriteria Sumber Daya Alam (A, B, C, D).
   - Pilihan Dropdown Kelompok Pengguna (1 sampai 5).
   - Pembentukan Kode Golongan Otomatis (A1 s/d D5) beserta pratinjau hitungan cepat.
   - Input Volume Pemakaian Air ($m^3$) dan % Tarif Pajak Manual (default 10%, rekomendasi 2% untuk SPAM/PDAM).
2. **Kalkulasi Otomatis Progresif 5 Blok**:
   - Blok 1: $0 - 50\text{ m}^3$
   - Blok 2: $51 - 500\text{ m}^3$
   - Blok 3: $501 - 1.000\text{ m}^3$
   - Blok 4: $1.001 - 2.500\text{ m}^3$
   - Blok 5: $> 2.500\text{ m}^3$
   - Standar Harga Air Baku (HAB): **Rp 3.079 / m³** (Pasal 11 & Lampiran II Pergub 3/2025).
   - Bobot Air Tanah (BAT): $(60\% \times S) + (40\% \times P)$.
3. **Penyimpanan Lokal (Local Storage)**:
   - Data tersimpan otomatis di browser pengguna, tidak hilang saat halaman di-refresh.
   - Tersedia tombol Edit dan Hapus per baris wajib pajak.
4. **Export Excel (.xlsx) per Kabupaten**:
   - Unduh laporan lengkap dalam format Microsoft Excel asli (`.xlsx`) via SheetJS untuk seluruh kabupaten atau difilter per kabupaten.
5. **Referensi Regulasi Lengkap**:
   - Tab Lampiran III Resmi Pergub Sulbar No. 3/2025.
   - Tab Matriks Bobot BAT 20 Golongan.
   - Tab Dasar Hukum & Petunjuk Penggunaan.
