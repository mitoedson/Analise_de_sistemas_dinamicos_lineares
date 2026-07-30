<h1>Estabilidade - Critério de Routh-Hurwitz - 02</h1>

Analise a estabilidade do seguinte polinômio:

$λ^3+ kλ^2 + kλ + 4 = 0$

utilizando o critério de Hurwitz. Para que valores de k o sistema é estável.

---

### Condição necessária
1. Todos os coeficientes $a_i$ devem existir (nenhum estar ausente/zero).
2. Todos os coeficientes devem ter o mesmo sinal.

Assim, k > 0.

### Montagem da tabela

$a_0 = 1, a_1 = k, a_2 = k, a_3 = 4$

| $s^n$ | $a_n$ | $a_{n-2}$ | $a_{n-4}$ | ... |
|---|---|---|---|---|
| $s^{n-1}$ | $a_{n-1}$ | $a_{n-3}$ | $a_{n-5}$ | ... |
| $s^{n-2}$ | $b_1$ | $b_2$ | $b_3$ | ... |
| $s^{n-3}$ | $c_1$ | $c_2$ | ... | |
| $\vdots$ | | | | |
| $s^0$ | ... | | | |

