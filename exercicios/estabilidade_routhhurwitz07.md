<h1>Estabilidade - Critério de Routh-Hurwitz - 07</h1>

Analise a estabilidade do seguinte polinômio:

$λ^5 + 3λ^4 + 8λ^3 + 40λ^2 + 68λ + 60 = 0$

utilizando o critério de Routh. Quantas raízes do polinômio tem parte real positiva?

---

Coeficientes: $a_0=1,\ a_1=3,\ a_2=8,\ a_3=40,\ a_4=68,\ a_5=60$

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|$λ^5$| 1 | 8 | 68 |
|$λ^4$| 3 | 40 | 60 |
|$λ^3$| $b_1$ | $b_2$ | |
|$λ^2$| $c_1$ | $c_2$ | |
|$λ^1$| $d_1$ | $d_2$ | |
|$λ^0$| $e_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & 8 \\ 3 & 40 \end{bmatrix}}{3} = -\frac{16}{3}, 
```
```math
b_2 = -\frac{\begin{bmatrix} 1 & 68 \\ 3 & 60 \end{bmatrix}}{3} = 48
```


| | col 1 | col 2 | col 3 |
|---|---|---|---|
|$λ^5$| 1 | 8 | 68 |
|$λ^4$| 3 | 40 | 60 |
|$λ^3$| $-\frac{16}{3}$ | 48 | 0 |
|$λ^2$| 67 | 60 | 0 |
|$λ^1$| $\frac{3536}{67}$ | 0 | |
|$λ^0$| 60 | | |




