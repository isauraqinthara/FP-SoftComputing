# FP-SoftComputing
Final Project Soft Computing: Optimasi Vehicle Routing Problem (VRP) di Surabaya Pusat menggunakan K-Means, Genetic Algorithm (GA), Simulated Annealing (SA), dan Ant Colony Optimization (ACO).

## 📌 Deskripsi Proyek
Proyek ini bertujuan untuk menyelesaikan permasalahan Vehicle Routing Problem (VRP) pada sistem pengangkutan sampah dari TPS (Tempat Pembuangan Sementara) di wilayah Surabaya Pusat menuju TPA Benowo.
Pengangkutan dilakukan oleh sejumlah arm-roll truck dengan keterbatasan kapasitas angkut. Sistem harus dapat:
- Menentukan pengelompokan TPS secara spasial (klasterisasi),
- Menyusun urutan kunjungan yang efisien,
- Menghindari pelanggaran batas kapasitas kendaraan,
- Meminimalkan total jarak tempuh.

### ✅ Pendekatan yang Digunakan
- **Clustering**: Menggunakan **K-Means** untuk mengelompokkan TPS berdasarkan koordinat geografis, disesuaikan dengan jumlah kendaraan.
- **Constraint Handling**: Memastikan volume sampah per klaster tidak melebihi batas kapasitas maksimal (contoh: 40 m³ per truk).
- **Routing Optimization**:
  - **Genetic Algorithm (GA)** – untuk menemukan rute optimal per klaster.
  - **Simulated Annealing (SA)** – untuk menghindari solusi lokal dan menyempurnakan hasil GA.
  - **Ant Colony Optimization (ACO)** – sebagai opsi eksploratif berbasis graf.

### 🎯 Output
- Rute optimal untuk tiap kendaraan: TPS → TPA → kembali ke Pool.
- Visualisasi interaktif peta rute (via `folium`).
- Jarak tempuh total per kendaraan (dalam kilometer).

## 🧰 Tools & Library
- Python 3
- `pandas`, `numpy`, `random`
- `sklearn.cluster.KMeans`
- `folium` – visualisasi peta interaktif
- `math` – untuk perhitungan jarak Haversine
- *Custom algorithms* – GA, SA, dan ACO

## 🚀 Cara Menjalankan Program
1. **Buka Google Colab**  
   Akses notebook Colab melalui link berikut:  
   [LINK Colab](https://colab.research.google.com/drive/1_H-QvKWbJtYxu17Z7ax4m5ZQlVGaOhpj)
2. **Unggah Dataset**  
   Dataset yang dibutuhkan:  
   `SURABAYA PUSAT TPA BENOWO - Sheet1.csv`  
   Contoh kode untuk upload:
   ```python
   from google.colab import files
   uploaded = files.upload()
3. Jalankan Seluruh Program
   Klik menu Runtime > Run all atau tekan Ctrl + F9 untuk menjalankan seluruh proses:
  - Membaca dan memproses data TPS
  - Melakukan clustering dengan K-Means
  - Menyusun rute optimal per klaster menggunakan GA / SA / ACO
  - Menampilkan peta hasil rute menggunakan Folium
