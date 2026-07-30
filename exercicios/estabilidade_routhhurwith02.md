<h1>Estabilidade - Critério de Routh-Hurwitz - 02</h1>

Analise a estabilidade do seguinte polinômio:

$λ^3+ kλ^2 + kλ + 4 = 0$

utilizando o critério de Hurwitz. Para que valores de k o sistema é estável.

---

### Condição necessária pelo critério de Routh
1. Todos os coeficientes $a_i$ devem existir (nenhum estar ausente/zero).
2. Todos os coeficientes devem ter o mesmo sinal.

Assim, k > 0.

### Montagem da tabela

| $λ^3$ | $a_0$ | $a_2$| $a_4$ | ... |
|---|---|---|---|---|
| $λ^2$ | $a_1$ | $a_3$ | $a_5$ | ... |
| $λ^1$ | $b_1$ | $b_2$ | $b_3$ | ... |
| $λ^0$ | $c_1$ | $c_2$  | ... | ... |

$a_0 = 1, a_1 = k, a_2 = k, a_3 = 4$

| $λ^3$ | 1 | k| 0 | ... |
|---|---|---|---|---|
| $λ^2$ | k | 4 | 0 | ... |
| $λ^1$ | $b_1$ | $b_2$ |  | ... |
| $λ^0$ | $c_1$ | $c_2$  |  | |

```math
b_1 = -\frac{\begin{bmatrix} a_0 & a_2 \\ a_1 & a_3 \end{bmatrix}}{a_1}
b_2 = -\frac{\begin{bmatrix} a_1 & a_3 \\ a_1 & a_5 \end{bmatrix}}{a_1}
c_1 = -\frac{\begin{bmatrix} a_1 & b_3 \\ b_1 & b_2 \end{bmatrix}}{b_1}

```
