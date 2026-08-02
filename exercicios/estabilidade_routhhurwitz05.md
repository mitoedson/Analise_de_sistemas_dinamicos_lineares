<h1>Estabilidade - Critério de Routh-Hurwitz - 05</h1>

Determine os valores da constante k para que todas as raízes dos seguintes polinômios tenham parte real negativa:

λ⁵ + λ⁴ + kλ³ + λ² + λ + k = 0

---

Coeficientes: $a_0=1,\ a_1=1,\ a_2=k,\ a_3=1,\ a_4=1,\ a_5=k$


| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| $b_1$ | $b_2$ | |
|λ²| $c_1$ | $c_2$ | |
|λ¹| $d_1$ | $d_1$ | |
|λ⁰| $e_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & k \\ 1 & 1 \end{bmatrix}}{1} = -\frac{1-k}{1} = k-1, 
b_2 = -\frac{\begin{bmatrix} 1 & 1 \\ 1 & k \end{bmatrix}}{1} = -\frac{k-1}{1} = -k+1 
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| k-1 | -k+1 | 0 |
|λ²| $c_1$ | $c_2$ | |
|λ¹| $d_1$ | $d_1$ | |
|λ⁰| $e_1$ | | |

```math
c_1 = -\frac{\begin{bmatrix} 1 & 1 \\ k-1 & -k+1 \end{bmatrix}}{k-1} = -\frac{-k+1-(k-1))}{k-1} = 2, 
c_2 = -\frac{\begin{bmatrix} 1 & k \\ k-1 & 0 \end{bmatrix}}{k-1} = -\frac{-k^2+k}{k-1} = k 
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| k-1 | -k+1 | 0 |
|λ²| 2 | k | 0 |
|λ¹| $d_1$ | $d_1$ | |
|λ⁰| $e_1$ | | |


```math
d_1 = -\frac{\begin{bmatrix} k-1 & -k+1 \\ 2 & k \end{bmatrix}}{2} = -\frac{k^2+k-2}{2}, 
d_2 = -\frac{\begin{bmatrix} k-1 & 0 \\ 2 & 0 \end{bmatrix}}{2} = -\frac{0}{2} = 0 
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| k-1 | -k+1 | 0 |
|λ²| 2 | k | 0 |
|λ¹| $-\frac{k^2+k-2}{2}$ | 0 | |
|λ⁰| $e_1$ | | |

```math
e_1 = -\frac{\begin{bmatrix} 2 & k \\ -\frac{k^2+k-2}{2} & 0 \end{bmatrix}}{-\frac{k^2+k-2}{2}} = -\frac{k\frac{k^2+k-2}{2}}{-\frac{k^2+k-2}{2}} = k 
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| k-1 | -k+1 | 0 |
|λ²| 2 | k | 0 |
|λ¹| $-\frac{k^2+k-2}{2}$ | 0 | |
|λ⁰| k | | |

Precisamos de $k-1>0 \Rightarrow k>1$, k>0, e $-\frac{k^2+k-2}{2} \Rightarrow -k^2-k+2 > 0$. Porém, $-k^2-k+2 > 0$, se e somente se, -2 < k < 1, e k > 1. 

Portanto, não existe $k\in\mathbb{R}$

---

<a href="estabilidade_routhhurwitz_metodo.md">Método de Routh-Hurwitz</a>
