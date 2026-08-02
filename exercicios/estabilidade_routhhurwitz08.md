<h1>Estabilidade - Critério de Routh-Hurwitz - 07</h1>

Analise a estabilidade do seguinte polinômio:

$P_1(\lambda)=λ^3 + (k+2)λ^2 + (2k+1)λ + (k+1)$

(a) Escreva as condições de Hurwitz para um polinômio cúbico.

(b) Determine o intervalo de valores de k para o qual todas as raízes possuem parte real negativa.

(c) Escolha dois valores de k: um estável e um instável. Explique a escolha.

---

(b) Matriz de Hurwitz

```math
H = \begin{pmatrix} k+2 & k+1 & 0\\ 1 & 2k+1 & 0\\ 0 & k+2 & k+1 \end{pmatrix}
```

```math
\Delta_1 = k+2 > 0, \quad \Delta_2 = \begin{vmatrix} k+2 & k+1 \\ 1 & 2k+1 \end{vmatrix} > 0, \quad \quad \Delta_3 = \begin{vmatrix} k+2 & k+1 & 0\\ 1 & 2k+1 & 0\\ 0 & k+2 & k+1 \end{vmatrix} > 0
```



---

<a href="estabilidade_routhhurwitz_metodo.md">Método de Routh-Hurwitz</a>
