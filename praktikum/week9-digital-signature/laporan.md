# Laporan Praktikum Kriptografi
Minggu ke-: 9 
Topik: [Digital Signature (RSA/DSA)]  
Nama: [Siti Kharisah]  
NIM: [230202787]  
Kelas: [5IKRA]  

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Mengimplementasikan tanda tangan digital menggunakan algoritma RSA/DSA.  
2. Memverifikasi keaslian tanda tangan digital.  
3. Menjelaskan manfaat tanda tangan digital dalam otentikasi pesan dan integritas data.  

---

## 2. Dasar Teori
Digital Signature adalah mekanisme kriptografi yang digunakan untuk menjamin keaslian, integritas, dan non-repudiation suatu pesan atau dokumen digital. Prosesnya melibatkan pembuatan nilai hash dari pesan, kemudian hash tersebut dienkripsi menggunakan kunci privat pengirim. Penerima memverifikasi tanda tangan dengan kunci publik untuk memastikan pesan tidak berubah dan benar berasal dari pengirim yang sah.
Pada RSA, algoritma yang sama dapat digunakan baik untuk enkripsi maupun tanda tangan digital, sedangkan pada DSA (Digital Signature Algorithm) algoritma dirancang khusus hanya untuk proses tanda tangan. DSA lebih fokus pada efisiensi penandatanganan, sementara RSA lebih fleksibel dan banyak digunakan dalam sistem keamanan modern.
Digital Signature banyak diterapkan pada sistem keamanan seperti HTTPS, e-mail, dan dokumen elektronik, serta didukung oleh Certificate Authority (CA) yang menjamin keterkaitan antara identitas pengguna dan kunci publiknya. Dengan demikian, Digital Signature menjadi komponen penting dalam menjaga keamanan komunikasi digital.

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
from Crypto.PublicKey import RSA
from Crypto.Signature import pkcs1_15
from Crypto.Hash import SHA256

# Generate pasangan kunci RSA
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Pesan yang akan ditandatangani
message = b"Hello, ini pesan penting."
h = SHA256.new(message)

# Buat tanda tangan dengan private key
signature = pkcs1_15.new(private_key).sign(h)
print("Signature:", signature.hex())
try:
    pkcs1_15.new(public_key).verify(h, signature)
    print("Verifikasi berhasil: tanda tangan valid.")
except (ValueError, TypeError):
    print("Verifikasi gagal: tanda tangan tidak valid.")
    
# Modifikasi pesan
fake_message = b"Hello, ini pesan palsu."
h_fake = SHA256.new(fake_message)

try:
    pkcs1_15.new(public_key).verify(h_fake, signature)
    print("Verifikasi berhasil (seharusnya gagal).")
except (ValueError, TypeError):
    print("Verifikasi gagal: tanda tangan tidak cocok dengan pesan.")
```
)

---

## 6. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](Screenshots/Eksekusi.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 7. Jawaban Pertanyaan
1. Enkripsi RSA digunakan untuk menjaga kerahasiaan pesan, sedangkan tanda tangan digital RSA digunakan untuk menjamin keaslian dan keutuhan pesan.
2. Tanda tangan digital menjamin integritas karena perubahan pesan akan mengubah hash, dan menjamin otentikasi karena tanda tangan dibuat menggunakan kunci privat pengirim.
3. Certificate Authority (CA) berperan sebagai pihak tepercaya yang memverifikasi identitas dan menerbitkan sertifikat digital agar kunci publik dapat dipercaya.
---

## 8. Kesimpulan
Digital Signature menggunakan algoritma RSA atau DSA untuk menjamin keaslian (authentication), keutuhan data (integrity), dan non-repudiation. Tanda tangan dibuat dengan kunci privat pengirim dan diverifikasi menggunakan kunci publik, sehingga penerima dapat memastikan bahwa pesan tidak diubah dan benar berasal dari pengirim yang sah. Sistem ini menjadi dasar keamanan pada berbagai aplikasi modern seperti HTTPS, e-mail, dan dokumen digital.

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log

```
commit 49be3a18b342268c730d4bbc1fc413c1ab9023dc (HEAD -> main, origin/main, origin/HEAD)
Author: sitikharisah18-bot <sitikharisah18@gmail.com>
Date:   Thu Dec 11 12:46:45 2025 +0700

    week9-digital-signature

```
