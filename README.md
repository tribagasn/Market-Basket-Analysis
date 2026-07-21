🛒 Market Basket Analysis using Association Rules
==================================================

📌 Project Overview
--------------------

Project ini bertujuan untuk menganalisis pola pembelian pelanggan menggunakan metode **Association Rule Mining** pada data transaksi retail. Analisis ini digunakan untuk menemukan hubungan antar produk yang sering dibeli bersamaan dalam satu transaksi.

Hasil analisis ini dapat membantu bisnis memahami pola pembelian pelanggan serta memberikan insight untuk strategi seperti **cross-selling, bundling produk, dan penataan produk di toko**.

Dari hasil analisis ditemukan bahwa kombinasi produk **sausage, whole milk, dan yogurt** memiliki nilai **lift tertinggi sebesar 2,183**, yang menunjukkan hubungan asosiasi yang cukup kuat dan berpotensi dimanfaatkan sebagai peluang strategi bisnis.

🎯 Problem Statement
---------------------

- Produk apa saja yang paling sering dibeli secara bersamaan oleh pelanggan?
- Aturan asosiasi apa yang memiliki nilai **support**, **confidence**, dan **lift** tertinggi?

❓ Business Question
---------------------

- Kombinasi produk apa yang paling potensial dijadikan bahan strategi **cross-selling** dan **product bundling**?
- Bagaimana pola transaksi pelanggan berdasarkan hari, bulan, dan segmen pelanggan?
- Produk apa yang menjadi kontributor penjualan terbesar dan perlu diprioritaskan ketersediaan stoknya?

🛠️ Tools & Tech Stack
------------------------

| Kategori | Tools |
|---|---|
| Bahasa Pemrograman | Python |
| Library Data Processing | Pandas, NumPy |
| Library Association Rule Mining | MLxtend (Apriori, TransactionEncoder) |
| Visualisasi | Matplotlib, Power BI |
| Environment | Jupyter Notebook |


⚙️ Method
-----------

1. **Data Understanding** — Memeriksa struktur, tipe data, dan statistik deskriptif dataset (`df_clean.info()`, `df_clean.describe()`). Dataset terdiri dari 38.765 baris dan 3 kolom: `Member_number`, `Date`, `itemDescription`.
2. **Data Cleaning** — Mengecek *missing value* (tidak ditemukan) dan *duplicate* (ditemukan 759 baris duplikat lalu dihapus), serta menyamakan format teks (huruf kecil, menghapus spasi berlebih).
3. **Feature Engineering** — Membuat `Transaction ID` (gabungan Member_number + Date), fitur waktu (year, month, day_of_week, is_weekend), `basket_size`, one-hot encoding untuk algoritma Apriori, serta segmentasi pelanggan (Occasional/Regular/One-time Buyer).
4. **Outlier Handling** — Mendeteksi outlier jumlah transaksi per member menggunakan metode IQR (54 member outlier ditemukan, tetap dipertahankan).
5. **Association Rules Mining** — Menerapkan algoritma **Apriori** untuk menghitung Support, Confidence, dan Lift dari setiap kombinasi produk.
6. **Visualisasi & Dashboard** — Menyajikan hasil analisis dalam dashboard Power BI yang mencakup tren transaksi, produk terlaris, proporsi segmen pelanggan, dan top association rules.


💡 Business Recommendations
-----------------------------

- **Optimalkan Persediaan Produk Terlaris** seperti *whole milk*, *other vegetables*, *rolls/buns*, dan *soda* agar stok selalu tersedia.
- **Terapkan Strategi Bundling dan Cross-selling** untuk kombinasi produk dengan lift tinggi, seperti *sausage, whole milk → yogurt*.
- **Optimalkan Product Placement** dengan menempatkan produk yang sering dibeli bersamaan pada rak yang berdekatan.
- **Tingkatkan Loyalitas Pelanggan** melalui program loyalitas dan promosi personalisasi, mengingat 64,64% pelanggan masih berstatus *Occasional Buyer*.
- **Sesuaikan Strategi Promosi dengan Pola Musiman**, mengingat transaksi memuncak pada bulan Agustus dan menurun pada bulan Februari.
- **Perluas Variasi Bundling Produk** berdasarkan kombinasi dengan nilai *confidence* dan *lift* tertinggi lainnya.

✅ Conclusion
--------------

Analisis data transaksi menunjukkan bahwa penjualan didominasi oleh produk kebutuhan sehari-hari, dengan **whole milk** sebagai produk terlaris, diikuti oleh *other vegetables*, *rolls/buns*, dan *soda*. Hal ini menegaskan bahwa produk kebutuhan pokok menjadi penggerak utama penjualan.

Dari sisi pelanggan, mayoritas merupakan **Occasional Buyer (64,64%)**, sementara pelanggan yang berbelanja secara rutin masih relatif sedikit. Pola transaksi bulanan cenderung stabil sepanjang tahun, dengan puncak pada Agustus (3.431 transaksi) dan titik terendah pada Februari (2.926 transaksi), menunjukkan adanya pola musiman yang bisa dimanfaatkan.

Hasil Market Basket Analysis mengidentifikasi kombinasi produk dengan asosiasi terkuat, yaitu **sausage, whole milk, dan yogurt** dengan nilai **Lift sebesar 2,183** — pelanggan yang membeli kombinasi ini memiliki peluang lebih dari dua kali lipat untuk membeli produk terkait dibandingkan pembelian secara acak. Temuan ini dapat menjadi dasar strategi *cross-selling*, *bundling*, dan penempatan produk untuk meningkatkan nilai transaksi dan penjualan secara keseluruhan.
