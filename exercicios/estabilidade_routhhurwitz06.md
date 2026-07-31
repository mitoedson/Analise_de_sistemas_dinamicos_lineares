<h1>Estabilidade - Critério de Routh-Hurwitz - 06</h1>

Analise a estabilidade do seguinte polinômio:

$λ^3+ kλ^2 + kλ + 4 = 0$

utilizando o critério de Hurwitz. Para que valores de k o sistema é estável.

---

### Pelo critério de Hurwitz:

**Critério de Hurwitz:** monta a **matriz de Hurwitz** $H$, uma matriz $n \times n$ construída a partir dos coeficientes do polinômio, organizados assim (para $a_n s^n + a_{n-1}s^{n-1} + \dots + a_0$):

```math
H = \begin{pmatrix} a_{n-1} & a_{n-3} & a_{n-5} & \cdots \\ a_n & a_{n-2} & a_{n-4} & \cdots \\ 0 & a_{n-1} & a_{n-3} & \cdots \\ 0 & a_n & a_{n-2} & \cdots \\ \vdots & & & \ddots \end{pmatrix}
```

(cada coluna desce um índice, preenchendo com zero quando o coeficiente não existe)

O critério então diz: o sistema é estável se, e somente se, **todos os menores principais líderes** (os determinantes $\Delta_1, \Delta_2, \dots, \Delta_n$, tomados dos blocos superiores-esquerdos crescentes da matriz) forem **positivos**:

```math
\Delta_1 = a_{n-1} > 0, \quad \Delta_2 = \begin{vmatrix} a_{n-1} & a_{n-3} \\ a_n & a_{n-2} \end{vmatrix} > 0, \quad \dots, \quad \Delta_n > 0
```

### Montagem da matriz de Hurwitz

```math
H = \begin{pmatrix} k & 4 & 0 \\ 1 & k & 0 \\ 0 & k & 4 \\ \end{pmatrix}
```

```math
\Delta_1 = |k| > 0 \Rightarrow k > 0
\Delta_2 = \begin{vmatrix} k & 4 \\ 1 & k \end{vmatrix} > 0 \Rightarrow k^2 - 4 > 0
\Delta_3 = \begin{vmatrix} k & 4 & 0 \\ 1 & k & 0 \\ 0 & k & 4 \\ \end{vmatrix} > 0

```

---

### Condição necessária pelo critério de Routh
1. Todos os coeficientes $a_i$ devem existir (nenhum estar ausente/zero).
2. Todos os coeficientes devem ter o mesmo sinal.

Coeficientes: $a_0=1,\ a_1=k,\ a_2=k,\ a_3=4$

Assim, k > 0.

**Critério de Routh:** monta a tabela recursiva que vimos, e verifica sinais na primeira coluna.

### Montagem da tabela

| $λ^3$ | $a_0$ | $a_2$| $a_4$ | ... |
|---|---|---|---|---|
| $λ^2$ | $a_1$ | $a_3$ | $a_5$ | ... |
| $λ^1$ | $b_1$ | $b_2$ | $b_3$ | ... |
| $λ^0$ | $c_1$ | $c_2$  | ... | ... |

```math
b_1 = -\frac{\begin{bmatrix} a_0 & a_2 \\ a_1 & a_3 \end{bmatrix}}{a_1}, 
b_2 = -\frac{\begin{bmatrix} a_0 & a_4 \\ a_1 & a_5 \end{bmatrix}}{a_1}, 
c_1 = -\frac{\begin{bmatrix} a_1 & a_3 \\ b_1 & b_2 \end{bmatrix}}{b_1}

```

Assim, para $a_0 = 1, a_1 = k, a_2 = k, a_3 = 4$:

| $λ^3$ | 1 | k| 0 | ... |
|---|---|---|---|---|
| $λ^2$ | k | 4 | 0 | ... |
| $λ^1$ | $b_1$ | $b_2$ |  | ... |
| $λ^0$ | $c_1$ |   |  | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & k \\ k & 4 \end{bmatrix}}{k} = -\frac{-k^2+4}{k} = \frac{k^2-4}{k}, 
b_2 = -\frac{\begin{bmatrix} 1 & 0 \\ k & 0 \end{bmatrix}}{k} = 0
```

| $λ^3$ | 1 | k| 0 | ... |
|---|---|---|---|---|
| $λ^2$ | k | 4 | 0 | ... |
| $λ^1$ | $\frac{k^2-4}{k}$ | $0$ |  | ... |
| $λ^0$ | $c_1$ |  |  | |

```math
c_1 = -\frac{\begin{bmatrix} k & 4 \\ \frac{k^2-4}{k} & 0 \end{bmatrix}}{k} = -\frac{-4(\frac{k^2-4}{k})}{\frac{k^2-4}{k}} = 4 
```
| $λ^3$ | 1 | k| 0 | ... |
|---|---|---|---|---|
| $λ^2$ | k | 4 | 0 | ... |
| $λ^1$ | $\frac{k^2-4}{k}$ | $0$ |  | ... |
| $λ^0$ | 4 |  |  | |


Precisamos que k > 0, e $\frac{k^2-4}{k} > 0 \Rightarrow  -2 < k < 2$. 

Portanto, k > 2.

---

**Por que dão o mesmo resultado:**

Não é coincidência — existe uma relação direta entre os elementos da primeira coluna da tabela de Routh e essas razões de determinantes de Hurwitz ($\Delta_k / \Delta_{k-1}$). Ou seja, o sinal de cada elemento da tabela de Routh corresponde ao sinal de um desses menores. Por isso os dois critérios são matematicamente equivalentes — Routh é essencialmente uma forma mais eficiente computacionalmente de obter a mesma informação que os determinantes de Hurwitz dão de forma mais "direta" mas com mais trabalho algébrico (calcular determinantes de ordem crescente é mais custoso que a recursão da tabela).

Na prática, por isso o método de Routh (tabular) é o mais usado em disciplinas de controle — mesmo resultado, menos conta.
