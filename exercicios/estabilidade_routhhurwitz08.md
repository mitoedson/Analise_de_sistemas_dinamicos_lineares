<h1>Estabilidade - Critério de Routh-Hurwitz - 08</h1>

Analise a estabilidade do seguinte polinômio:

$P_1(\lambda)=λ^3 + (k+2)λ^2 + (2k+1)λ + (k+1)$

(a) Escreva as condições de Hurwitz para um polinômio cúbico.

(b) Determine o intervalo de valores de k para o qual todas as raízes possuem parte real negativa.

(c) Escolha dois valores de k: um estável e um instável. Explique a escolha.

---
(a) 
Os coeficientes do polinômio devem ser positivos. Ou seja, $$k+2>0 \Rightarrow k>-2$$, $$2k+1>0  \Rightarrow k>-\frac{1}{2}$$ e $$k+1>0 \Rightarrow k>-1$$

(b)
Observando a matriz de Hurwitz, os menores principais devem ser positivos

```math
H = \begin{pmatrix} k+2 & k+1 & 0\\ 1 & 2k+1 & 0\\ 0 & k+2 & k+1 \end{pmatrix}
```

```math
\Delta_1 = k+2 > 0, \rightarrow k > -2 
```
```math
\Delta_2 = \begin{vmatrix} k+2 & k+1 \\ 1 & 2k+1 \end{vmatrix} > 0 \Rightarrow  (k+2)(2k+1) - (k+1)(1) = 2k^2 + k + 4k + 2 - k - 1 = 2k^2 + 4k + 1 > 0
```
```math
\Rightarrow k < -1-\frac{1}{2}\sqrt{2}\qquad\text{ou}\qquad k > -1+\frac{1}{2}\sqrt{2}
```
```math
\Delta_3 = \begin{vmatrix} k+2 & k+1 & 0\\ 1 & 2k+1 & 0\\ 0 & k+2 & k+1 \end{vmatrix} > 0 \Rightarrow (k+2)(2k+1)(k+1) - (1)(k+1)(k+1) =
```
```math
= (k+1)[(2k+1)(k+2)-(k+1)] = (k+1)(2k^2+4k+k+2-k-1) = (k+1)(2k^2+4k+1) = 0 
```
```math
\Rightarrow k > - 1,\qquad  k < -1-\frac{1}{2}\sqrt{2}\qquad\text{ou}\qquad k > -1+\frac{1}{2}\sqrt{2}
```
Combinando-os, tem-se que: $$-1-\frac{1}{2}\sqrt{2} < k < -1\quad e \quad k >  -1+\frac{1}{2}\sqrt{2}$$

(c) Podemos optar para sistema estável, k = 2, pois é maior que $$-1+\frac{1}{2}\sqrt{2}$$

$$\Delta_1 = 2+2 > 0$$
$$\Delta_2 = 2(2)^2 + 4(2) + 1 = 17 > 0$$
$$\Delta_3 = (2+1)(2(2)^2+4(2)+1) = 3(17) = 51 > 0$$

Todos os menores principais são positivos, confirmando que é estável.


Podemos optar para sistema instável, k = -1, pois não pertence ao intervalo citado.

$$\Delta_1 = -1+2 > 0$$
$$\Delta_2 = 2(-1)^2 + 4(-1) + 1 = -1 < 0$$
$$\Delta_3 = (-1+1)(2(-1)^2+4(-1)+1) = 0 = 0$$

Confirma apenas positivo para o primeiro, e os demais não são. Confirma que é instável.

---

<a href="estabilidade_routhhurwitz_metodo.md">Método de Routh-Hurwitz</a>
