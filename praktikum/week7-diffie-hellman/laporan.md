# Laporan Praktikum Kriptografi
Minggu ke-: 7
Topik: [Diffie-Hellman Key Exchange]  
Nama: [Siti Kharisah]  
NIM: [230202787]  
Kelas: [5IKRA]  

---

## 1. Tujuan
(Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Melakukan simulasi protokol **Diffie-Hellman** untuk pertukaran kunci publik.  
2. Menjelaskan mekanisme pertukaran kunci rahasia menggunakan bilangan prima dan logaritma diskrit.  
3. Menganalisis potensi serangan pada protokol Diffie-Hellman (termasuk serangan **Man-in-the-Middle / MITM**).  .)

---

## 2. Dasar Teori
Diffie-Hellman Key Exchange adalah metode kriptografi yang digunakan untuk memungkinkan dua pihak berbagi kunci rahasia melalui jaringan yang tidak aman. Algoritma ini menggunakan konsep matematika berupa perpangkatan modular, di mana kedua pihak menyepakati nilai publik berupa bilangan prima besar dan generator. Meskipun nilai-nilai tersebut diketahui publik, kunci rahasia tetap aman karena sulitnya menyelesaikan masalah logaritma diskrit.

Dalam prosesnya, masing-masing pihak memilih bilangan rahasia, lalu menghitung nilai publik yang dipertukarkan. Setelah pertukaran, kedua pihak dapat menghitung kunci rahasia yang sama tanpa pernah mengirimkan kunci tersebut secara langsung. Pihak luar yang menyadap komunikasi hanya dapat melihat nilai publik, namun tidak dapat menghitung kunci rahasia secara praktis.

Diffie-Hellman menjadi dasar bagi banyak protokol keamanan modern seperti TLS dan VPN. Meskipun aman, algoritma ini rentan terhadap serangan man-in-the-middle jika tidak disertai mekanisme autentikasi, sehingga biasanya dikombinasikan dengan sertifikat digital atau algoritma kriptografi lainnya.

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
1. Karena kunci dibentuk dari perhitungan matematika (perpangkatan modular) tanpa pernah dikirim langsung, sehingga aman meski lewat saluran publik.
2. Kelemahan utamanya adalah rentan terhadap serangan man-in-the-middle (MITM).
3. Serangan MITM dicegah dengan autentikasi, misalnya menggunakan sertifikat digital, tanda tangan digital, atau protokol TLS.

 
---

## 8. Kesimpulan
Berdasarkan percobaan, Diffie-Hellman terbukti efektif untuk melakukan pertukaran kunci secara aman melalui saluran publik tanpa mengirimkan kunci rahasia secara langsung. Namun, tanpa autentikasi tambahan, protokol ini rentan terhadap serangan man-in-the-middle. Oleh karena itu, Diffie-Hellman perlu dikombinasikan dengan mekanisme autentikasi agar keamanan komunikasi tetap terjamin.

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
