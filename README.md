# Otomata-W11 -- CYK (Cocke–Younger–Kasami) Algorithm

## 🧠 Apa Itu CYK Algorithm?

CYK (Cocke–Younger–Kasami) adalah algoritma parsing yang digunakan untuk menentukan apakah sebuah string dapat dihasilkan oleh suatu grammar dalam **Chomsky Normal Form (CNF)**. CYK merupakan algoritma **bottom-up** yang berbasis pada **Dynamic Programming**.

Algoritma ini cocok untuk:
- Parsing bahasa formal
- Validasi struktur kalimat dalam Natural Language Processing (NLP)
- Implementasi parser dalam compiler

## ⚙️ Cara Kerja CYK Algorithm
1. **Input**: Grammar dalam CNF dan sebuah string.
2. **Buat tabel segitiga bawah** (`n x n`) untuk menyimpan himpunan variabel yang menghasilkan substring tertentu.
3. **Inisialisasi baris pertama** dari tabel dengan variabel-variabel yang menghasilkan setiap karakter tunggal.
4. **Isi tabel** dengan mengevaluasi kombinasi substring dari panjang 2 hingga n, menggunakan aturan produksi.
5. Jika simbol start (`S`) ada di posisi kiri atas tabel (`table[0][n-1]`), maka string dapat dihasilkan oleh grammar.

## 📥 Cara Menjalankan Program

  ```
  git clone https://github.com/username/cyk-algorithm.git
  cd cyk-algorithm
  python3 cyk.py
  ```

**Contoh Input**
```
5
S -> AB
A -> BB
A -> a
B -> AB
B -> b
aabbb
```
**Contoh Output**
```
YES
a : [A] , a : [A] , b : [B] , b : [B] , b : [B]
aa : [] , ab : [B,S] , bb : [A] , bb : [A]
aab : [B,S] , abb : [A] , bbb : [B,S]
aabb : [A] , abbb : [B,S]
aabbb : [B,S]
```
