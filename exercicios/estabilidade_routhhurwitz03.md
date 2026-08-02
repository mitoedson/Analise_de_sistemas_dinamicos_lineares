<h1>Estabilidade - Critério de Routh-Hurwitz - 03</h1>

Determine os valores da constante k para que todas as raízes dos seguintes polinômios tenham parte real negativa:

λ⁴ + kλ³ + λ² + λ + 1 = 0

---

Coeficientes: $a_0=1,\ a_1=k,\ a_2=1,\ a_3=1,\ a_4=1$

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | 1 |
|λ³| k | 1 | 0 |
|λ²| $b_1$ | $b_2$ | |
|λ¹| $c_1$ | $c_2$ | |
|λ⁰| $d_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & 1 \\ k & 1 \end{bmatrix}}{k} = -\frac{1-k}{k} = \frac{k-1}{k}, 
b_2 = -\frac{\begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix}}{k} = -\frac{-k}{k} = 1
```


| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | 1 |
|λ³| k | 1 | 0 |
|λ²| $\frac{k-1}{k}$ | 1 | 0 |
|λ¹| $c_1$ | $c_2$ | |
|λ⁰| $d_1$ | | |


```math
c_1 = -\frac{\begin{bmatrix} k & 1 \\ \frac{k-1}{k} & 1 \end{bmatrix}}{\frac{k-1}{k}} = -\frac{k-(\frac{k-1}{k})}{\frac{k-1}{k}} = -\frac{k^2-k+1}{k-1}, 
c_2 = -\frac{\begin{bmatrix} k & 0 \\ \frac{k-1}{k} & 0 \end{bmatrix}}{\frac{k-1}{k}} = -\frac{0}{\frac{k-1}{k}} = 0
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | 1 |
|λ³| k | 1 | 0 |
|λ²| $\frac{k-1}{k}$ | 1 | 0 |
|λ¹| $-\frac{k^2-k+1}{k-1}$ | 0 | |
|λ⁰| $d_1$ | | |

```math
d_1 = -\frac{\begin{bmatrix} \frac{k-1}{k} & 1 \\ -\frac{k^2-k+1}{k-1} & 0 \end{bmatrix}}{-\frac{k^2-k+1}{k-1}} = 1
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | 1 |
|λ³| k | 1 | 0 |
|λ²| $\frac{k-1}{k}$ | 1 | 0 |
|λ¹| $-\frac{k^2-k+1}{k-1}$ | 0 | |
|λ⁰| 1 | | |

Precisamos de $k-1>0 \Rightarrow k>1$, e $-k^2+k-1>0 \Rightarrow$ não possui raízes em k, logo $-k^2+k-1 < 0$ para todo k Real.

Portanto, não existe $k\in\mathbb{R}$

---

<a href="estabilidade_routhhurwitz_metodo.md">Método de Routh-Hurwitz</a>
