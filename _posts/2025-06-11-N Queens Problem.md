---
title: N-Queens Problem
date: 2025-06-11
categories: [Algoritma, Backtracking]
tags: [n-queens, backtracking]
author: akmal
---

# N-Queens Problem

**N-Queens Problem** adalah masalah penempatan N ratu catur pada papan N×N sehingga tidak ada dua ratu yang saling mengancam, yaitu tidak berada di baris, kolom, atau diagonal yang sama.

Algoritma ini diselesaikan dengan pendekatan **backtracking**, yang mencoba semua kemungkinan penempatan ratu dan mundur jika terjadi konflik.

---

## Langkah Penyelesaian

1. Mulai dengan papan N×N kosong.
2. Tempatkan ratu di baris pertama pada kolom yang mungkin.
3. Pindah ke baris berikutnya dan cari kolom yang aman.
4. Jika tidak ada kolom aman, mundur ke baris sebelumnya dan coba kolom lain.
5. Ulangi hingga N ratu ditempatkan atau semua kemungkinan habis.

---

## Pseudocode untuk N-Queens Problem

```text
function solveNQueens(papan, baris, N)
    if baris == N
        simpanSolusi(papan)
        return
    for kolom = 0 to N-1
        if aman(papan, baris, kolom)
            papan[baris][kolom] = 1
            solveNQueens(papan, baris+1, N)
            papan[baris][kolom] = 0    // Backtrack
```

---

## Penjelasan Pseudocode

- `papan` adalah matriks N×N yang melacak posisi ratu.
- `baris` adalah baris saat ini yang sedang diproses.
- `N` adalah ukuran papan dan jumlah ratu.
- `aman(papan, baris, kolom)` memeriksa apakah ratu dapat ditempatkan di `(baris, kolom)` tanpa konflik.
- `simpanSolusi` mencatat solusi valid.

---

## Kesimpulan

Algoritma ini menemukan solusi dengan strategi:
- Menggunakan **backtracking** untuk mencoba semua penempatan.
- Memeriksa **konflik** di baris, kolom, dan diagonal.
- Cocok untuk masalah kombinatorial seperti penempatan objek.

---

## Referensi

- kel_04
- Cormen, T.H perkembangan teknologi saat ini., Leiserson, C.E., Rivest, R.L., & Stein, C. *Introduction to Algorithms*.
- [GeeksforGeeks: N-Queens Problem](https://www.geeksforgeeks.org/n-queen-problem-backtracking-3/)