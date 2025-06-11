---
title: Fractional Knapsack Problem
date: 2025-06-11 
categories: [Algoritma, Greedy]
tags: [knapsack, fractional-knapsack, greedy-algorithm] 
author: akmal    
---

**Fractional Knapsack Problem** adalah versi dari masalah Knapsack di mana kita dapat membagi item menjadi bagian-bagian fraksional. Tujuan utama dari masalah ini adalah untuk memaksimalkan total nilai dari item yang dimasukkan ke dalam knapsack dengan kapasitas terbatas.

Masalah ini dapat diselesaikan secara efisien menggunakan **Greedy Algorithm**, dengan memilih item berdasarkan rasio nilai per unit berat tertinggi terlebih dahulu.

---

## Langkah Penyelesaian

1. Hitung rasio `value/weight` untuk setiap item.
2. Urutkan item berdasarkan rasio tersebut secara menurun.
3. Ambil item sepenuhnya jika masih muat di knapsack.
4. Jika item tidak bisa diambil sepenuhnya, ambil sebagian yang masih muat.

---

## Pseudocode untuk Fractional Knapsack

```text
sort items by value/weight in descending order
for i = 1 to n
    if weight[i] <= remaining_capacity
        take all of item i
        remaining_capacity -= weight[i]
    else
        take (remaining_capacity / weight[i]) fraction of item i
        break
```

---

## Penjelasan Pseudocode

- `n` adalah jumlah item.
- `weight[i]` dan `value[i]` masing-masing menunjukkan berat dan nilai dari item ke-i.
- `remaining_capacity` adalah kapasitas sisa knapsack.
- Kita memilih item berdasarkan rasio nilai terhadap berat (`value/weight`) secara menurun untuk memaksimalkan nilai.

---

## Contoh

Misalkan ada 3 item:
- Item A: berat = 10, nilai = 60 → rasio = 6
- Item B: berat = 20, nilai = 100 → rasio = 5
- Item C: berat = 30, nilai = 120 → rasio = 4

Jika kapasitas knapsack adalah 50:
- Ambil seluruh Item A dan B → total berat = 30
- Ambil 2/3 dari Item C (karena sisa kapasitas = 20)
- Total nilai = 60 + 100 + (2/3 * 120) = 240

---

## Kesimpulan

Fractional Knapsack merupakan variasi dari Knapsack Problem yang dapat diselesaikan secara efisien dengan algoritma greedy. Dengan mengambil barang berdasarkan rasio `value/weight` tertinggi dan diperbolehkannya pengambilan sebagian barang, kita bisa memperoleh solusi optimal secara cepat dan sederhana. Pendekatan greedy cocok untuk masalah ini karena pilihan optimal lokal mengarah ke solusi optimal global.

---

## Referensi

- kel_2
- Cormen, T.H., Leiserson, C.E., Rivest, R.L., & Stein, C. *Introduction to Algorithms*.
- [GeeksforGeeks: Fractional Knapsack Problem](https://www.geeksforgeeks.org/fractional-knapsack-problem/)
