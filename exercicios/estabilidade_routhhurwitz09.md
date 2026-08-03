<h1>Estabilidade - Critério de Routh-Hurwitz - 09</h1>

Analise a estabilidade do seguinte polinômio:

$P_2(\lambda)=λ^4 + 2λ^3 + (k+3)λ^2 + (2k+1)λ + k$

(a) Monte a tabela de Routh completa.

(b)  Determine os valores de k para estabilidade assintótica.

(c)  Para k = −1, determine o número de raízes com parte real positiva.

(d)  Para k = 1, explique por que o sistema passa no teste.

---

(a) Tabela de Routh

Coeficientes: $a_0=1,\ a_1=2,\ a_2=(k+3),\ a_3=(2k+1),\ a_4=k$

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|$λ^4$| 1 | k+3 | k |
|$λ^3$| 2 | 2k+1 | 0 |
|$λ^2$| $b_1$ | $b_2$ | |
|$λ^1$| $c_1$ | $c_2$ | |
|$λ^0$| $d_1$ | $d_2$ | |

(b)
```math
b_1 = -\frac{\begin{bmatrix} 1 & k+3 \\ 2 & 2k+1 \end{bmatrix}}{2} = \frac{5}{2}, 
b_2 = -\frac{\begin{bmatrix} 1 & k \\ 2 & 0 \end{bmatrix}}{2} = k
```
```math
c_1 = -\frac{\begin{bmatrix} 2 & 2k+1 \\ \frac{5}{2} & k \end{bmatrix}}{\frac{5}{2}} = \frac{6k}{5}+1, 
c_2 = -\frac{\begin{bmatrix} 2 & 0 \\ \frac{5}{2} & 0 \end{bmatrix}}{\frac{5}{2}} = 0
```
```math
d_1 = -\frac{\begin{bmatrix} \frac{5}{2} & k \\ \frac{6k}{5}+1 & 0 \end{bmatrix}}{\frac{6k}{5}+1}= k
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|$λ^4$| 1 | k+3 | k |
|$λ^3$| 2 | 2k+1 | 0 |
|$λ^2$| $\frac{5}{2}$ | k | 0 |
|$λ^1$| $\frac{6k}{5} +1$ | 0 | |
|$λ^0$| k | | |

Para os valores de k para estabilidade assintótica, analisamos a primeira coluna da tabela:

$\frac{6k}{5}+1 > 0 \Rightarrow k > -\frac{5}{6}$, $k>0$. Logo, $k>0$ para estabilidade assintótica.


(c) Para k = −1, determine o número de raízes com parte real positiva.

$\frac{6(-1)}{5}+1 > 0 \Rightarrow -\frac{1}{5}<0$, $(-1)<0$. Temos uma troca de sinal, portanto, uma raíz com parte real positiva.


(d) Para k = 1, explique por que o sistema passa no teste.

$\frac{6(1)}{5}+1 > 0 \Rightarrow \frac{11}{5}$, $(1)>0$. Sim, passa no teste, pois todos elementos da primeira coluna são positivos. 

---

<a href="estabilidade_routhhurwitz_metodo.md">Método de Routh-Hurwitz</a>
