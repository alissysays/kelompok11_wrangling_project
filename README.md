
# README – Dokumentasi Dataset & Transformasi Data

## 1. Definisi Umum
### **GWh**  
Satuan energi yang menunjukkan total listrik sebesar satu miliar watt yang digunakan, didistribusikan, atau dihasilkan selama satu jam.

---

## 2. Dataset Pelanggan (BPS, 2020–2023)

- **df1 (Pelanggan 2020)** – BPS  
  Distribusi listrik (GWh) berdasarkan kelompok pelanggan tahun 2020.

- **df2 (Pelanggan 2021)** – BPS  
  Distribusi listrik berdasarkan kelompok pelanggan tahun 2021.

- **df3 (Pelanggan 2022)** – BPS  
  Distribusi listrik berdasarkan kelompok pelanggan tahun 2022.

- **df4 (Pelanggan 2023)** – BPS  
  Distribusi listrik berdasarkan kelompok pelanggan tahun 2023.

- **df_cust** – Gabungan df1–df4  
  Dataset empat tahun yang digabung menggunakan *outer join* pada kolom **Kelompok Pelanggan – PLN**.

---

## 3. Dataset Provinsi (BPS, 2020–2023)

- **df1 (Provinsi 2020)** – BPS  
  Distribusi listrik (GWh) berdasarkan provinsi tahun 2020.

- **df2 (Provinsi 2021)** – BPS  
  Distribusi listrik provinsi tahun 2021.

- **df3 (Provinsi 2022)** – BPS  
  Distribusi listrik provinsi tahun 2022.

- **df4 (Provinsi 2023)** – BPS  
  Distribusi listrik provinsi tahun 2023.

- **df_c1–df_c4**  
  Versi pembersihan tiap dataframe (normalisasi nama provinsi + konversi GWh ke numerik).

- **df_prov**  
  Gabungan df_c1–df_c4 menggunakan *outer join*.

---

## 4. Dataset PLN (PDF PLN 2020–2023)

- **df1 (PLN 2020)**  
  Tabel hasil ekstraksi PDF PLN 2020 yang telah dirapikan.

- **df2 (PLN 2021)**  
  Tabel hasil ekstraksi PDF PLN 2021 yang telah dirapikan.

- **df3 (PLN 2022)**  
  Tabel hasil ekstraksi PDF PLN 2022 yang telah dirapikan.

- **df4 (PLN 2023)**  
  Tabel hasil ekstraksi PDF PLN 2023 yang telah dirapikan.

- **df_pln_gabungan**  
  Gabungan data PLN 2020–2023 yang telah distandarkan.

---

## 5. Dataset ESDM (2020–2023)

- **df1 (ESDM 2020)**  
  Rekonstruksi tabel ESDM dari dua halaman PDF.

- **df2 (ESDM 2021)**  
  Rekonstruksi tabel ESDM 2021 dari dua halaman PDF.

- **df3 (ESDM 2022)**  
  Rekonstruksi tabel ESDM 2022 dari dua halaman PDF.

- **df4 (ESDM 2023)**  
  DataFrame dari file Excel ESDM 2023 yang telah distandarkan.

- **df_esdm2**  
  Gabungan tiga tahun (2020–2022) setelah menghapus 12 baris awal yang tidak relevan.

- **df_esdm_final**  
  Gabungan ESDM 2020–2023 melalui *left join*.

---

## 6. Dataset Transformasi untuk Analisis

- **df_total_melted** dari df_cust  
  Total distribusi listrik nasional per tahun (format long). Disimpan dalam file berformat CSV Bernama tren konsumsi listrik .csv

- **df_melt** dari df_cust  
  Distribusi GWh per kelompok pelanggan (format long). Disimpan dalam file berformat CSV bernama tren konsumsi per pelanggan .csv

- **df_filtered** dari df_cust  
  Distribusi listrik 2023 tanpa baris total. Disimpan dalam file berformat CSV Bernama proporsi_pelanggan.csv

- **df_box_melted** dari df_prov  
  Distribusi listrik provinsi 2020–2023 (long format). Disimpan dalam file berformat CSV bernama konsumsi listrik 2020-2023.csv

- **df_melted** dari df_pln_gabungan  
  Distribusi listrik 2023 per provinsi per segmen pelanggan. Disimpan dalam file berformat CSV Bernama konsumsi listrik per sektor 2023.csv dan konsumsi listrik per provinsi 2023.csv

- **df_merged** dari df_esdm + df_prov  
  Gabungan pendapatan listrik (Rp) dan distribusi (GWh) 2023, termasuk rasio Rp/GWh. Disimpan dalam file berformat CSV Bernama rasio pendapatan 2023.csv

- **df_corr_data** dari df_pln_gabungan  
  Dataset GWh enam segmen pelanggan untuk analisis korelasi tahun 2023. Disimpan dalam file berformat CSV Bernama corr_data_2023.csv.
