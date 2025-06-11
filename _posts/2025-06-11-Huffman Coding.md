---
title: Huffman Coding
date: 2025-06-11
categories: [Algoritma, Kompresi Data]
tags: [huffman-coding, greedy-algorithm]
author: akmal
---

# Huffman Coding

**Huffman Coding** adalah algoritma kompresi data tanpa kehilangan yang memberikan kode panjang variabel untuk karakter berdasarkan frekuensinya dalam data masukan. Karakter dengan frekuensi lebih tinggi mendapat kode lebih pendek, sehingga mengoptimalkan ukuran data terenkode.

Algoritma ini menggunakan pendekatan **greedy** dengan membangun pohon biner (Huffman Tree) untuk menentukan kode prefiks yang unik untuk setiap karakter.

---

## Langkah Penyelesaian

1. Hitung frekuensi setiap karakter dalam data masukan.
2. Buat min-heap dari simpul yang berisi karakter dan frekuensinya.
3. Ambil dua simpul dengan frekuensi terendah, gabungkan menjadi simpul baru dengan frekuensi total, dan masukkan kembali ke heap.
4. Ulangi hingga hanya satu simpul (pohon) tersisa.
5. Tetapkan kode biner (0 untuk kiri, 1 untuk kanan) berdasarkan jalur pohon untuk setiap karakter.

---

## Pseudocode untuk Huffman Coding

```text
Buat min-heap H dari karakter dan frekuensinya
while H.size > 1
    kiri = H.extractMin()        // Ambil simpul dengan frekuensi terendah
    kanan = H.extractMin()       // Ambil simpul dengan frekuensi terendah berikutnya
    simpulBaru = new Node(kiri.freq + kanan.freq, kiri, kanan)
    H.insert(simpulBaru)         // Masukkan simpul baru ke heap
pohon = H.extractMin()           // Pohon Huffman
for setiap daun in pohon
    buatKode(daun, kodeBiner)    // Tetapkan kode biner berdasarkan jalur
return kodeBiner
```

---

## Penjelasan Pseudocode

- `H` adalah min-heap yang menyimpan simpul dengan karakter dan frekuensinya.
- `kiri` dan `kanan` adalah simpul dengan frekuensi terendah yang digabungkan.
- `simpulBaru` adalah simpul baru dengan frekuensi total dari `kiri` dan `kanan`.
- `buatKode` secara rekursif menelusuri pohon untuk menghasilkan kode biner untuk setiap karakter.
- `kodeBiner` adalah himpunan kode untuk setiap karakter.

---

## Kesimpulan

Algoritma ini menghasilkan kode optimal dengan strategi:
- Menggunakan **min-heap** untuk menggabungkan karakter berdasarkan frekuensi.
- Menghasilkan **kode prefiks** yang memastikan dekode tanpa ambigu.
- Cocok untuk kompresi data seperti teks atau file multimedia.

---

## Referensi

- kel_03
- Cormen, T.H., Leiserson, C.E., Rivest, R.L., & Stein, C. *Introduction to Algorithms*.
- [GeeksforGeeks: Huffman Coding](https://www.geeksforgeeks.org/huffman-coding-greedy-algo-3/)