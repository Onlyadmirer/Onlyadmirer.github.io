---
title: Activity Selection Problem
date: 2025-06-11 
categories: [Algoritma, Greedy]
tags: [activity-selection, greedy-algorithm]     
author: akmal 
---


# Activity Selection Problem

**Activity Selection Problem** adalah masalah optimasi yang bertujuan memilih aktivitas sebanyak mungkin tanpa tumpang tindih. Diberikan sejumlah aktivitas dengan waktu mulai (`s`) dan waktu selesai (`f`), tantangannya adalah memilih subset aktivitas terbesar yang tidak saling bertabrakan.  

Algoritma yang digunakan untuk menyelesaikan masalah ini adalah **Greedy Algorithm**, yang berfokus pada memilih aktivitas yang selesai paling awal.

---

## Langkah Penyelesaian

1. Urutkan aktivitas berdasarkan waktu selesai.
2. Pilih aktivitas pertama yang selesai paling awal.
3. Pilih aktivitas berikutnya jika waktu mulai lebih besar atau sama dengan waktu selesai aktivitas sebelumnya.

---

## Pseudocode untuk Activity Selection Problem

```text
for i = 2 to n
    if s[i] >= f[j]       // Jika waktu mulai aktivitas lebih besar atau sama dengan waktu selesai aktivitas terakhir
        A = A ∪ {ai}      // Pilih aktivitas ai
        j = i             // Update indeks aktivitas terakhir yang dipilih

return A                  // Kembalikan himpunan aktivitas yang terpilih
```

---

## Penjelasan Pseudocode

- `s[]` adalah array yang berisi waktu mulai dari setiap aktivitas.
- `f[]` adalah array yang berisi waktu selesai dari setiap aktivitas (sudah diurutkan).
- `n` adalah jumlah total aktivitas yang tersedia.
- `A` adalah himpunan aktivitas yang terpilih.
- `j` adalah indeks aktivitas terakhir yang dipilih.

---

## Kesimpulan

Algoritma ini memilih aktivitas sebanyak mungkin tanpa tumpang tindih dengan strategi:
- Memilih aktivitas yang **selesai paling awal**
- Melanjutkan ke aktivitas berikutnya yang **kompatibel** (tidak bentrok waktu) dengan aktivitas yang sudah dipilih.

---

## Referensi

- kel_01
- Cormen, T.H., Leiserson, C.E., Rivest, R.L., & Stein, C. *Introduction to Algorithms*.
- [GeeksforGeeks: Activity Selection Problem](https://www.geeksforgeeks.org/activity-selection-problem-greedy-algo-1/)
