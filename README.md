# HR Analytics & Workforce Attrition Dashboard

## Overview
Sebuah *dashboard* Excel interaktif yang menganalisis metrik tenaga kerja HR dan pola pengunduran diri (*attrition*) karyawan menggunakan dataset IBM HR Analytics. Proyek ini mengubah data mentah HR menjadi wawasan visual strategis yang mencakup distribusi demografi, tingkat *turnover* per departemen, struktur gaji, dan dinamika masa kerja untuk mendukung strategi retensi talenta berbasis data.

<img width="1086" height="607" alt="HR Analytics Dashboard Preview" src="https://github.com/user-attachments/assets/2fe68064-8f3e-4a9a-b3b8-ece44983ee6e" />

---

## Business Questions Framework

| Dimensi | Pertanyaan Bisnis Utama |
| :--- | :--- |
| **Tenaga Kerja & Demografi** | • Berapa jumlah total karyawan, dan bagaimana distribusi tenaga kerja berdasarkan kelompok usia dan jenis kelamin?<br>• Departemen dan peran pekerjaan mana yang memiliki jumlah karyawan tertinggi? |
| **Attrition & Turnover** | • Berapa tingkat *attrition* karyawan secara keseluruhan (`AttritionNumeric`)?<br>• Departemen mana yang mengalami *turnover* karyawan tertinggi? |
| **Kompensasi** | • Bagaimana struktur total dan rata-rata pendapatan bulanan di seluruh organisasi? |

---

## Data Cleaning & Preparation
1. **Redundant Column Removal:** Menghapus kolom konstan yang bernilai tunggal dan tidak variatif (`EmployeeCount`, `Over18`, `StandardHours`).
2. **Missing Value Handling:** Memastikan integritas data tanpa adanya nilai kosong pada atribut krusial.
3. **Data Type Validation:** Memastikan ketepatan tipe data (numerik untuk pendapatan/usia, teks untuk kategori).
4. **Feature Engineering (`AttritionNumeric`):** Membuat kolom bantuan numerik (`1` jika *Attrition* = 'Yes', `0` jika 'No') untuk mempermudah perhitungan *Attrition Rate* pada Pivot Table.
5. **Grouping & Categorization:** Mengelompokkan usia ke dalam rentang kelompok umur (*Age Groups*) untuk analisis tren demografi.

---

## Visualizations & Dashboard Layout
- **KPI Cards:** Menampilkan *Total Employee* (1.470), *Total Monthly Income* ($9.55M), *Avg. Years at Company* (7.0 tahun), dan *Average Attrition Rate* (16,12%).
- **Employee Count by Age Group (Line Chart):** Mengidentifikasi konsentrasi usia karyawan puncak pada rentang 28–37 tahun.
- **Top 10 Job Roles by Employee Volume (Bar Chart):** Memvisualisasikan distribusi peran dengan *Sales Executive* dan *Research Scientist* sebagai jumlah terbanyak.
- **Attrition Count by Department (Column Chart):** Menunjukkan jumlah *turnover* tertinggi terjadi di departemen *Research & Development* (133) dan *Sales* (92).
- **Attrition Distribution (Doughnut Chart):** Menampilkan perbandingan rasio karyawan yang bertahan (83,88%) dan yang keluar (16,12%).

---

## Dataset Fields
- **Demographics & Work History:** `Age`, `Gender`, `MaritalStatus`, `Education`, `EducationField`, `TotalWorkingYears`, `YearsAtCompany`, `YearsInCurrentRole`, `YearsWithCurrManager`.
- **Job & Department Details:** `Department`, `JobRole`, `JobLevel`, `BusinessTravel`, `DistanceFromHome`.
- **Compensation & Performance:** `MonthlyIncome`, `PercentSalaryHike`, `PerformanceRating`, `StockOptionLevel`.
- **Attrition Target:** `Attrition` ('Yes'/'No') & `AttritionNumeric` (1/0).

---

## Tools Used
- **Microsoft Excel / Power Query:** Pembersihan data, transformasi tipe data, dan pembuatan *custom column*.
- **Pivot Tables & Pivot Charts:** Agregasi data interaktif dan pembuatan modul visualisasi.
- **Slicers & Dynamic Filters:** Filter interaktif berdasarkan *Department* dan *Gender*.

---

## Key Business Insights
1. **Tingkat Attrition:** Tingkat *turnover* organisasi sebesar **16,12%** (237 dari 1.470 karyawan).
2. **Turnover Berdasarkan Departemen:** Departemen **Sales** memiliki persentase tingkat *attrition* tertinggi (~20,6%), sedangkan **Research & Development** menyumbang jumlah kasus keluar terbanyak secara kuantitas (133 karyawan).
3. **Puncak Usia Kerja:** Mayoritas tenaga kerja berada pada kelompok usia **28–37 tahun**.

---

## Strategic Recommendations
1. **Fokus Retensi Sales & R&D:** Evaluasi beban kerja dan skema insentif untuk peran *Sales* dan *R&D* guna menekan tingkat kepindahan karyawan.
2. **Pengembangan Karir Jalur Tengah:** Buat program pengembangan karir yang jelas untuk kelompok usia produktif (28–37 tahun) agar tingkat keterikatan (*engagement*) tetap tinggi.
3. **Survei Kepuasan Kerja Periodik:** Lakukan evaluasi berkala terhadap faktor kompensasi dan jalur promosi untuk menjaga kestabilan *turnover* di bawah 10%.
