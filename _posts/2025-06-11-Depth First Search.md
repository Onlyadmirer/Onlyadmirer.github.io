---
title: Depth First Search
date: 2025-06-11
categories: [Algoritma, Penjelajahan Graf]
tags: [dfs, graph-traversal]
author: akmal
---

# Depth First Search

**Depth First Search (DFS)** adalah algoritma penjelajahan graf yang mengeksplorasi sejauh mungkin di setiap cabang sebelum mundur. Algoritma ini dapat diimplementasikan secara rekursif atau menggunakan tumpukan.

DFS sering digunakan untuk deteksi siklus atau pengurutan topologi.

---

## Langkah Penyelesaian

1. Mulai dari simpul sumber dan tandai sebagai dikunjungi.
2. Proses simpul tersebut.
3. Secara rekursif jelajahi setiap tetangga yang belum dikunjungi.
4. Mundur ketika tidak ada tetangga yang belum dikunjungi.

---

## Pseudocode untuk Depth First Search

```text
function DFS(graf, simpul, dikunjungi)
    dikunjungi.add(simpul)
    proses(simpul)
    for tetangga in graf[simpul]
        if tetangga not in dikunjungi
            DFS(graf, tetangga, dikunjungi)
```

---

## Penjelasan Pseudocode

- `graf` adalah struktur data yang menyimpan daftar ketetanggaan.
- `simpul` adalah simpul saat ini yang sedang diproses.
- `dikunjungi` adalah himpunan yang melacak simpul yang sudah dieksplorasi.
- `proses(simpul)` dapat berupa pencetakan atau penyimpanan simpul.

---

## Kesimpulan

Algoritma ini efisien dengan strategi:
- Menggunakan **rekursi** atau tumpukan untuk menjelajahi cabang secara mendalam.
- Cocok untuk **deteksi siklus** atau masalah seperti penyelesaian labirin.
- Tidak selalu menemukan jalur terpendek.

---

## Referensi

- kel_08
- Cormen, T.H., Leiserson, C.E., Rivest, R.L., & Stein, C. *Introduction to Algorithms*.
- [GeeksforGeeks: Depth First Search](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/)