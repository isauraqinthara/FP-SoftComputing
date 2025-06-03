# FP-SoftComputing
Final Project Soft Computing for simulating Vehicle Route Problem with Constraint on Surabaya Regions.

## Deskripsi Proyek
Proyek ini merupakan implementasi dari Final Project Soft Computing yang bertujuan mensimulasikan dan mengoptimasi Vehicle Routing Problem (VRP) dalam konteks pengangkutan sampah dari sejumlah TPS (Tempat Pembuangan Sementara) di wilayah Surabaya Pusat menuju TPA (Tempat Pembuangan Akhir) Benowo, dengan mempertimbangkan kendala kapasitas kendaraan (vehicle capacity constraint).
Metode ini meniru sistem nyata pengangkutan sampah oleh arm-roll truck yang harus:
- Menjemput sampah dari beberapa TPS/LPS,
- Memastikan kapasitas truk tidak melebihi batas maksimum, dan
- Menyusun urutan kunjungan TPS yang efisien untuk setiap kendaraan agar jarak tempuh total seminimal mungkin.
Pendekatan yang Digunakan:
- Clustering: Mengelompokkan TPS ke dalam beberapa klaster berdasarkan lokasi geografis menggunakan K-Means, dengan jumlah klaster = jumlah arm-roll truck tersedia.
- Constraint Handling: Menghitung total volume sampah dalam tiap klaster dan memastikan beban muatan tidak melebihi kapasitas truk (penyaringan ulang klaster).
- Routing Optimization: Untuk setiap klaster, urutan rute TPS dioptimalkan menggunakan:
    - Genetic Algorithm (GA): Algoritma evolusioner untuk menemukan rute optimal berdasarkan urutan titik.
    - Simulated Annealing (SA): Digunakan sebagai alternatif untuk menghindari solusi lokal dan memperbaiki hasil dari GA.
    - Ant Colony Optimization (ACO): Digunakan untuk eksplorasi rute secara graf-based melalui simulasi perilaku semut pencari jalur.

## Tools & Library
- Python 3
- `pandas`, `numpy`, `random`
- `sklearn.cluster.KMeans`
- `folium` (untuk visualisasi)
- `math` (untuk Haversine distance)

## Cara Menjalankan Program
1. Buka Google Colab
   Akses program melalui:
   [LINK Colab](https://colab.research.google.com/drive/1_H-QvKWbJtYxu17Z7ax4m5ZQlVGaOhpj)
2. Upload Dataset
   Upload file berikut:
   `SURABAYA PUSAT TPA BENOWO`
   ```python
   from google.colab import files
   uploaded = files.upload()
3. Jalankan Semua Sel
Tekan Runtime > Run all atau Ctrl + F9 untuk menjalankan semua tahapan:
  - Membaca dan memproses data lokasi
  - Menentukan jumlah klaster berdasarkan jumlah kendaraan
  - Menentukan rute optimal tiap klaster menggunakan Genetic Algorithm
  - Menampilkan rute dalam peta interaktif dengan Folium
