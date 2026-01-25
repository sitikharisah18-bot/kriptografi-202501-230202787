# Laporan Praktikum Kriptografi
Minggu ke-: 13  
Topik: [TinyChain – Proof of Work (PoW)]  
Nama: [Siti Kharisah]  
NIM: [230202787]  
Kelas: [5IKRA]  

---

## 1. Tujuan
1. Menjelaskan peran **hash function** dalam blockchain.  
2. Melakukan simulasi sederhana **Proof of Work (PoW)**.  
3. Menganalisis keamanan cryptocurrency berbasis kriptografi.

---

## 2. Dasar Teori
TinyChain dengan mekanisme Proof of Work (PoW) merupakan simulasi sederhana dari teknologi blockchain yang digunakan untuk memahami proses penambangan dan keamanan data. Dalam PoW, sebuah blok baru hanya dapat ditambahkan ke rantai jika penambang berhasil menemukan nilai nonce yang menghasilkan hash sesuai tingkat kesulitan tertentu. Proses ini membutuhkan komputasi yang tinggi sehingga mencegah manipulasi data secara mudah.
PoW berfungsi sebagai mekanisme konsensus, yaitu cara jaringan menyepakati blok mana yang valid. Karena setiap perubahan data akan mengubah hash blok dan seluruh blok setelahnya, maka blockchain menjadi immutabel. Hal ini membuat penyerang harus mengulang proses PoW untuk seluruh blok, yang secara praktis sangat sulit dilakukan.
Dalam TinyChain, PoW membantu menunjukkan bagaimana keamanan dan kepercayaan dapat dibangun tanpa pihak pusat. Meskipun sederhana dan kurang efisien dibanding sistem modern, TinyChain efektif sebagai media pembelajaran untuk memahami konsep dasar blockchain dan Proof of Work.

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

### Langkah 1 — Membuat Struktur Blok
```python
import hashlib
import time

class Block:
    def __init__(self, index, previous_hash, data, timestamp=None):
        self.index = index
        self.timestamp = timestamp or time.time()
        self.data = data
        self.previous_hash = previous_hash
        self.nonce = 0
        self.hash = self.calculate_hash()

    def calculate_hash(self):
        value = str(self.index) + str(self.timestamp) + str(self.data) + str(self.previous_hash) + str(self.nonce)
        return hashlib.sha256(value.encode()).hexdigest()

    def mine_block(self, difficulty):
        while self.hash[:difficulty] != "0" * difficulty:
            self.nonce += 1
            self.hash = self.calculate_hash()
        print(f"Block mined: {self.hash}")
```

---

### Langkah 2 — Membuat Blockchain
```python
class Blockchain:
    def __init__(self):
        self.chain = [self.create_genesis_block()]
        self.difficulty = 4

    def create_genesis_block(self):
        return Block(0, "0", "Genesis Block")

    def get_latest_block(self):
        return self.chain[-1]

    def add_block(self, new_block):
        new_block.previous_hash = self.get_latest_block().hash
        new_block.mine_block(self.difficulty)
        self.chain.append(new_block)

# Uji coba blockchain
my_chain = Blockchain()
print("Mining block 1...")
my_chain.add_block(Block(1, "", "Transaksi A → B: 10 Coin"))

print("Mining block 2...")
my_chain.add_block(Block(2, "", "Transaksi B → C: 5 Coin"))
```

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
1. Fungsi hash penting karena menjaga integritas dan keutuhan data, serta menghubungkan blok agar sulit dimanipulasi.
2. Proof of Work mencegah double spending dengan memastikan hanya satu blok valid yang disepakati jaringan melalui proses komputasi yang sulit.
3. Kelemahan PoW adalah membutuhkan energi dan daya komputasi besar, sehingga kurang efisien dan berdampak pada konsumsi listrik.
---

## 8. Kesimpulan
Kesimpulan dari percobaan TinyChain – Proof of Work (PoW) menunjukkan bahwa mekanisme PoW mampu menjaga integritas dan keamanan blockchain dengan mempersulit perubahan data pada blok. Proses pencarian nonce membuktikan bagaimana konsensus dicapai secara terdesentralisasi. Namun, percobaan ini juga memperlihatkan bahwa PoW membutuhkan komputasi dan energi yang cukup besar.

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
commit 539fcb03746e5308b6d7c30f74d5587dc898f42f
Author: sitikharisah18-bot <sitikharisah18@gmail.com>
Date:   Sun Jan 25 22:41:48 2026 +0700

    week13-tinychain

```
