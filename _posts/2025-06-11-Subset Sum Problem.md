---
title: Subset Sum Problem
date: 2025-06-11
categories: [Algoritma, Pemrograman Dinamis]
tags: [subset-sum, dynamic-programming]
author: akmal
---

# Subset Sum Problem

**Subset Sum Problem** bertujuan menemukan apakah ada subset dari sekumpulan bilangan bulat positif yang jumlahnya sama dengan nilai target.

Masalah ini diselesaikan dengan **pemrograman dinamis** untuk efisiensi pada masukan sedang, meskipun secara teoretis merupakan masalah NP-Complete.

---

## Langkah Penyelesaian

1. Buat tabel DP berukuran (n+1)×(target+1), di mana `dp[i][j]` menunjukkan apakah subset dari i elemen pertama dapat menghasilkan jumlah j.
2. Inisialisasi `dp[0][0] = true` (subset kosong menghasilkan jumlah 0).
3. Untuk setiap elemen dan jumlah, perbarui tabel berdasarkan apakah elemen saat ini dimasukkan atau diabaikan.
4. Jawabannya adalah `dp[n][target]`.

---

## Pseudocode untuk Subset Sum Problem

```text
function subsetSum(himpunan, n, target)
    dp[0][0] = true
    for i = 1 to n
        for j = 0 to target
            if himpunan[i-1] <= j
                dp[i][j] = dp[i-1][j-himpunan[i-1]] or dp[i-1][j]
            else
                dp[i][j] = dp[i-1][j]
    return dp[n][target]
```

---

## Penjelasan Pseudocode

- `himpunan` adalah array bilangan bulat positif.
- `n` adalah jumlah elemen dalam himpunan.
- `target` adalah jumlah yang diinginkan.
- `dp[i][j]` menyimpan nilai boolean yang menunjukkan apakah jumlah j dapat dicapai dengan i элементов pertama.
- Pilihan untuk memasukkan atau mengabaikan `himpunan[i-1]` diperiksa jika elemen tersebut tidak melebihi j.

---

## Kesimpulan

Algoritma ini menyelesaikan masalah dengan strategi:
- Menggunakan **pemrograman dinamis** untuk menghindari perhitungan berulang.
- Membuat **tabel DP** untuk melacak kemungkinan jumlah.
- Cocok untuk masalah optimasi kombinatorial.

---

## Referensi

- kel_05
- Cormen, T.H., Leiserson, C.E., Rivest, R.L., & Stein, C. *Introduction to Algorithms*.
- [GeeksforGeeks: Subset Sum Problem](https://www.geeksforgeeks.org/subset-sum-problem-dp-25/)