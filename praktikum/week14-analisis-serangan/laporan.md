# Laporan Praktikum Kriptografi
Minggu ke-: 14  
Topik: [Analisis Serangan Kriptografi]  
Nama: [Siti Kharisah]  
NIM: [230202787]  
Kelas: [5IKRA]  

---

## 1. Tujuan
1. Mengidentifikasi jenis serangan pada sistem informasi nyata.  
2. Mengevaluasi kelemahan algoritma kriptografi yang digunakan.  
3. Memberikan rekomendasi algoritma kriptografi yang sesuai untuk perbaikan keamanan.  

---

## 2. Dasar Teori
Analisis serangan kriptografi adalah studi tentang berbagai metode yang digunakan untuk melemahkan atau memecahkan sistem kriptografi tanpa mengetahui kunci rahasia secara langsung. Tujuannya adalah mengevaluasi tingkat keamanan suatu algoritma dan mengidentifikasi celah yang dapat dimanfaatkan penyerang. Serangan dapat menargetkan algoritma, protokol, maupun implementasinya.

Beberapa jenis serangan kriptografi yang umum antara lain brute force, ciphertext-only attack, known-plaintext attack, dan chosen-plaintext attack. Selain itu, terdapat serangan modern seperti side-channel attack yang memanfaatkan informasi fisik (waktu eksekusi, konsumsi daya) dan man-in-the-middle attack yang menyerang proses pertukaran kunci.

Analisis serangan kriptografi sangat penting dalam perancangan sistem keamanan agar algoritma dan protokol yang digunakan cukup kuat terhadap berbagai ancaman. Dengan memahami pola serangan, pengembang dapat memilih parameter yang aman dan menerapkan praktik keamanan yang tepat.
---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

---

## 5. Source Code
(Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:

```python
# contoh potongan kode
def encrypt(text, key):
    return ...
```
)

---

## 6. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/output.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 7. Jawaban Pertanyaan
1. Sistem lama rentan karena menggunakan algoritma usang, panjang kunci pendek, dan kata sandi lemah tanpa proteksi tambahan.
2. Kelemahan algoritma berasal dari desain matematisnya, sedangkan kelemahan implementasi berasal dari kesalahan penerapan meskipun algoritmanya aman.
3. Organisasi dapat menjaga keamanan dengan menggunakan algoritma modern, memperbarui sistem secara berkala, dan melakukan audit serta pengujian keamanan rutin.
---

## 8. Kesimpulan
Kesimpulan dari percobaan Analisis Serangan Kriptografi menunjukkan bahwa banyak celah keamanan muncul akibat penggunaan algoritma usang dan kesalahan implementasi. Percobaan ini menegaskan pentingnya pemilihan algoritma yang kuat serta konfigurasi yang benar. Dengan evaluasi dan pembaruan rutin, sistem kriptografi dapat tetap aman terhadap berbagai jenis serangan.

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
commit d0dfc226c74de05c90c946fd8392fbc16690580d
Author: sitikharisah18-bot <sitikharisah18@gmail.com>
Date:   Tue Jan 6 12:02:39 2026 +0700

    week14-analisis-serangan

```
