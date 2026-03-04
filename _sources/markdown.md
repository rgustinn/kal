# Eliminasi Gaussian

**Eliminasi Gaussian** adalah algoritma untuk menyelesaikan sistem persamaan linier dengan melakukan transformasi pada sistem agar lebih mudah dipecahkan. Dalam praktiknya, kita bekerja dengan matriks augmented yang berisi koefisien dan konstanta dari sistem persamaan.

Tujuan eliminasi adalah mengubah sistem linier yang kompleks menjadi sistem yang berbentuk lebih sederhana (seperti segitiga atas), sehingga solusi variabel-variabelnya dapat ditemukan dengan mudah melalui substitusi balik.

Ada tiga operasi baris yang digunakan dalam eliminasi, yang tidak mengubah solusi sistem:
- Tukarkan posisi ke dua persamaan.
- Kalikan persamaan dengan bilangan apa pun yang bukan nol.
- Gantikan suatu persamaan dengan jumlah persamaan itu sendiri dan kelipatan peserta lainnya.

## Contoh 1: Operasi baris dan eliminasi

$$\begin{split}
\begin{eqnarray*}
x_1 - x_2 + x_3 & = & 3\\
2x_1 + x_2 + 8x_3 & = & 18\\
4x_1 + 2x_2 -3x_3 & = & -2
\end{eqnarray*}
\end{split}$$

kita dapat menukar persamaan pertama dengan yang persamaan terakhir

$$\begin{split}
\begin{eqnarray*}
4x_1 + 2x_2 -3x_3 & = & -2 \\
2x_1 + x_2 + 8x_3 & = & 18\\
x_1 - x_2 + x_3 & = & 3
\end{eqnarray*}
\end{split}$$

atau kita dapat mengalikan persamaan pertama dengan 5

$$\begin{split}
\begin{eqnarray*}
5x_1 - 5x_2 + 5x_3 & = & 15\\
2x_1 + x_2 + 8x_3 & = & 18\\
4x_1 + 2x_2 -3x_3 & = & -2
\end{eqnarray*}
\end{split}$$

atau kita dapat menambahkan 2 kali persamaan pertama dengan persamaan terakhir

$$\begin{split}
\begin{eqnarray*}
x_1 - x_2 + x_3 & = & 3\\
2x_1 + x_2 + 3x_3 & = & 8\\
6x_1 \quad\quad -x_3 & = & 4
\end{eqnarray*}
\end{split}$$

Operasi terakhir adalah yang paling penting karena memungkinkan kita mengeliminasi variabel dari salah satu persamaan. Perhatikan bahwa persamaan ketiga tidak lagi mengandung suku $$x2$$ Ini adalah kunci dari algoritma eliminasi.

## Tiga Operasi Dasar Baris

1. A.rescale_row(i, a) Fungsi: Mengalikan baris ke i dengan skala a.
2. A.add_multiple_of_row(i, j, a) Fungsi: Menambahkan a x (baris ke-j) ke baris ke-i
3. A.swap_rows(i, j) Fungsi: Menukar baris ke-i dengan baris ke-j
 
```python
A= matrix([[1, -1, 1, 3], [2, 1, 8, 18], [4, 2, -3, -2]])
#tambahkan -2 kali baris 0 ke baris 1
A.add_multiple_of_row(0,1,-2)
A.add_multiple_of_row(0, 2, -4)
A.add_multiple_of_row(1, 2, -2)
A.with_rescale_row(1, 1, 0/3)
A.with_rescale_row(2, 1, 0/-19)
```

$$
\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 3 & 6 & 12 \\
4 & 2 & -3 & -2
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 3 & 6 & 12 \\
0 & 6 & -7 & -14
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 3 & 6 & 12 \\
0 & 0 & -19 & -38
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 1 & 2 & 4 \\
0 & 0 & -19 & -38
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 1 & 2 & 4 \\
0 & 0 & 1 & 2
\end{bmatrix}
$$

hasil matrix diatas diubah kembali menjadi sistem persamaan

$$\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 1 & 2 & 4 \\
0 & 0 & 1 & 2
\end{bmatrix}$$

dan dapat ditemukan bahwa

$$
\begin{cases}
x_1 - x_2 + x_3 = 3 \\
x_2 + 2x_3 = 4 \\
x_3 = 2
\end{cases}
$$

 dapat diketahui bahwa X3=2 kita subtitusikan ke persamaan kedua

$$
x_2 + 2(2) = 4
$$

$$
x_2 = 0
$$

lalu  hasil X2 kita subtitusikan ke persamaan pertama

$$
\begin{aligned}
x_1 - 0 + 2 &= 3 \\
x_1 + 2 &= 3 \\
x_1 &= 3 - 2 \\
x_1 &= 1
\end{aligned}
$$

bentuk himpunan penyelesaiannya (1,0, 2)S