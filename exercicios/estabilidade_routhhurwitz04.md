<h1>Estabilidade - Critério de Routh-Hurwitz - 04</h1>

Determine os valores da constante k para que todas as raízes dos seguintes polinômios tenham parte real negativa:

λ⁴ + λ³ + λ² + λ + k = 0

---

Coeficientes: $a_0=1,\ a_1=1,\ a_2=1,\ a_3=1,\ a_4=k$

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | k |
|λ³| 1 | 1 | 0 |
|λ²| $b_1$ | $b_2$ | |
|λ¹| $c_1$ | $c_2$ | |
|λ⁰| $d_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & 1 \\ 1 & 1 \end{bmatrix}}{1} = -\frac{0}{1} = 0, 
b_2 = -\frac{\begin{bmatrix} 1 & k \\ 1 & 0 \end{bmatrix}}{1} = -\frac{-k}{1} = k
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | k |
|λ³| 1 | 1 | 0 |
|λ²| 0 | k | |
|λ¹| $c_1$ | $c_2$ | |
|λ⁰| $d_1$ | | |


Já na linha λ² aparece **0 na primeira coluna**, independentemente de $k$. Isso por si só impede estabilidade estrita (sinaliza raízes sobre o eixo imaginário ou problema na construção do array).

Portanto, não existe $k\in\mathbb{R}$

---

<a href="estabilidade_routhhurwitz_metodo.md">Método de Routh-Hurwitz</a>



