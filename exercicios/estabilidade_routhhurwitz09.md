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
|$λ^5$| 1 | k+3 | k |
|$λ^4$| 2 | 2k+1 | 0 |
|$λ^3$| $b_1$ | $b_2$ | |
|$λ^2$| $c_1$ | $c_2$ | |
|$λ^1$| $d_1$ | $d_2$ | |
|$λ^0$| $e_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & 8 \\ 3 & 40 \end{bmatrix}}{3} = -\frac{16}{3}, 
b_2 = -\frac{\begin{bmatrix} 1 & 68 \\ 3 & 60 \end{bmatrix}}{3} = 48
```
```math
c_1 = -\frac{\begin{bmatrix} 3 & 40 \\ -\frac{16}{3} & 48 \end{bmatrix}}{-\frac{16}{3}} = 67, 
c_2 = -\frac{\begin{bmatrix} 3 & 60 \\ -\frac{16}{3} & 0 \end{bmatrix}}{-\frac{16}{3}} = 60
```
```math
d_1 = -\frac{\begin{bmatrix} -\frac{16}{3} & 48 \\ 67 & 60 \end{bmatrix}}{67} = \frac{3536}{67}, 
d_2 = 0
```
```math
e_1 = -\frac{\begin{bmatrix} 67 & 60 \\ \frac{3536}{67} & 0 \end{bmatrix}}{\frac{3536}{67}} = 60 
```


| | col 1 | col 2 | col 3 |
|---|---|---|---|
|$λ^5$| 1 | 8 | 68 |
|$λ^4$| 3 | 40 | 60 |
|$λ^3$| $-\frac{16}{3}$ (primeira troca de sinal)| 48 | 0 |
|$λ^2$| 67 (segunda troca de sinal)| 60 | 0 |
|$λ^1$| $\frac{3536}{67}$ | 0 | |
|$λ^0$| 60 | | |


O critério de Routh-Hurwitz diz:

 **O número de trocas de sinal na primeira coluna = número de raízes com parte real positiva**

**2 raízes do polinômio têm parte real positiva** 

Como há raízes com parte real positiva, o sistema associado a esse polinômio (se fosse um polinômio característico de um sistema linear) seria **instável**.





---

<a href="estabilidade_routhhurwitz_metodo.md">Método de Routh-Hurwitz</a>
