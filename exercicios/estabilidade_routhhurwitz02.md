<h1>Estabilidade - Critério de Routh-Hurwitz - 02</h1>

Determine os valores da constante k para que todas as raízes dos seguintes polinômios tenham parte real negativa:

λ³ + λ² + λ + k = 0

---

Pelo critério de Routh:

Coeficientes: $a_0=1,\ a_1=1,\ a_2=1,\ a_3=k$

| | col 1 | col 2 | col 3|
|---|---|---|---|
|λ³| 1 | 1 | 0 |
|λ²| 1 | k | 0 |
|λ¹| $b_1$ | $b_2$ | |
|λ⁰| $c_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & 1 \\ 1 & k \end{bmatrix}}{1} = -\frac{k-1}{1} = -k+1, 
b_2 = -\frac{\begin{bmatrix} 1 & 0 \\ 1 & 0 \end{bmatrix}}{1} = 0
```

| | col 1 | col 2 | col 3|
|---|---|---|---|
|λ³| 1 | 1 | 0 |
|λ²| 1 | k | 0 |
|λ¹| -k+1 | 0 | |
|λ⁰| $c_1$ | | |


```math
c_1 = -\frac{\begin{bmatrix} 1 & k \\ -k+1 & 0 \end{bmatrix}}{-k+1} = -\frac{0-(-k^2+k)}{-k+1} = -\frac{-k(-k+1)}{-k+1} = k
```

| | col 1 | col 2 |
|---|---|---|
|λ³| 1 | 1 |
|λ²| k | 1 |
|λ¹| -k+1 | 0 |
|λ⁰| k | |

Precisamos de $1-k>0 \Rightarrow k<1$ e $k>0$.

Portanto, $0<k<1$

---

<a href="estabilidade_routhhurwitz_metodo.md">Método de Routh-Hurwitz</a>
