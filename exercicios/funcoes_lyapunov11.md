<h1>Estabilidade - Funções de Lyapunov - 11</h1>

Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} -1 & 0 \\ 0 & -1 \end{bmatrix} x
```
---
Usando o fluxo: equação de Lyapunov (com $Q=I$) → checar $P$ pelos menores principais líderes → confirmar/classificar o tipo via $T$ e $D$ de $A$.

## Passo 1 — calcular $A^T$

Como $A$ já é simétrica (matriz diagonal), $A^T=A$:

```math
A^T=\begin{bmatrix}-1&0\\0&-1\end{bmatrix}
```

## Passo 2 — calcular $A^TP$

```math
A^TP=\begin{bmatrix}-1&0\\0&-1\end{bmatrix}\begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix}
```

**Elemento (1,1):** $(-1)(p_{11})+(0)(p_{12}) = -p_{11}$

**Elemento (1,2):** $(-1)(p_{12})+(0)(p_{22}) = -p_{12}$

**Elemento (2,1):** $(0)(p_{11})+(-1)(p_{12}) = -p_{12}$

**Elemento (2,2):** $(0)(p_{12})+(-1)(p_{22}) = -p_{22}$

```math
A^TP=\begin{bmatrix}-p_{11}&-p_{12}\\-p_{12}&-p_{22}\end{bmatrix}
```

## Passo 3 — calcular $PA$

```math
PA=\begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix}\begin{bmatrix}-1&0\\0&-1\end{bmatrix}
```

**Elemento (1,1):** $(p_{11})(-1)+(p_{12})(0)=-p_{11}$

**Elemento (1,2):** $(p_{11})(0)+(p_{12})(-1)=-p_{12}$

**Elemento (2,1):** $(p_{12})(-1)+(p_{22})(0)=-p_{12}$

**Elemento (2,2):** $(p_{12})(0)+(p_{22})(-1)=-p_{22}$

```math
PA=\begin{bmatrix}-p_{11}&-p_{12}\\-p_{12}&-p_{22}\end{bmatrix}
```

## Passo 4 — somar $A^TP+PA$

```math
A^TP+PA=\begin{bmatrix}-2p_{11}&-2p_{12}\\-2p_{12}&-2p_{22}\end{bmatrix}
```

Igualando a $-I=\begin{bmatrix}-1&0\\0&-1\end{bmatrix}$:

$$-2p_{11}=-1 \;\Rightarrow\; p_{11}=0{,}5$$
$$-2p_{12}=0 \;\Rightarrow\; p_{12}=0$$
$$-2p_{22}=-1 \;\Rightarrow\; p_{22}=0{,}5$$

## Passo 5 — checar se $P$ é positiva definida

```math
P=\begin{bmatrix}0{,}5&0\\0&0{,}5\end{bmatrix}
```

**Menor 1:** $p_{11}=0{,}5>0$ ✓

**Menor 2 (determinante):** $\det(P)=(0{,}5)(0{,}5)-0^2=0{,}25>0$ ✓

**$P$ é positiva definida!** → **assintoticamente estável**

## Passo 6 — classificar o tipo via traço e determinante de $A$

$$T=\text{traço}(A)=-1+(-1)=-2$$
$$D=\det(A)=(-1)(-1)-(0)(0)=1$$

$D=1>0$; $T^2-4D=4-4=0$ → autovalores reais e **repetidos** ($\lambda=T/2=-1$, autovalor duplo); $T<0$ → **nó estável**

Aqui, como a matriz $A$ já é diagonal com autovalores repetidos ($-1,-1$) e é **diagonalizável** (na verdade já está diagonal), esse é o caso de **nó estável "próprio"** (também chamado de nó em estrela) — todas as trajetórias entram na origem em linha reta, em qualquer direção.

## Conclusão

$$P>0 \;\Rightarrow\; \text{assintoticamente estável}; \qquad T<0,\ D>0,\ T^2-4D=0 \;\Rightarrow\; \textbf{nó estável}$$


---

Esse item foi o mais simples de todos (matriz já diagonal, sem termos cruzados).
