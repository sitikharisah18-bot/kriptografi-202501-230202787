# Laporan Praktikum Kriptografi
Minggu ke-: 11  
Topik: [Secret Sharing (Shamir’s Secret Sharing)]  
Nama: [Siti Kharisah]  
NIM: [230202787]  
Kelas: [5IKRA]  

---

## 1. Tujuan
1. Menjelaskan konsep **Shamir Secret Sharing** (SSS).  
2. Melakukan simulasi pembagian rahasia ke beberapa pihak menggunakan skema SSS.  
3. Menganalisis keamanan skema distribusi rahasia. 
---

## 2. Dasar Teori
Shamir’s Secret Sharing adalah skema kriptografi yang digunakan untuk membagi sebuah rahasia menjadi beberapa bagian (share) dan mendistribusikannya ke beberapa pihak. Rahasia tersebut hanya dapat direkonstruksi jika sejumlah minimal bagian tertentu (threshold) digabungkan, sedangkan sebagian kecil bagian tidak akan memberikan informasi apa pun tentang rahasia. Metode ini didasarkan pada konsep polinomial dalam matematika.

Dalam skema ini, rahasia disimpan sebagai konstanta dalam sebuah polinomial berderajat 
𝑘
−
1
k−1. Setiap peserta menerima satu titik pada polinomial tersebut sebagai share. Untuk mendapatkan kembali rahasia, diperlukan minimal 
𝑘
k share agar polinomial dapat direkonstruksi menggunakan interpolasi Lagrange. Jika jumlah share kurang dari threshold, rahasia tetap aman.

Shamir’s Secret Sharing banyak digunakan untuk pengamanan kunci kriptografi, sistem backup, dan manajemen akses bersama, karena meningkatkan keamanan dengan menghindari penyimpanan rahasia pada satu pihak saja. Skema ini sangat efektif dalam mencegah kehilangan atau penyalahgunaan rahasia secara tunggal.

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

from secretsharing import SecretSharer

# Rahasia yang ingin dibagi
secret = "KriptografiUPB2025"

# Bagi menjadi 5 shares, ambang batas 3 (minimal 3 shares untuk rekonstruksi)
shares = SecretSharer.split_secret(secret, 3, 5)
print("Shares:", shares)

# Rekonstruksi rahasia dari 3 shares
recovered = SecretSharer.recover_secret(shares[:3])
print("Recovered secret:", recovered)
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
1. Keuntungan utama Shamir Secret Sharing adalah rahasia tidak tersimpan utuh pada satu pihak; sebagian share saja tidak dapat mengungkap kunci, sehingga lebih aman dibanding membagikan salinan kunci langsung.
2. Threshold (k) menentukan jumlah minimum share yang harus digabungkan untuk merekonstruksi rahasia; jika kurang dari 
𝑘
k, rahasia tetap aman.
3. Contoh skenario nyata: pengamanan kunci master perusahaan, di mana kunci hanya bisa diakses jika minimal beberapa manajer menyetujui bersama.  

---

## 8. Kesimpulan
Kesimpulan dari percobaan Shamir’s Secret Sharing menunjukkan bahwa sebuah rahasia dapat dibagi menjadi beberapa bagian dan hanya dapat direkonstruksi jika jumlah share memenuhi nilai threshold yang ditentukan. Percobaan ini membuktikan bahwa share individu tidak mengungkap informasi rahasia apa pun. Dengan demikian, Shamir’s Secret Sharing meningkatkan keamanan dan keandalan pengelolaan kunci kriptografi.

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
commit d69192ab254eb8342edfe977cf21506b53f2f914
Author: sitikharisah18-bot <sitikharisah18@gmail.com>
Date:   Tue Jan 6 13:33:52 2026 +0700

    week11-secret-sharing

```
