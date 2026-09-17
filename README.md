# 🚚 Supply Chain Analysis & Dashboard

## 📌 Project Overview

Proyek ini merupakan **hands-on project** untuk menerapkan konsep analisis data dan dashboard menggunakan **Google Sheets** dan **Google Looker Studio**.

Dataset yang digunakan merupakan data **Supply Chain Analysis** dari Kaggle yang terdiri dari **100 records** dengan informasi mengenai penjualan, produk, inventory, supplier, manufacturing, shipping, hingga quality control.

Dalam proyek ini, saya melakukan proses **data preparation, data transformation, data analysis, data visualization, dan dashboard development** untuk memahami performa penjualan, profitabilitas produk, kualitas produksi, supplier, serta aktivitas logistik dan pengiriman.

Dashboard dibuat secara interaktif menggunakan Google Looker Studio dengan beberapa filter berdasarkan **Product Type, Inspection Results, Supplier Name, dan Transportation Modes**.

📎 **Dataset Source:** [Supply Chain Analysis – Kaggle](https://www.kaggle.com/datasets/harshsingh2209/supply-chain-analysis/suggestions)

---

## 🗂️ Dataset

- **Dataset:** Supply Chain Analysis
- **Source:** Kaggle
- **Format:** CSV
- **Records:** 100
- **Columns:** 24

Dataset berisi informasi yang berkaitan dengan beberapa aspek supply chain, meliputi:

- Product Type
- SKU
- Customer Demographics
- Price
- Number of Products Sold
- Revenue Generated
- Stock Levels
- Availability
- Order Quantities
- Supplier Name
- Location
- Production Volumes
- Manufacturing Lead Time
- Manufacturing Costs
- Lead Time
- Shipping Carriers
- Transportation Modes
- Routes
- Shipping Times
- Shipping Costs
- Lead Times
- Inspection Results
- Defect Rates
- Costs

---

## 🛠️ Data Preparation & Analysis

Sebelum membuat dashboard di Looker Studio, dataset CSV terlebih dahulu diunggah ke **Google Sheets** untuk dilakukan proses data preparation dan transformation.

### Data Preparation

Beberapa proses yang saya lakukan meliputi:

- Mengunggah dataset CSV dari Kaggle ke Google Sheets.
- Memeriksa struktur dan format setiap kolom.
- Melakukan transformasi data di Google Sheets.
- Menyesuaikan format data sesuai kebutuhan analisis.
- Mengunggah data yang telah dipersiapkan ke Google Looker Studio.
- Melakukan pengecekan ulang format data setelah data digunakan sebagai data source di Looker Studio.

### Calculated Fields

Untuk menghasilkan beberapa metric tambahan yang digunakan dalam dashboard, saya membuat **Calculated Field** di Google Looker Studio.

#### Net Profit

Net Profit dihitung dengan mengurangi total revenue dengan manufacturing costs, shipping costs, dan costs.

    SUM(Revenue generated) - (SUM(Manufacturing costs) + SUM(Shipping costs) + SUM(Costs))

#### Gross Profit Margin (%GPM)

Gross Profit Margin dihitung berdasarkan perbandingan Net Profit terhadap total revenue.

    Net Profit / SUM(Revenue generated)

#### % Defect Rate

Untuk mendapatkan rata-rata defect rate dalam bentuk persentase pada dashboard, digunakan formula:

    AVG(Defect rates) / 100

Calculated fields tersebut kemudian digunakan sebagai metric dalam dashboard untuk membantu analisis performa keuangan dan kualitas produk.

---

# 📊 Dashboard Highlights & Key Insights

## 1️⃣ Executive Summary & Business Performance

Dashboard menyediakan beberapa KPI utama untuk memberikan gambaran umum mengenai performa supply chain.

### 🔍 Key Insight

Berdasarkan hasil analisis:

- **Revenue:** $577,605
- **Total Profit:** $519,399
- **Gross Profit Margin:** 89.92%
- **Total Products Sold:** 46,099 unit
- **Average Defect Rate:** 2.28%

KPI tersebut digunakan sebagai ringkasan awal untuk melihat performa keuangan, volume penjualan, dan kualitas produk secara keseluruhan.

---

## 2️⃣ Sales Performance & Product Analysis

Bagian ini digunakan untuk menganalisis performa penjualan berdasarkan lokasi dan kategori produk.

Analisis yang ditampilkan meliputi:

- Revenue & Sales Volume by Location
- Revenue & Net Profit by Product Type
- Revenue & Net Profit by Product Type across Locations

### 🔍 Key Insight

Berdasarkan hasil analisis:

- **Mumbai** mencatatkan revenue sebesar **$137,755.03** dengan volume penjualan sebanyak **9,426 unit**.
- **Skincare** memiliki revenue sebesar **$241,628.16** dan net profit sebesar **$217,242.73**.
- Berdasarkan kombinasi lokasi dan product type, **Skincare di Mumbai** menghasilkan net profit sebesar **$40,513.91**.

Analisis ini digunakan untuk melihat perbedaan performa penjualan berdasarkan lokasi serta kontribusi masing-masing kategori produk terhadap revenue dan profit.

---

## 3️⃣ Quality Control & Production Risk

Bagian ini digunakan untuk melihat kondisi kualitas produk berdasarkan defect rate dan hasil inspeksi.

Analisis yang ditampilkan meliputi:

- Defect Rates by Product Type
- Inspection Results by Product Type

### 🔍 Key Insight

Berdasarkan hasil analisis:

- **Haircare** memiliki defect rate sebesar **2.48%**.
- **Skincare** memiliki defect rate sebesar **2.33%**.
- **Cosmetics** memiliki defect rate sebesar **1.92%**.
- **Skincare** memiliki jumlah status *Fail* sebanyak **13 kasus**.
- **Skincare** juga memiliki jumlah status *Pass* tertinggi dibandingkan kategori produk lainnya.

Analisis ini membantu melihat perbedaan tingkat defect dan hasil inspeksi antar kategori produk.

---

## 4️⃣ Manufacturing & Supplier Analysis

Bagian ini digunakan untuk melihat perbedaan manufacturing cost dan manufacturing lead time berdasarkan supplier.

Analisis yang ditampilkan meliputi:

- Manufacturing Lead Time by Supplier
- Manufacturing Costs by Supplier

### 🔍 Key Insight

Berdasarkan hasil analisis:

- **Supplier 1** memiliki manufacturing cost sebesar **$1,221.86**.
- **Supplier 3** memiliki manufacturing cost sebesar **$654.51**.
- **Supplier 1** memiliki manufacturing lead time rata-rata **12.59 hari**.
- **Supplier 5** memiliki manufacturing lead time rata-rata **16.33 hari**.

Analisis ini digunakan untuk membandingkan biaya produksi dan waktu produksi antar supplier.

> **Note:** Perbandingan manufacturing cost dan lead time dalam proyek ini hanya menunjukkan kondisi berdasarkan data yang tersedia dan tidak digunakan untuk menentukan supplier terbaik secara keseluruhan.

---

## 5️⃣ Shipping & Logistics Analysis

Bagian ini digunakan untuk menganalisis waktu dan biaya pengiriman berdasarkan shipping carrier dan transportation mode.

Analisis yang ditampilkan meliputi:

- Shipping Times by Shipping Carrier & Transportation Mode
- Shipping Costs by Shipping Carrier & Transportation Mode

### 🔍 Key Insight

Berdasarkan hasil analisis:

- Kombinasi **Carrier B + Air** memiliki rata-rata shipping time sebesar **4.21 hari**.
- Kombinasi **Carrier A + Rail** memiliki rata-rata shipping time sebesar **5.60 hari**.
- Kombinasi **Carrier A + Sea** memiliki rata-rata shipping cost sebesar **$3.88**.
- Kombinasi **Carrier C + Road** memiliki rata-rata shipping cost sebesar **$6.55**.

Analisis ini digunakan untuk melihat perbedaan waktu dan biaya pengiriman berdasarkan kombinasi shipping carrier dan transportation mode.

---

# 🖼️ Dashboard Preview

![Supply Chain Dashboard Preview](Supply%20Chain%20-%20Dashboard.jpeg)

📊 **[View Interactive Dashboard in Google Looker Studio](https://datastudio.google.com/reporting/98648ab2-d2a8-4629-8bfa-72b2b8ccf637)**

📄 **[View Full Dashboard in High-Resolution PDF](./Supply_Chain_Report.pdf)**

---

# 📁 Project Structure

**supply_chain_dataset.csv:** Berisi dataset supply chain yang digunakan sebagai sumber data analisis.

**Supply Chain - Dashboard.jpeg:** Berisi preview dashboard.

**Supply_Chain_Report.pdf:** Berisi versi PDF dari dashboard yang dibuat menggunakan Google Looker Studio.

**README.md:** Berisi dokumentasi proyek, proses data preparation, calculated fields, analisis, key insights, dan project takeaways.

---

# 🧰 Tools & Skills Demonstrated

### Tools

- Google Sheets
- Google Looker Studio

### Skills & Techniques

- Data Preparation
- Data Transformation
- Dimension & Metric Configuration
- Data Aggregation
- Calculated Field
- Sales Analysis
- Revenue Analysis
- Profit Analysis
- Product Performance Analysis
- Quality Analysis
- Supplier Analysis
- Manufacturing Analysis
- Shipping & Logistics Analysis
- Data Visualization
- Dashboard Development
- Data Interpretation

---

# 🎯 Project Takeaways

Melalui proyek ini, saya berlatih menerapkan konsep **data analysis dan dashboard development secara mandiri** menggunakan dataset supply chain.

Berbeda dengan project sebelumnya yang mengikuti learning materials, pada project ini saya mencoba menentukan sendiri aspek yang ingin dianalisis, memilih metric dan dimension yang sesuai, membuat calculated field, serta menginterpretasikan hasil visualisasi.

Project ini juga membantu saya memahami bahwa proses analisis tidak hanya berkaitan dengan pembuatan dashboard, tetapi juga dengan menentukan **pertanyaan analisis, metric yang digunakan, aggregation, dan cara menginterpretasikan pola yang ditemukan dalam data**.

Secara keseluruhan, proses yang saya lakukan dalam proyek ini adalah:

**Raw Data → Data Preparation → Data Transformation → Data Analysis → Calculated Field → Data Visualization → Dashboard Development → Insight**

---

# 👤 Author

**Alena Mansika**

- 💻 **GitHub:** [@alenamansika](https://github.com/alenamansika)
- 💼 **LinkedIn:** [Alena Mansika](https://www.linkedin.com/in/alenamansika)
