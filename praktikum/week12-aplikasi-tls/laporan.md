# Laporan Praktikum Kriptografi
Minggu ke-:12  
Topik: [Aplikasi TLS & E-commerce]  
Nama: [Siti Kharisah]  
NIM: [230202787]  
Kelas: [5IKRA]  

---

## 1. Tujuan
1. Menganalisis penggunaan kriptografi pada **email** dan **SSL/TLS**.  
2. Menjelaskan enkripsi dalam transaksi **e-commerce**.  
3. Mengevaluasi isu **etika & privasi** dalam penggunaan kriptografi di kehidupan sehari-hari.  
---

## 2. Dasar Teori
TLS (Transport Layer Security) adalah protokol keamanan yang digunakan untuk melindungi komunikasi data di jaringan, khususnya internet. TLS menyediakan kerahasiaan, integritas, dan otentikasi dengan menggunakan kombinasi kriptografi kunci publik dan kunci simetris. Dalam proses handshake, TLS memverifikasi identitas server menggunakan sertifikat digital dan membentuk kunci sesi yang aman untuk komunikasi selanjutnya.
Dalam konteks e-commerce, TLS sangat penting untuk melindungi data sensitif seperti informasi login, nomor kartu kredit, dan data transaksi. Dengan TLS (ditandai HTTPS), pengguna dapat yakin bahwa data yang dikirim tidak disadap atau dimodifikasi oleh pihak tidak berwenang. Selain itu, TLS membantu membangun kepercayaan pelanggan terhadap keamanan platform e-commerce.
Penerapan TLS didukung oleh Certificate Authority (CA) yang menjamin keaslian identitas server e-commerce. Tanpa TLS, transaksi online rentan terhadap serangan seperti man-in-the-middle. Oleh karena itu, TLS menjadi fondasi utama keamanan dan keandalan sistem e-commerce modern.

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
1. HTTP tidak terenkripsi sehingga data mudah disadap, sedangkan HTTPS menggunakan TLS untuk mengenkripsi dan mengamankan komunikasi.
2. Sertifikat digital penting untuk memverifikasi identitas server dan mencegah serangan man-in-the-middle dalam komunikasi TLS.
3. Kriptografi melindungi privasi data dari akses tidak sah, tetapi dapat menyulitkan penegakan hukum dan menimbulkan dilema etika terkait akses terhadap data terenkripsi.
---

## 8. Kesimpulan
Kesimpulan dari percobaan Aplikasi TLS & E-commerce menunjukkan bahwa penggunaan TLS mampu mengamankan komunikasi dengan menyediakan kerahasiaan, integritas, dan otentikasi data. TLS melindungi informasi sensitif transaksi e-commerce dari penyadapan dan manipulasi. Dengan demikian, TLS meningkatkan kepercayaan dan keamanan dalam transaksi online.

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
