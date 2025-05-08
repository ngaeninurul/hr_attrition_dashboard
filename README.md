
# 🚪HR ATTRITION DASHBOARD📉


## 🏢 Business Understanding

**Jaya Jaya Maju** merupakan perusahaan multinasional yang telah berdiri sejak tahun 2000 dan memiliki lebih dari 1000 karyawan yang tersebar di berbagai wilayah. Meskipun perusahaan telah berkembang secara signifikan, mereka menghadapi tantangan serius terkait tingginya **attrition rate** atau tingkat karyawan keluar, yang telah melebihi 10%. Hal ini menimbulkan kekhawatiran akan stabilitas tim dan meningkatnya biaya rekrutmen serta pelatihan. Manajer HR membutuhkan insight berbasis data untuk memahami penyebab utama dari attrition ini dan untuk memonitor faktor-faktor risiko ke depan secara sistematis.

### Permasalahan Bisnis

Berikut adalah pertanyaan bisnis utama yang dijawab dalam proyek ini:

1. **Seberapa besar tingkat attrition perusahaan saat ini, dan bagaimana kondisi tenaga kerja secara keseluruhan?**
2. **Apa saja faktor yang paling berkontribusi terhadap risiko attrition, dan bagaimana pengaruhnya berdasarkan demografi karyawan?**
3. **Bagaimana proyeksi attrition berdasarkan masa kerja dan hasil model prediktif yang dikembangkan?**
4. **Apa karakteristik umum atau pola perilaku yang paling sering dimiliki oleh karyawan yang meninggalkan perusahaan (attrition)?**

### Cakupan Proyek

Cakupan proyek ini meliputi:

- Eksplorasi dan pembersihan data karyawan.
- Analisis deskriptif terhadap tingkat attrition secara keseluruhan.
- Identifikasi faktor-faktor utama yang berkontribusi terhadap risiko attrition.
- Pengembangan model prediksi attrition berbasis machine learning.
- Pembuatan business dashboard menggunakan **Metabase** untuk membantu manajer HR memantau attrition dan faktor risiko utama.
- Penyusunan rekomendasi strategis berbasis data untuk mendukung pengambilan keputusan manajemen SDM.

### Persiapan

**Sumber dataset:** [Jaya Jaya Maju - Employee Dataset](https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee)

**Setup Environment:**

Untuk melihat isi dashboard, gunakan aplikasi **Metabase** melalui Docker. Pastikan Docker telah terinstal.

1. Buka Command Prompt atau Terminal.
2. Jalankan perintah berikut untuk menyiapkan Metabase:
   ```bash
   docker pull metabase/metabase:v0.46.4
   ```

3. Jalankan Metabase:
   ```bash
   docker run -d -p 3000:3000 --name metabase-hr metabase/metabase
   ```

4. Akses melalui browser:
   ```
   http://localhost:3000
   ```

5. Login ke Metabase dengan:
   - Email: `root@mail.com`
   - Password: `root123`

6. (Opsional) Jika ingin menyalin database yang sudah berisi dashboard, jalankan perintah ini:
   ```bash
   docker cp metabase-hr:/metabase.db/metabase.db.mv.db ./
   ```


## 📊 Business Dashboard

Dashboard dibangun dengan menggunakan **Metabase** untuk membantu departemen HR:

- Menyediakan gambaran menyeluruh mengenai tingkat attrition perusahaan.
- Mengidentifikasi faktor utama yang menyebabkan karyawan keluar.
- Menyajikan insight demografis terkait risiko attrition.
- Memvisualisasikan tren attrition berdasarkan masa kerja dan proyeksi risiko ke depan dengan bantuan model prediksi.

## ✅ Conclusion

1. Dari **1.470 karyawan**, terdapat **179 kasus attrition** (keluar), menghasilkan **attrition rate sebesar 12,2%**. Ini menunjukkan tingkat turnover yang cukup tinggi dan dapat berdampak negatif pada stabilitas serta efisiensi SDM.
   
2. Faktor **Stock Option Level**, **Job Involvement**, **Environment Satisfaction**, dan **Age** terbukti menjadi penyebab utama attrition. Karyawan dengan job involvement rendah atau stock option tidak tersedia memiliki risiko lebih tinggi untuk keluar. Karyawan yang **belum menikah** dan berpendidikan **sarjana atau di bawahnya** lebih banyak mengalami attrition. Hal ini menunjukkan bahwa faktor demografis seperti status pernikahan dan latar belakang pendidikan mempengaruhi stabilitas kerja.

3. Attrition tertinggi terjadi pada karyawan dengan **masa kerja < 2 tahun**. Model prediksi yang dikembangkan juga menunjukkan bahwa **lembur berlebihan (Overtime)** dan **ketidakpuasan kerja** adalah indikator kuat untuk risiko attrition.

4. Karakteristik umum karyawan yang keluar meliputi:
   - **Job Involvement dan Environment Satisfaction rendah**
   - **Stock Option tidak tersedia**
   - **Berusia muda (<30 tahun)**
   - **Belum menikah**
   - **Masa kerja singkat (<3 tahun)**  
   Secara umum, mereka adalah karyawan yang belum menetap secara profesional maupun personal dan belum terikat secara emosional pada perusahaan.



## 🎯 Rekomendasi Actions

Berikut beberapa rekomendasi strategis berbasis data:

- **Program Retensi Awal:** Fokus pada karyawan dengan masa kerja <2 tahun melalui onboarding yang efektif, mentorship, dan pelatihan kerja.
- **Insentif Jangka Panjang:** Perluas pemberian stock option atau bonus loyalitas untuk meningkatkan retensi.
- **Peningkatan Keterlibatan:** Jalankan program peningkatan job involvement seperti feedback 360Â°, rekognisi tim, dan pelibatan dalam pengambilan keputusan.
- **Monitoring Proaktif:** Gunakan dashboard Metabase untuk memantau sinyal risiko attrition secara berkala.
- **Keseimbangan Kerja:** Tinjau kembali kebijakan overtime dan dorong budaya work-life balance yang sehat.



## ▶️ Menjalankan File Prediksi 

Untuk melakukan prediksi attrition menggunakan model yang telah dibuat, ikuti langkah berikut:

1. Siapkan folder project dan pastikan di dalamnya terdapat file berikut:
   - `prediction.py`
   - `model_prediction.pkl`
   - `features_le.pkl`
   - `input_prediction.csv` *(berisi data yang ingin diprediksi, dapat diubah)*

2. Buka terminal/CMD, lalu arahkan ke folder tempat file disimpan:
   ```bash
   cd path/to/folder

3. Jalankan script prediksi:
   ```bash
   python prediction.py
   
4. Setelah berhasil dijalankan, hasil prediksi akan otomatis tersimpan dalam file `output_prediction.csv`
