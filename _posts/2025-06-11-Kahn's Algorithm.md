---
title: Kahn's Algorithm
date: 2025-06-11
categories: [Algoritma, Pengurutan Topologi]
tags: [kahn-algorithm, topological-sort]
author: akmal
---

# Kahn's Algorithm

**Kahn's Algorithm** digunakan untuk pengurutan topologi pada Grafik Aciklik Terarah (DAG). Ini menghasilkan urutan linear simpul sehingga untuk setiap sisi terarah (u,v), simpul u muncul sebelum v dalam urutan.

Algoritma ini menggunakan pendekatan berbasis antrean untuk memproses simpul dengan derajat masuk nol.

---

## Langkah Penyelesaian

1. Hitung derajat masuk untuk setiap simpul.
2. Tambahkan semua simpul dengan derajat masuk 0 ke antrean.
3. Selama antrean tidak kosong:
   - Keluarkan simpul dan tambahkan ke hasil.
   - Kurangi derajat masuk tetangga simpul tersebut.
   - Jika derajat masuk tetangga menjadi 0, tambahkan ke antrean.
4. Jika hasil mengandung semua simpul, pengurutan valid; jika tidak, graf memiliki siklus.

---

## Pseudocode untuk Kahn's Algorithm

```text
function kahnsAlgorithm(graf, V)
    inDegree = hitungInDegree(graf, V)
    antrean = new Queue()
    for simpul = 0 to V-1
        if inDegree[simpul] == 0
            antrean.enqueue(simpul)
    hasil = []
    while antrean tidak kosong
        simpul = antrean.dequeue()
        hasil.add(simpul)
        for tetangga in graf[simpul]
            inDegree[tetangga] -= 1
            if inDegree[tetangga] == 0
                antrean.enqueue(tetangga)
    if hasil.size != V
        return "Graf memiliki siklus"
    return hasil
```

---

## Penjelasan Pseudocode

- `graf` adalah daftar ketetanggaan dari graf.
- `V` adalah jumlah simpul.
- `inDegree` adalah array yang menyimpan derajat masuk setiap simpul.
- `antrean` menyimpan simpul dengan derajat masuk 0.
- `hasil` menyimpan urutan topologi.

---

## Kesimpulan

Algoritma ini menghasilkan pengurutan topologi dengan strategi:
- Menggunakan **antrean** untuk memproses simpul tanpa dependensi.
- Memeriksa **siklus** dalam graf.
- Cocok untuk penjadwalan tugas atau analisis dependensi.

---

## Referensi

- kel_09
- Cormen, T.H., Leiserson, C.E., Rivest, R.L., & Stein, C. *Introduction to Algorithms*.
- [GeeksforGeeks: Kahn's Algorithm](https://www.geeksforgeeks.org/topological-sorting-indegree-based-solution/)