---
title: Dijkstra's Algorithm
date: 2025-06-11
categories: [Algoritma, Jalur Terpendek]
tags: [dijkstra, shortest-path]
author: akmal
---

# Dijkstra's Algorithm

**Dijkstra's Algorithm** menemukan jalur terpendek dari simpul sumber ke semua simpul lain dalam graf berbobot dengan bobot sisi tidak negatif. Algoritma ini menggunakan pendekatan **greedy** dengan antrean prioritas untuk memilih simpul dengan jarak terkecil.

Algoritma ini sering digunakan dalam navigasi dan perutean jaringan.

---

## Langkah Penyelesaian

1. Inisialisasi jarak: sumber = 0, lainnya = tak hingga.
2. Gunakan antrean prioritas untuk menyimpan simpul dan jarak sementara.
3. Selama antrean tidak kosong:
   - Ambil simpul dengan jarak minimal.
   - Perbarui jarak tetangga jika ditemukan jalur lebih pendek melalui simpul saat ini.
4. Tandai simpul yang diproses sebagai dikunjungi.

---

## Pseudocode untuk Dijkstra's Algorithm

```text
function dijkstra(graf, sumber, V)
    jarak = [∞, ..., ∞], jarak[sumber] = 0
    antreanPrioritas = new PriorityQueue()
    antreanPrioritas.insert(sumber, 0)
    dikunjungi = new Set()
    while antreanPrioritas tidak kosong
        simpul = antreanPrioritas.extractMin()
        if simpul in dikunjungi
            continue
        dikunjungi.add(simpul)
        for tetangga, bobot in graf[simpul]
            if jarak[simpul] + bobot < jarak[tetangga]
                jarak[tetangga] = jarak[simpul] + bobot
                antreanPrioritas.insert(tetangga, jarak[tetangga])
    return jarak
```

---

## Penjelasan Pseudocode

- `graf` adalah daftar ketetanggaan dengan bobot sisi.
- `sumber` adalah simpul awal.
- `V` adalah jumlah simpul.
- `jarak` menyimpan jarak terpendek ke setiap simpul.
- `antreanPrioritas` menyimpan simpul dan jarak sementara untuk diproses.

---

## Kesimpulan

Algoritma ini menemukan jalur terpendek dengan strategi:
- Menggunakan **antrean prioritas** untuk memilih simpul dengan jarak minimal.
- Memperbarui **jarak** secara serakah untuk memastikan jalur optimal.
- Cocok untuk aplikasi seperti navigasi GPS dan optimasi jaringan.

---

## Referensi

- kel_10
- Cormen, T.H., Leiserson, C.E., Rivest, R.L., & Stein, C. *Introduction to Algorithms*.
- [GeeksforGeeks: Dijkstra's Algorithm](https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-greedy-algo-7/)