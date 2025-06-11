---
title: Breadth First Search
date: 2025-06-11
categories: [Algoritma, Penjelajahan Graf]
tags: [bfs, graph-traversal]
author: akmal
---

# Breadth First Search

**Breadth First Search (BFS)** adalah algoritma penjelajahan graf yang mengeksplorasi semua simpul pada kedalaman saat ini sebelum pindah ke kedalaman berikutnya. Algoritma ini menggunakan antrean untuk mengelola urutan eksplorasi.

BFS sering digunakan untuk menemukan jalur terpendek dalam graf tanpa bobot.

---

## Langkah Penyelesaian

1. Mulai dari simpul sumber dan tambahkan ke antrean.
2. Tandai simpul sumber sebagai dikunjungi.
3. Selama antrean tidak kosong:
   - Keluarkan simpul dari antrean.
   - Proses simpul tersebut.
   - Tambahkan semua tetangga yang belum dikunjungi ke antrean dan tandai sebagai dikunjungi.

---

## Pseudocode untuk Breadth First Search

```text
function BFS(graf, sumber)
    antrean = new Queue()
    dikunjungi = new Set()
    antrean.enqueue(sumber)
    dikunjungi.add(sumber)
    while antrean tidak kosong
        simpul = antrean.dequeue()
        proses(simpul)
        for tetangga in graf[simpul]
            if tetangga not in dikunjungi
                antrean.enqueue(tetangga)
                dikunjungi.add(tetangga)
```

---

## Penjelasan Pseudocode

- `graf` adalah struktur data yang menyimpan daftar ketetanggaan.
- `sumber` adalah simpul awal penjelajahan.
- `antrean` menyimpan simpul yang akan diproses.
- `dikunjungi` melacak simpul yang sudah dieksplorasi.
- `proses(simpul)` dapat berupa pencetakan atau penyimpanan simpul.

---

## Kesimpulan

Algoritma ini efektif dengan strategi:
- Menggunakan **antrean** untuk menjelajahi simpul level demi level.
- Menjamin **jalur terpendek** dalam graf tanpa bobot.
- Cocok untuk aplikasi seperti navigasi GPS dan analisis jaringan.

---

## Referensi

- kel_07
- Cormen, T.H., Leiserson, C.E., Rivest, R.L., & Stein, C. *Introduction to Algorithms*.
- [GeeksforGeeks: Breadth First Search](https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/)