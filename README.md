Nama    : M.Fahmi Hadi Wijaya
NIM     : 251511016
Kelas   : 1A-D3

#Menjalankan program
1. pastikan sudah install pyhtonn
//bisa dengan ketik "pyhton --version" di terminal

2. install dependensi
 dengan klik "pyhton -m pip install nltk" di terminal

3. jalankan program dengan klik "pyhton vsm.py base.txt query1.txt" di terminal (begitu pula dengan query2 dan query3)


#penjelasan singkat algoritma

1. preprocessing: setiap dokumen diproses melalui 3 langkah, yyaitu dengan tokenisasi (memecah teks menjadi kata individual), pembersihan (menghapus stopwords atau kata umum seperti the, is, and dan lain-lain), dan stemming (mereduksi kata ke bentuk dasarnya menggunakan porter stemmer)

2. pembobotan TF-IDF: yaitu setiap term diberi bobot menggunakan rumus TF-IDF

3. cosine similarity: kemiripan antara query dan dokumen dihitung dengan cosine similarity

4. Ranking: dokumen diurutkan berdasarkan nilai similarity dari tertinggi ke terendah, serta hanya dokumen dengan nilai similarity >0.001 yang ditampilkan.


#contoh hasil keluaran program:
misal kita gunakan query2:
-output terminal:
=======================================================
 Information Retrieval
=======================================================

1. Inisialisasi
NTLK sudah terinstall
data nltk siap  digunakan

2. Membaca dokumen
  Ditemukan 10 dokumen: ['doc1.txt', 'doc2.txt', 'doc3.txt', 'doc4.txt', 'doc5.txt', 'doc6.txt', 'doc7.txt', 'doc8.txt', 'doc9.txt', 'doc10.txt']
  - doc1.txt: 34 term setelah preprocessing
  - doc2.txt: 33 term setelah preprocessing
  - doc3.txt: 31 term setelah preprocessing
  - doc4.txt: 34 term setelah preprocessing
  - doc5.txt: 32 term setelah preprocessing
  - doc6.txt: 27 term setelah preprocessing
  - doc7.txt: 28 term setelah preprocessing
  - doc8.txt: 28 term setelah preprocessing
  - doc9.txt: 26 term setelah preprocessing
  - doc10.txt: 31 term setelah preprocessing

3. Membangun inverted index & menghitung TF-IDF
  Total term unik: 172
Inverted index disimpan ke 'index.txt'
[OK] Bobot TF-IDF disimpan ke 'weights.txt'

4. Memproses query
  Query: cosine similarity document ranking
Hasil ranking disimpan ke 'response.txt'

=======================================================
  HASIL PENCARIAN
=======================================================
  Query : cosine similarity document ranking
  Dokumen relevan (similarity > 0.001): 5
-------------------------------------------------------
  Rank   Dokumen              Similarity
  ----   ------------------   ----------
  1      doc5.txt             0.1314
  2      doc1.txt             0.1281
  3      doc2.txt             0.1280
  4      doc4.txt             0.1203
  5      doc3.txt             0.0585
=======================================================

Semua file output berhasil dibuat
  - index.txt    : Inverted index
  - weights.txt  : Bobot TF-IDF per dokumen
  - response.txt : Hasil ranking dokumen