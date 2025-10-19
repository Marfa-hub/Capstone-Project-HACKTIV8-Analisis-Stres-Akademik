Capstone Project: Analisis Faktor Stres Akademik Mahasiswa By: Muhammad Ardi Fajar
Bagian 1: AI Support Explanation (Penjelasan Dukungan AI)
Bagian ini mendokumentasikan proses iteratif dalam penyempurnaan prompt dan parameter model AI (IBM Granite) untuk mencapai hasil analisis yang optimal, sesuai dengan template logbook.

Entri 1: Klasifikasi Baseline (Zero-Shot)
Task or goal: Melakukan klasifikasi awal (baseline) pada data mahasiswa untuk memprediksi Kategori Stres (Stres Rendah, Stres Sedang, Stres Tinggi).
Prompt details: Klasifikasikan mahasiswa berikut sebagai Stres Rendah, Stres Sedang, atau Stres Tinggi: Mahasiswa 1: {'academic_stage': 'undergraduate', 'peer_pressure': 2, ...} Mahasiswa 2: {'academic_stage': 'high school', 'peer_pressure': 4, ...} Mahasiswa 3: {'academic_stage': 'undergraduate', 'peer_pressure': 3, ...}
Parameter settings: Default
Strengths: Prompt berhasil dieksekusi oleh model.
Weaknesses: Ini adalah prompt "zero-shot" (tanpa contoh). AI diminta menebak tanpa diberi panduan, sehingga akurasinya tidak dapat diandalkan dan berisiko tinggi salah.
Adjustments made: -
Observed outcomes: Model memberikan klasifikasi, namun keakuratannya diragukan.
Future recommendations: Menyempurnakan prompt dengan memberikan contoh jawaban yang benar (few-shot learning) untuk "mengajari" model.

Entri 2: Klasifikasi Refined (Few-Shot)
Task or goal: Meningkatkan akurasi klasifikasi Kategori Stres dengan prompt yang disempurnakan.
Prompt details: Tugas: Klasifikasikan 'Kategori Stres' ... Ikuti contoh format di bawah ini. --- CONTOH --- Faktor: {'academic_stage': 'undergraduate', 'peer_pressure': 4, ...} Kategori Stres: Stres Tinggi Faktor: {'academic_stage': 'undergraduate', 'peer_pressure': 2, ...} Kategori Stres: Stres Sedang Faktor: {'academic_stage': 'high school', 'peer_pressure': 1, ...} Kategori Stres: Stres Rendah --- DATA UJI --- Faktor: {'academic_stage': 'undergraduate', 'peer_pressure': 3, ...} Kategori Stres:
Parameter settings: Default
Strengths: Akurasi prediksi meningkat drastis. Dengan melihat 3 contoh, model AI dapat memahami pola dan memberikan klasifikasi yang benar pada data uji.
Weaknesses: Masih menggunakan parameter default, output AI mungkin masih bisa lebih dioptimalkan.
Adjustments made: Prompt diubah dari "zero-shot" menjadi "few-shot" dengan menambahkan 3 contoh data dan jawaban yang benar.
Observed outcomes: Model AI berhasil memprediksi data uji dengan benar, sesuai dengan jawaban yang sebenarnya.
Future recommendations: Menerapkan proses iteratif yang sama (baseline vs refined) untuk tugas rangkuman.

Entri 3: Rangkuman Baseline
Task or goal: Membuat rangkuman awal (baseline) dari temuan data statistik.
Prompt details: Tugas: Anda adalah seorang analis data. Baca "transkrip" temuan analisis data di bawah ini dan buatkan rangkuman (summary) dalam 3 poin utama (bullet points) yang menyoroti wawasan paling penting bagi seorang dekan universitas. --- Transkrip Temuan Data --- [Distribusi Kategori Stres: Stres Tinggi: 60.4%, Stres Sedang: 20.9%, ...] [Rata-rata Faktor per Kategori Stres: Untuk Stres Tinggi: Peer Pressure: 3.5, Home Pressure: 4.1, ...] --- Akhir Transkrip --- Rangkuman 3 Poin Utama:
Parameter settings: Default
Weaknesses: Prompt terlalu umum ("wawasan paling penting"). Rangkuman yang dihasilkan AI mungkin benar, tetapi tidak tajam dan kurang fokus pada insight spesifik yang dapat ditindaklanjuti.
Adjustments made: -
Observed outcomes: Model memberikan rangkuman umum tentang temuan data.
Future recommendations: Menyempurnakan prompt agar lebih spesifik dan menyesuaikan parameter model untuk mengontrol output.

Entri 4: Rangkuman Refined + Penyesuaian Parameter
Task or goal: Membuat rangkuman yang sangat tajam, ringkas, dan actionable (dapat ditindaklanjuti).
Prompt details: Tugas: ... buatkan rangkuman (summary) dalam 3 poin utama (bullet points). Pastikan rangkuman Anda SANGAT TAJAM dan FOKUS pada:
Kategori stres mana yang paling banyak dialami mahasiswa.
Faktor tekanan spesifik apa yang paling menonjol pada kelompok 'Stres Tinggi'.
Wawasan penting lainnya yang bisa ditindaklanjuti oleh seorang dekan. --- Transkrip Temuan Data --- [...] --- Akhir Transkrip --- Rangkuman 3 Poin Utama yang Telah Difokuskan:
Parameter settings: max_tokens: 100, top_k: 10, top_p: 0.7, repetition_penalty: 1.2
Strengths: Kombinasi prompt yang sangat spesifik dan parameter yang ketat (mengurangi max_tokens dan kreativitas top_k/top_p) memaksa AI menghasilkan rangkuman yang jauh lebih baik, fokus, dan relevan sesuai kebutuhan.
Adjustments made: 1. Prompt disempurnakan untuk fokus pada 3 poin spesifik. 2. Parameter model disesuaikan untuk mengontrol panjang dan fokus output.
Observed outcomes: Model AI menghasilkan rangkuman yang ringkas dan tajam, yang langsung menyoroti masalah utama (mayoritas stres tinggi, didorong oleh kompetisi dan tekanan rumah).
Future recommendations: -
Bagian 2: Insight, Findings, & Recommendations
Bagian ini menjelaskan temuan utama dari analisis data dan memberikan rekomendasi yang dapat ditindaklanjuti berdasarkan temuan tersebut.
Insight & Findings (Wawasan & Temuan) Berdasarkan analisis klasifikasi dan rangkuman yang didukung oleh AI, tiga temuan utama teridentifikasi dari data 139 mahasiswa:
Stres Akademik Mayoritas Berada di Level Tinggi: Hasil rangkuman AI terhadap data statistik menunjukkan bahwa mayoritas mahasiswa (63.3%) berada dalam kategori 'Stres Tinggi'. Ini menunjukkan bahwa stres akademik adalah masalah signifikan dan umum di kalangan responden.
Kompetisi & Tekanan Rumah adalah Pendorong Utama Stres Tinggi: Analisis lebih lanjut yang dirangkum oleh AI mengidentifikasi bahwa pada kelompok 'Stres Tinggi', faktor pendorong utamanya adalah 'competition' (rata-rata 3.70 dari 5) dan 'home_pressure' (rata-rata 3.43 dari 5).
Tekanan Teman Sebaya Memiliki Dampak Terkecil: Menariknya, 'peer_pressure' (tekanan teman sebaya) memiliki rata-rata yang relatif lebih rendah (3.38) di kelompok 'Stres Tinggi' dibandingkan dua faktor lainnya.

Conclusion & Recommendations (Kesimpulan & Rekomendasi) Kesimpulan: Stres akademik di kalangan mahasiswa berada pada tingkat yang mengkhawatirkan, didorong terutama oleh tingginya persaingan akademik dan tekanan yang berasal dari rumah.
Rekomendasi: Berdasarkan temuan tersebut, dua rekomendasi spesifik diajukan untuk pihak universitas: 
a. Mengelola Ekspektasi Kompetisi: Mengembangkan program atau lokakarya bagi mahasiswa yang berfokus pada "Persaingan Akademik yang Sehat", manajemen waktu, dan strategi koping (selain emotional breakdown), untuk membantu mereka mengelola stres yang berasal dari 'competition'. 
b. Melibatkan dan Mengedukasi Orang Tua: Membuat program/seminar (misalnya saat orientasi mahasiswa baru) yang ditujukan kepada orang tua. Program ini harus memberikan edukasi tentang dampak 'home_pressure' dan memberikan panduan bagi orang tua tentang cara terbaik mendukung perjalanan akademik anak mereka secara positif tanpa menimbulkan stres yang berlebihan.

tautan raw dataset: https://www.kaggle.com/datasets/grandmaster07/student-stress-levels-dataset
