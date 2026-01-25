# Laporan Praktikum Kriptografi
Minggu ke-: 15 
Topik: tinycoin-erc2 
Nama: Siti Kharisah  
NIM: 230202787
Kelas: 5IKRA 

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Mengembangkan proyek sederhana berbasis algoritma kriptografi.  
2. Mendokumentasikan proses implementasi proyek ke dalam repository Git.  
3. Menyusun laporan teknis hasil proyek akhir.  


---

## 2. Dasar Teori
ERC-20 merupakan standar token pada blockchain Ethereum yang menetapkan aturan dan fungsi dasar agar token dapat digunakan secara seragam oleh dompet digital, bursa, serta smart contract lainnya. Standar ini mencakup fungsi utama seperti pengecekan total suplai, informasi saldo, serta mekanisme pengiriman dan pemberian izin penggunaan token. Dengan adanya standar ERC-20, token seperti TinyCoin dapat beroperasi dan terintegrasi dengan berbagai layanan di ekosistem Ethereum secara lebih mudah dan konsisten.

TinyCoin yang dibangun berdasarkan standar ERC-20 menggunakan smart contract sebagai pengatur utama dalam proses penerbitan, distribusi, dan transaksi token. Seluruh aktivitas tersebut berjalan secara otomatis dan terdesentralisasi sesuai kode yang telah dideploy ke blockchain. Karena smart contract bersifat tidak dapat diubah, aspek keamanan dan kualitas kode menjadi sangat penting agar token dapat digunakan dengan aman, termasuk saat dimanfaatkan dalam aplikasi terdesentralisasi seperti DeFi.

Penggunaan ERC-20 memberikan keuntungan berupa kompatibilitas yang luas, kemudahan integrasi, serta potensi likuiditas yang tinggi melalui platform pertukaran terdesentralisasi. Meski demikian, terdapat beberapa keterbatasan seperti biaya transaksi yang dipengaruhi gas fee serta risiko kesalahan implementasi kontrak. Oleh sebab itu, pengembangan TinyCoin–ERC-20 perlu memperhatikan standar keamanan dan praktik terbaik dalam pemrograman smart contract.

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
1. Fungsi utama ERC-20
Menjadi standar token di blockchain Ethereum agar token dapat digunakan secara seragam dan kompatibel dengan dompet, bursa, serta aplikasi terdesentralisasi (dApp).
2. Mekanisme transfer token ERC-20
Transfer dilakukan melalui fungsi transfer atau transferFrom, yang memindahkan saldo token dari satu alamat ke alamat lain sesuai jumlah yang ditentukan, dengan validasi saldo dan izin (approval).
3. Risiko dan mitigasi smart contract
Risiko utama meliputi bug kode dan celah keamanan. Mitigasinya dilakukan melalui audit kode, pengujian menyeluruh, serta penggunaan library standar yang telah teruji.
---

## 8. Kesimpulan
ERC-20 berperan penting sebagai standar token dalam ekosistem blockchain Ethereum karena memastikan interoperabilitas dan kemudahan integrasi dengan berbagai platform dan aplikasi terdesentralisasi. Melalui mekanisme smart contract, proses transfer dan pengelolaan token dapat dilakukan secara otomatis, transparan, dan terdesentralisasi. Namun, implementasi smart contract tetap memiliki risiko keamanan, sehingga diperlukan perancangan yang matang, pengujian menyeluruh, serta penerapan praktik terbaik agar token dapat digunakan secara aman dan andal.
Berdasarkan hasil implementasi program, standar ERC-20 berhasil diterapkan untuk mengelola token TinyCoin secara terstruktur dan konsisten. Program mampu menjalankan fungsi utama seperti pengecekan saldo, transfer token, serta mekanisme izin (approval) sesuai dengan ketentuan ERC-20. Hal ini menunjukkan bahwa logika smart contract telah berjalan dengan baik dan sesuai tujuan perancangan.

Selain itu, pengujian program membuktikan bahwa proses transfer token berlangsung secara otomatis dan transparan melalui smart contract tanpa campur tangan pihak ketiga. Meskipun demikian, aspek keamanan dan efisiensi kode tetap menjadi perhatian utama, sehingga diperlukan pengujian lanjutan dan audit smart contract agar program dapat digunakan secara aman dan andal dalam lingkungan blockchain.
---

## 9. Daftar Pustaka
Buterin, V. (2015). Ethereum: A Next-Generation Smart Contract and Decentralized Application Platform.
Ethereum Foundation. (2023). ERC-20 Token Standard.
Antonopoulos, A. M., & Wood, G. (2018). Mastering Ethereum: Building Smart Contracts and DApps. O’Reilly Media.

---

## 10. Commit Log
commit 5063698f832ed448509ec834fa6defb01da346ae
Author: sitikharisah18-bot <sitikharisah18@gmail.com>
Date:   Sun Jan 25 23:05:30 2026 +0700

    week15-rinycoin-erc20

```
