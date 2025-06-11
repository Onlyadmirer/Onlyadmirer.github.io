---
title: Rat in a Maze
date: 2025-06-11
categories: [Algoritma, Backtracking]
tags: [rat-in-maze, backtracking]
author: akmal
---

# Rat in a Maze

**Rat in a Maze** adalah masalah pencarian jalur bagi tikus dari sudut kiri atas (0,0) ke sudut kanan bawah (n-1,n-1) pada labirin n×n. Beberapa sel diblokir (0) dan lainnya terbuka (1), dengan tikus hanya bisa bergerak ke kanan atau ke bawah.

Pendekatan **backtracking** digunakan untuk menjelajahi semua jalur yang mungkin.

---

## Langkah Penyelesaian

1. Mulai dari (0,0) dengan matriks solusi kosong.
2. Jika sel saat ini valid, masukkan ke jalur.
3. Coba bergerak ke kanan atau ke bawah secara rekursif.
4. Jika mencapai tujuan, simpan jalur.
5. Jika langkah gagal, mundur dan coba opsi lain.

---

## Pseudocode untuk Rat in a Maze

```text
function solveMaze(labirin, x, y, solusi, n)
    if x == n-1 and y == n-1
        solusi[x][y] = 1
        simpanSolusi(solusi)
        return
    if aman(labirin, x, y, n)
        solusi[x][y] = 1
        solveMaze(labirin, x+1, y, solusi, n)    // Ke kanan
        solveMaze(labirin, x, y+1, solusi, n)    // Ke bawah
        solusi[x][y] = 0                         // Backtrack
```

---

## Penjelasan Pseudocode

- `labirin` adalah matriks n×n yang menunjukkan sel terbuka (1) dan diblokir (0).
- `(x, y)` adalah posisi saat ini tikus.
- `solusi` adalah matriks yang melacak jalur.
- `n` adalah ukuran labirin.
- `aman(labirin, x, y, n)` memeriksa apakah sel valid (dalam batas dan terbuka).

---

## Kesimpulan

Algoritma ini menemukan jalur dengan strategi:
- Menggunakan **backtracking** untuk mencoba semua kemungkinan jalur.
- Memeriksa **validitas** gerakan ke kanan atau ke bawah.
- Cocok untuk masalah pencarian jalur dalam grid.

---

## Referensi

- kel_06
- Cormen, T.H., Leiserson, C.E., Rivest, R.L., & Stein, C. *Introduction to Algorithms*.
- [GeeksforGeeks: Rat in a Maze](https://www.geeksforgeeks.org/rat-in-a-maze-backtracking-2/)