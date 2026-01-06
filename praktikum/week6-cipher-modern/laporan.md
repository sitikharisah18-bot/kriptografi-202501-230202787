# Laporan Praktikum Kriptografi
Minggu ke-: 6  
Topik: Cipher Modern (DES, AES, RSA)
Nama:  Siti Kharisah
NIM: 230202787 
Kelas: 5IKRA  

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Mengimplementasikan algoritma **DES** untuk blok data sederhana.  
2. Menerapkan algoritma **AES** dengan panjang kunci 128 bit.  
3. Menjelaskan proses pembangkitan kunci publik dan privat pada algoritma **RSA**.  


---

## 2. Dasar Teori
Cipher modern adalah algoritma kriptografi yang dirancang dengan dasar matematika dan komputasi yang kuat untuk mengamankan data digital. DES (Data Encryption Standard) dan AES (Advanced Encryption Standard) termasuk ke dalam cipher simetris, yaitu menggunakan satu kunci yang sama untuk proses enkripsi dan dekripsi. DES bekerja pada blok 64-bit dengan panjang kunci efektif 56-bit, namun kini dianggap tidak aman karena ukuran kuncinya terlalu kecil. Sebagai penggantinya, AES dikembangkan dengan tingkat keamanan lebih tinggi, mendukung panjang kunci 128, 192, dan 256-bit, serta efisien untuk implementasi perangkat lunak maupun perangkat keras.

Sementara itu, RSA merupakan cipher asimetris yang menggunakan sepasang kunci, yaitu kunci publik dan kunci privat. Keamanan RSA bergantung pada kesulitan faktorisasi bilangan prima besar, sehingga sangat cocok digunakan untuk pertukaran kunci dan tanda tangan digital. Berbeda dengan AES yang cepat untuk enkripsi data dalam jumlah besar, RSA relatif lebih lambat dan biasanya digunakan bersama algoritma simetris dalam sistem keamanan modern.

Secara umum, cipher modern dirancang untuk mengatasi kelemahan cipher klasik dengan menyediakan tingkat keamanan yang lebih tinggi terhadap serangan kriptanalisis. Kombinasi penggunaan algoritma simetris seperti AES dan algoritma asimetris seperti RSA menjadi standar dalam berbagai aplikasi keamanan, seperti SSL/TLS, perbankan digital, dan sistem komunikasi aman.

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
Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:

### Langkah 1 — Implementasi DES (Opsional, Simulasi)
```python
from Crypto.Cipher import DES
from Crypto.Random import get_random_bytes

key = get_random_bytes(8)  # kunci 64 bit (8 byte)
cipher = DES.new(key, DES.MODE_ECB)

plaintext = b"ABCDEFGH"
ciphertext = cipher.encrypt(plaintext)
print("Ciphertext:", ciphertext)

decipher = DES.new(key, DES.MODE_ECB)
decrypted = decipher.decrypt(ciphertext)
print("Decrypted:", decrypted)
```
---

### Langkah 2 — Implementasi AES-128
```python
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes

key = get_random_bytes(16)  # 128 bit key
cipher = AES.new(key, AES.MODE_EAX)

plaintext = b"Modern Cipher AES Example"
ciphertext, tag = cipher.encrypt_and_digest(plaintext)

print("Ciphertext:", ciphertext)

# Dekripsi
cipher_dec = AES.new(key, AES.MODE_EAX, nonce=cipher.nonce)
decrypted = cipher_dec.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())
```
---

### Langkah 3 — Implementasi RSA
```python
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP

# Generate key pair
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Enkripsi dengan public key
cipher_rsa = PKCS1_OAEP.new(public_key)
plaintext = b"RSA Example"
ciphertext = cipher_rsa.encrypt(plaintext)
print("Ciphertext:", ciphertext)

# Dekripsi dengan private key
decipher_rsa = PKCS1_OAEP.new(private_key)
decrypted = decipher_rsa.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())
```
---

## 6. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/Eksekusi.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 7. Jawaban Pertanyaan
1. DES dan AES menggunakan kunci simetris (satu kunci yang sama), sedangkan RSA menggunakan kunci asimetris (kunci publik dan privat); dari sisi keamanan, DES lemah karena kuncinya pendek, AES sangat kuat, dan RSA aman bergantung pada kesulitan faktorisasi bilangan besar.
2. AES lebih banyak digunakan karena memiliki keamanan lebih tinggi, ukuran kunci lebih panjang, dan lebih efisien dibanding DES.
3. RSA bersifat asimetris karena menggunakan dua kunci berbeda; kunci dibangkitkan dari dua bilangan prima besar yang menghasilkan kunci publik dan kunci privat yang saling terkait secara matematis.
---

## 8. Kesimpulan
Berdasarkan percobaan, cipher modern terbukti memiliki tingkat keamanan yang jauh lebih tinggi dibandingkan cipher klasik karena didukung oleh kunci yang lebih kuat dan struktur algoritma yang kompleks. AES menunjukkan efisiensi dan keamanan terbaik untuk enkripsi data, sementara RSA efektif digunakan untuk pertukaran kunci secara aman. Kombinasi keduanya sangat penting dalam sistem keamanan modern.
---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log

```
commit d0dfc226c74de05c90c946fd8392fbc16690580d 
Author: sitikharisah18-bot <sitikharisah18@gmail.com>
Date:   Tue Jan 6 12:02:39 2026 +0700

    week6-chiper-modern

```
