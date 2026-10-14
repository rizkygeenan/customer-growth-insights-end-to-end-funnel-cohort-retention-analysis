# 📊 Strategic Growth Insights via Funnel & Cohort Analysis

Welcome to the **Strategic Growth Insights** repository! This project analyzes user acquisition, activation, conversion drop-offs, and long-term customer retention using **Funnel Analysis** and **Cohort Analysis**. 

---

## 📌 Executive Summary
Understanding user flow through a product or service is critical for scaling business growth. While **Funnel Analysis** helps identify where users drop off during their journey, **Cohort Analysis** reveals how user behavior and retention evolve over time. 

By combining both frameworks, this project provides a holistic view of user lifecycle performance and delivers data-backed strategic recommendations to boost conversion and retention rates.

---

## 🎯 Project Objectives
1. **Build & Measure Business Funnels:** Map key conversion stages (e.g., *Visit → Add to Cart → Checkout → Purchase*) and evaluate conversion/drop-off metrics.
2. **Cohort Analysis & Retention Tracking:** Group users by signup cohort to calculate monthly/weekly retention rates and analyze cohort trends.
3. **Calculated Field Implementation:** Formulate metrics such as *Conversion Rate (CR)*, *Drop-off Rate*, *Retention Rate*, and *Revenue per User*.
4. **Interactive Dashboard & Visualization:** Develop clear, structured visualizations using **Power BI** / **Google Colab**.
5. **Strategic Business Recommendations:** Formulate actionable strategies to address friction points and optimize growth.

---

## 🛠️ Tools & Technologies
- **Data Manipulation & Analysis:** Python (Pandas, NumPy) on **Google Colaboratory**
- **Data Visualization & Dashboarding:** **Power BI** / Matplotlib & Seaborn
- **Calculated Fields / Measures:** DAX (Power BI) & Pandas Analytics

---

## 📂 Data & Workflow Architecture

### 1. Funnel Analysis Architecture
The primary business funnel evaluated follows these key conversion stages:
1. **Stage 1: Session / Visit** (Top of Funnel - Acquisition)
2. **Stage 2: Product View / Add to Cart** (Middle of Funnel - Intent)
3. **Stage 3: Checkout / Payment Details** (Middle of Funnel - Evaluation)
4. **Stage 4: Successful Purchase** (Bottom of Funnel - Conversion)

#### Key Funnel Metrics & Formulas:
$$\text{Conversion Rate (Stage } N) = \left( \frac{\text{Users in Stage } N}{\text{Users in Stage } N-1} \right) \times 100\%$$

$$\text{Drop-off Rate (Stage } N) = 100\% - \text{Conversion Rate (Stage } N)$$

---

### 2. Cohort Analysis Architecture
Users are categorized into cohorts based on their **First Acquisition / Signup Month** (e.g., *2026-01, 2026-02, etc.*) and tracked over subsequent time periods ($M_0, M_1, M_2, \dots, M_n$).

#### Retention Rate Formula:
$$\text{Retention Rate } (M_n) = \left( \frac{\text{Active Users in Month } n}{\text{Total Cohort Size at Month } 0} \right) \times 100\%$$

---

## 📐 Calculated Fields Reference

| Field Name | Expression / Formula | Business Purpose |
| :--- | :--- | :--- |
| **Stage Conversion Rate** | `DIVIDE([Users Current Stage], [Users Previous Stage], 0)` | Identifies friction points between sequential funnel stages. |
| **Overall Funnel CR** | `DIVIDE([Purchased Users], [Total Visitors], 0)` | Measures end-to-end acquisition efficiency. |
| **Cohort Retention Rate** | `DIVIDE([Active Users Period N], [Initial Cohort Size Period 0], 0)` | Evaluates product-market fit and long-term user stickiness. |
| **ARPU (Revenue per User)**| `DIVIDE(SUM([Total Revenue]), COUNT DISTINCT([User ID]), 0)` | Tracks monetization health across cohorts. |

---

## 📈 Key Findings & Strategic Insights

### 1. Top Funnel Drop-off Point (Education Startup)
- **Drop-off Terbesar:** Terjadi pada transisi dari **Bookings → Free Trials** dengan tingkat kehilangan (*drop-off rate*) sebesar **37,3%** (hanya **62,7%** pengguna dari *Bookings* yang berlanjut ke *Free Trials*).
- **Penyebab Utama:**
  - **Kendala Jadwal:** Bentrok waktu, lupa, atau kehilangan momentum saat sesi uji coba.
  - **Minim Reminder:** Pengingat (WhatsApp/Email) belum optimal, menyebabkan tingkat kehadiran rendah.
  - **Ekspektasi vs Realita:** Keraguan calon pengguna/orang tua terhadap materi atau format kelas.
  - **Friction Onboarding:** Langkah teknis masuk ke platform *Free Trial* terlalu rumit.

### 2. Cohort Retention Pattern (Fintech 2024)
- **Stabilitas Jan 2024:** Mendominasi dengan 115 pengguna dan mempertahankan retensi jangka panjang yang sangat kuat sebesar **52,2%** pada Bulan ke-11 ($M_{11}$), menunjukkan *product-market fit* yang kokoh di awal tahun.
- **Volatilitas Pertengahan Tahun:** *Cohort* antara Feb–Nov mengalami penurunan ukuran sampel (5–15 pengguna), memicu volatilitas statistik dan kurva retensi yang rentan.
- **Penurunan Des 2024:** Retensi awal ($M_0$) turun tajam menjadi **37,3%** untuk 51 pelanggan baru, mengindikasikan adanya hambatan *onboarding* atau kualitas *traffic* yang lebih rendah di akhir tahun.
- **Rata-rata Retensi $M_1$:** Berada di kisaran **56,9%**.

---

## 💡 Strategic Recommendations

### 1. Optimize Middle-Funnel Friction (Funnel Optimization)
- **Action:** Terapkan pengingat otomatis multi-saluran (WhatsApp & *push notification*) pada 24 jam dan 1 jam sebelum *Free Trial*, serta sederhanakan alur teknis bergabung dengan tautan satu klik.
- **Impact:** Mengurangi tingkat *drop-off* 37,3% pada tahap *Free Trial* dan mengoptimalkan *Overall Conversion Rate*.

### 2. Targeted Onboarding & Early Retention Programs
- **Action:** Perbaiki *funnel onboarding* untuk *cohort* akhir tahun (misalnya Desember) serta replikasi saluran akuisisi dan *engagement loop* sukses dari *cohort* Januari.
- **Impact:** Mendongkrak retensi awal dari 37,3% dan mempercepat waktu konversi (*Time to Conversion*).

### 3. Re-engagement Campaign for Attrition Cohorts
- **Action:** Terapkan program loyalitas dengan menyebarkan *cashback* kondisional atau pencapaian hadiah (*reward milestones*) antara Bulan ke-3 hingga ke-6.
- **Impact:** Mencegah penurunan retensi yang tajam (*churn*) dan memperpanjang *Customer Lifetime Value* (CLV).
---

## 🧠 Reflection Questions

### 1. Mengapa Funnel Analysis saja tidak cukup untuk memahami pertumbuhan bisnis?
> *Funnel Analysis* hanya memberikan gambaran kuantitatif secara statis (*snapshot*) tentang bagaimana pengguna bergerak dalam satu alur transaksi instan. Funnel tidak mengukur retensi jangka panjang, nilai ulangan (*repeat order*), atau loyalitas pelanggan. Sebuah bisnis bisa memiliki konversi funnel yang tinggi tetapi tetap bangkrut jika seluruh penggunanya mengalami *churn* setelah pembelian pertama.

### 2. Apa insight tambahan yang diberikan Cohort Analysis dibanding Funnel Analysis?
> *Cohort Analysis* menambahkan dimensi **waktu** dan **perilaku kelompok**. Dampak dari perubahan produk, efektivitas kampanye pemasaran di waktu tertentu, serta tingkat retensi jangka panjang pelanggan dari waktu ke waktu dapat diukur secara akurat melalui matriks cohort.

### 3. Jika conversion tinggi tetapi retention rendah, apa implikasinya bagi bisnis?
> Implikasinya adalah bisnis terjebak dalam fenomena **"Leaky Bucket"** (Ember Bocor). Bisnis harus terus-menerus membelanjakan biaya akuisisi (*Customer Acquisition Cost / CAC*) yang mahal untuk mendapatkan pengguna baru karena pengguna lama tidak kembali. Hal ini membuat model bisnis menjadi tidak berkelanjutan (*unscalable*) dan menekan *Customer Lifetime Value (LTV)*.

---

## 📸 Dashboard Preview

### Customer Funnel
<img width="871" height="486" alt="customer-funnel" src="https://github.com/user-attachments/assets/30a09438-06af-4bb6-984a-e9985b0c9cd0" />

### Cohort
<img width="831" height="447" alt="cohort" src="https://github.com/user-attachments/assets/ca129b25-4f3a-4937-9e4e-60ae05f7f47a" />

---

## 👤 Author

- **Nama**: Muhammad Rizky Ginanjar
- **Role**: Data Analyst
- **LinkedIn**: [Muhammad Rizky Ginanjar](https://www.linkedin.com/in/rizkyginan/)
