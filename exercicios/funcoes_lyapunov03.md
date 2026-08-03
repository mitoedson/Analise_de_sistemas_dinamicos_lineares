<h1>Funções de Lyapunov - 03</h1>

Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} 2 & -1 \\ 3 & -2 \end{bmatrix} x
```
---

## Passo 1 — montar a equação de Lyapunov com $Q=I$

```math
A^T=\begin{bmatrix}2&3\\-1&-2\end{bmatrix}
```

Calculando $A^TP+PA$ (mesmo processo de antes):

```math
A^TP+PA=\begin{bmatrix}4p_{11}+6p_{12} & -p_{11}+3p_{22}\\ -p_{11}+3p_{22} & -2p_{12}-4p_{22}\end{bmatrix}
```

Igualando a $-I$:

```math
4p_{11}+6p_{12}=-1 (i)
```
```math
-p_{11}+3p_{22}=0 (ii)
```
```math
-2p_{12}-4p_{22}=-1 (iii)
```

## Passo 2 — resolver o sistema

Da (ii): $p_{11}=3p_{22}$

Da (iii): $p_{12}=\dfrac{1-4p_{22}}{2}$

Substituindo os dois em (i):
```math
4(3p_{22})+6\left(\frac{1-4p_{22}}{2}\right)=-1
```
```math
12p_{22}+3(1-4p_{22})=-1
```
```math
12p_{22}+3-12p_{22}=-1
```
```math
3=-1
```

## Uma contradição! O sistema não tem solução para $P$

Isso é um resultado **diferente** dos itens anteriores: não é que $P$ deu "indefinida" — é que a equação de Lyapunov **nem sequer tem solução** para $Q=I$! Isso significa que o operador $A^TP+PA$ está numa situação **singular** (matematicamente, ligado a quando $\lambda_i+\lambda_j=0$ para algum par de autovalores de $A$ — chamada condição de ressonância).

Note que não podemos afirmar se o sistema é estável ou não. Além disso, o traço é zero. O sistema pode ser marginalmente estável (Centro) ou instável (ponto de sela).

## Confirmando via traço e determinante de $A$

$$T=\text{traço}(A)=2+(-2)=0$$
$$D=\det(A)=(2)(-2)-(-1)(3)=-4+3=-1$$

Repare: $T=0$ — exatamente a condição que causa essa "ressonância" (os dois autovalores somam zero, $\lambda_1+\lambda_2=0$, o que torna a equação de Lyapunov sem solução única).

Como $D=-1<0$: autovalores reais ($$\lambda_1=1, \lambda_2=-1$$), sinais opostos → **sela**

---

<a href="funcoes_lyapunov_metodo.md">Método Sistemático da Função de Lyapunov</a>

Usando o fluxo: equação de Lyapunov (com $Q=I$) → checar $P$ pelos menores principais líderes → confirmar/classificar o tipo via $T$ e $D$ de $A$.




