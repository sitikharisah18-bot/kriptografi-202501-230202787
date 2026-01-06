# Laporan Praktikum Kriptografi
Minggu ke-: 10
Topik: [Public Key Infrastructure (PKI & Certificate Authority)]  
Nama: [Siti Kharisah]  
NIM: [230202787]  
Kelas: [5IKRA]  

---

## 1. Tujuan
1. Membuat sertifikat digital sederhana.  
2. Menjelaskan peran Certificate Authority (CA) dalam sistem PKI.  
3. Mengevaluasi fungsi PKI dalam komunikasi aman (contoh: HTTPS, TLS). 

---

## 2. Dasar Teori
 Public Key Infrastructure (PKI) adalah kerangka kerja keamanan yang digunakan untuk mengelola kunci publik dan privat dalam komunikasi digital. PKI memastikan tiga aspek utama keamanan, yaitu autentikasi, kerahasiaan, dan integritas data, dengan memanfaatkan kriptografi kunci publik. Dalam PKI, setiap entitas memiliki pasangan kunci (public key dan private key), di mana kunci publik dapat dibagikan secara terbuka sedangkan kunci privat dijaga kerahasiaannya.

Certificate Authority (CA) berperan sebagai pihak tepercaya yang menerbitkan dan memverifikasi sertifikat digital. Sertifikat digital berisi identitas pemilik, kunci publik, serta tanda tangan digital CA yang menjamin keaslian sertifikat tersebut. Dengan adanya CA, pengguna dapat mempercayai bahwa kunci publik benar-benar milik entitas yang sah, sehingga mencegah serangan seperti man-in-the-middle.

PKI juga mencakup mekanisme pengelolaan sertifikat seperti penerbitan, distribusi, pembaruan, dan pencabutan sertifikat (melalui CRL atau OCSP). Infrastruktur ini banyak digunakan dalam berbagai layanan keamanan, seperti HTTPS pada web, tanda tangan digital, email aman, dan sistem autentikasi jaringan, sehingga menjadi fondasi penting dalam keamanan informasi modern.


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

from cryptography import x509 # type: ignore
from cryptography.x509.oid import NameOID # type: ignore
from cryptography.hazmat.primitives import hashes, serialization # type: ignore
from cryptography.hazmat.primitives.asymmetric import rsa # type: ignore
from datetime import datetime, timedelta

# Generate key pair
key = rsa.generate_private_key(public_exponent=65537, key_size=2048)

# Buat subject & issuer (CA sederhana = self-signed)
subject = issuer = x509.Name([
    x509.NameAttribute(NameOID.COUNTRY_NAME, u"ID"),
    x509.NameAttribute(NameOID.ORGANIZATION_NAME, u"UPB Kriptografi"),
    x509.NameAttribute(NameOID.COMMON_NAME, u"example.com"),
])

# Buat sertifikat
cert = (
    x509.CertificateBuilder()
    .subject_name(subject)
    .issuer_name(issuer)
    .public_key(key.public_key())
    .serial_number(x509.random_serial_number())
    .not_valid_before(datetime.utcnow())
    .not_valid_after(datetime.utcnow() + timedelta(days=365))
    .sign(key, hashes.SHA256())
)

# Simpan sertifikat
with open("cert.pem", "wb") as f:
    f.write(cert.public_bytes(serialization.Encoding.PEM))

print("Sertifikat digital berhasil dibuat: cert.pem")

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
1. Fungsi utama CA adalah memverifikasi identitas entitas dan menerbitkan sertifikat digital yang menjamin keaslian kunci publik.
2. Self-signed certificate tidak tepercaya karena tidak diverifikasi pihak ketiga, sehingga mudah dipalsukan.
3. PKI mencegah MITM dengan validasi sertifikat server oleh CA tepercaya dan verifikasi tanda tangan digital saat TLS/HTTPS.
---

## 8. Kesimpulan
Berdasarkan percobaan, PKI terbukti efektif dalam menjamin autentikasi, kerahasiaan, dan integritas komunikasi melalui penggunaan sertifikat digital. Peran Certificate Authority sangat penting untuk membangun kepercayaan dan mencegah serangan man-in-the-middle. Tanpa validasi sertifikat yang benar, keamanan komunikasi TLS/HTTPS tidak dapat terjamin.

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log

```
commit f153e80e498ea8475abb53c5c052df1b6a07704c
Author: sitikharisah18-bot <sitikharisah18@gmail.com>
Date:   Thu Dec 18 09:56:51 2025 +0700

    week10-pki
```
