# Matriks Invers

## Determinan
$$
\begin{equation*}
\det A=\sum_{j=1}^n(-1)^{1+j}a_{1j}\det A_{1  j}=a_{11}\det A_{11}-a_{12} A_{12}+\cdots +(-1)^{1+n}a_{1n}\det A_{1  n}\text{.}
\end{equation*}
$$

##Minor & Ekspansi baris/kolom
$$
\begin{equation*}
\sum_{k=1}^n(-1)^{k+j}a_{kj}M_{kj}
\end{equation*}
$$

## Rumus Invers

$$
A^{-1} = \frac{1}{\det(A)} \cdot \operatorname{adj}(A)
$$

## Rumus Adjoint
$$
\begin{equation*}
(adj A)_{ij}=(-1)^{i+j}M_{ji}\text{.}
\end{equation*}
$$

Jika, 

$$
A =
\begin{bmatrix}
1 & 1 & 1 & 1 \\
2 & -1 & 1 & -1 \\
1 & 2 & -1 & 1 \\
3 & -1 & 2 & 1
\end{bmatrix}
$$

Menghitung Determinan (ekspansi baris pertama)

$$
\det(A) = a_{11}M_{11} + a_{12}M_{12} + a_{13}M_{13} + a_{14}M_{14}
$$
$$
M_{ij} = (-1)^{i+j} M_{ij}
$$

$$
\begin{split}
\det(A)=
1
\left|
\begin{array}{ccc}
-1 & 1 & -1\\
2 & -1 & 1\\
-1 & 2 & 1
\end{array}
\right|
-
1
\left|
\begin{array}{ccc}
2 & 1 & -1\\
1 & -1 & 1\\
3 & 2 & 1
\end{array}
\right|
+
1
\left|
\begin{array}{ccc}
2 & -1 & -1\\
1 & 2 & 1\\
3 & -1 & 1
\end{array}
\right|
-
1
\left|
\begin{array}{ccc}
2 & -1 & 1\\
1 & 2 & -1\\
3 & -1 & 2
\end{array}
\right|
\end{split}
$$

Determinan, 

$$
\det(A)=13
$$

Invers Matriks,

$$
\begin{split}
A^{-1}=
\frac{1}{13}
\left[
\begin{array}{cccc}
-3 & 3 & 4 & 2\\
9 & 4 & 1 & -6\\
11 & 2 & -6 & -3\\
-4 & -9 & 1 & 7
\end{array}
\right]
\end{split}
$$

# Tugas 2: Evaluasi Determinan dan Matriks
# A. Hitunglah determinan matriks dengan ekspansi baris

## Rumus Determinan

$$
\det(A) = \sum_{k=1}^{n} (-1)^{i+k} \, a_{ik} \, M_{ik}
$$

---

## 1. Matriks 2×2

$$
A =
\begin{bmatrix}
-7 & -5 \\
1 & 4
\end{bmatrix}
$$

### Langkah

$$
\det(A) = (-7)(4) - (-5)(1)
$$

$$
= -28 + 5 = -23
$$

---

## 2. Matriks 3×3 (Ekspansi baris ke-1)

$$
A =
\begin{pmatrix}
0 & 2 & -3 \\
1 & -2 & -1 \\
0 & 0 & 1
\end{pmatrix}
$$

### Rumus

$$
\det(A) = \sum_{k=1}^{3} (-1)^{1+k} a_{1k} M_{1k}
$$

### Ekspansi

$$
= (-1)^{1+1}(0)M_{11} + (-1)^{1+2}(2)M_{12} + (-1)^{1+3}(-3)M_{13}
$$

### Minor

$$
M_{12} =
\begin{vmatrix}
1 & -1 \\
0 & 1
\end{vmatrix}
= 1
$$

$$
M_{13} =
\begin{vmatrix}
1 & -2 \\
0 & 0
\end{vmatrix}
= 0
$$

### Hasil

$$
\det(A) = (0) + (-1)(2)(1) + (1)(-3)(0)
$$

$$
= -2
$$

---

## 3. Matriks 4×4

$$
A =
\begin{pmatrix}
1 & -3 & 1 & 1 \\
-3 & 1 & 1 & 1 \\
1 & 1 & -3 & 1 \\
1 & 1 & 1 & -3
\end{pmatrix}
$$

### Ekspansi baris pertama

$$
\det(A) = 1M_{11} - (-3)M_{12} + 1M_{13} - 1M_{14}
$$

### Hasil

$$
\det(A) = -256
$$

---

# B. Invers Matriks (Metode Adjoin)

## Rumus

$$
(adj\,A)_{ij} = (-1)^{i+j} M_{ji}
$$

$$
A^{-1} = \frac{1}{\det(A)} \, adj(A)
$$

---

## 4. Matriks 2×2

$$
A =
\begin{pmatrix}
-7 & -5 \\
1 & 4
\end{pmatrix}
$$

### Determinan

$$
\det(A) = -23
$$

### Adjoin

$$
adj(A) =
\begin{pmatrix}
4 & 5 \\
-1 & -7
\end{pmatrix}
$$

### Invers

$$
A^{-1} =
\frac{1}{-23}
\begin{pmatrix}
4 & 5 \\
-1 & -7
\end{pmatrix}
$$

---

## 5. Matriks 3×3

$$
A =
\begin{pmatrix}
0 & 2 & -3 \\
1 & -2 & -1 \\
0 & 0 & 1
\end{pmatrix}
$$

### Determinan

$$
\det(A) = -2
$$

### Kofaktor

$$
C =
\begin{pmatrix}
-2 & -1 & 0 \\
-2 & 0 & 0 \\
-8 & 3 & -2
\end{pmatrix}
$$

### Adjoin

$$
adj(A) =
\begin{pmatrix}
-2 & -2 & -8 \\
-1 & 0 & 3 \\
0 & 0 & -2
\end{pmatrix}
$$

### Invers

$$
A^{-1} = \frac{1}{-2} \, adj(A)
$$

---

## 6. Matriks 4×4

$$
A =
\begin{pmatrix}
1 & -3 & 1 & 1 \\
-3 & 1 & 1 & 1 \\
1 & 1 & -3 & 1 \\
1 & 1 & 1 & -3
\end{pmatrix}
$$

### Determinan

$$
\det(A) = -256
$$

### Adjoin

$$
adj(A) =
\begin{pmatrix}
16 & -16 & 16 & -16 \\
-16 & 16 & -16 & 16 \\
16 & -16 & 16 & -16 \\
-16 & 16 & -16 & 16
\end{pmatrix}
$$

### Invers

$$
A^{-1} = \frac{1}{-256} \, adj(A)
$$