<h1>Estabilidade - Funções de Lyapunov - 02</h1>

(b)
```math
\frac{dx}{dt} = \begin{bmatrix} 5 & -1 \\ 3 & 1 \end{bmatrix} x
```
---

## Passo 1 — montar a equação de Lyapunov com $Q=I$

```math
A^T=\begin{bmatrix}5&3\\-1&1\end{bmatrix}
```

Calculando $A^TP$:
```math
$$A^TP=\begin{bmatrix}5&3\\-1&1\end{bmatrix}\begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix}=\begin{bmatrix}5p_{11}+3p_{12} & 5p_{12}+3p_{22}\\-p_{11}+p_{12} & -p_{12}+p_{22}\end{bmatrix}$$
```

Calculando $PA$:
```math
$$PA=\begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix}\begin{bmatrix}5&-1\\3&1\end{bmatrix}=\begin{bmatrix}5p_{11}+3p_{12} & -p_{11}+p_{12}\\5p_{12}+3p_{22} & -p_{12}+p_{22}\end{bmatrix}$$
```

Somando ($A^TP+PA$)=-I:
```math
$$\begin{bmatrix}10p_{11}+6p_{12} & -p_{11}+6p_{12}+3p_{22}\\ -p_{11}+6p_{12}+3p_{22} & -2p_{12}+2p_{22}\end{bmatrix}=\begin{bmatrix}-1&0\\0&-1\end{bmatrix}$$
```

## Passo 2 — sistema de equações

```math
10p_{11}+6p_{12}=-1(i)
```
```math
-p_{11}+6p_{12}+3p_{22}=0 (ii)
```
```math
-2p_{12}+2p_{22}=-1 (iii)
```

## Passo 3 — resolver

Da (iii): $p_{22}=p_{12}-\dfrac12$

Substituindo em (ii): $-p_{11}+6p_{12}+3\left(p_{12}-\dfrac12\right)=0 \Rightarrow -p_{11}+9p_{12}=\dfrac32 \Rightarrow p_{11}=9p_{12}-\dfrac32$

Substituindo em (i): $10\left(9p_{12}-\dfrac32\right)+6p_{12}=-1$
$$90p_{12}-15+6p_{12}=-1 \Rightarrow 96p_{12}=14 \Rightarrow p_{12}=\frac{7}{48}$$

Logo: 
$p_{11}=9\left(\dfrac{7}{48}\right)-\dfrac32=\dfrac{63}{48}-\dfrac{72}{48}=-\dfrac{9}{48}=-\dfrac{3}{16}$
$p_{22} = \frac{7}{48}-\dfrac{1}{2} = -\frac{17}{48}$

## Passo 4 — checar se $P$ é positiva definida

Já no primeiro menor principal: $p_{11}=-\dfrac{3}{16}<0$ ✗

**$P$ falha imediatamente** — nem precisa calcular $p_{22}$ ou o determinante, já que o critério de Sylvester exige que *todos* os menores sejam positivos, e o primeiro já falhou. O sistema não é assintoticamente estável.

## Passo 5 — como $P$ falhou, confirmar via traço e determinante de $A$

$$T=\text{traço}(A)=5+1=6>0$$
$$D=\det(A)=(5)(1)-(-1)(3)=5+3=8>0$$

$D>0$, $T^2-4D=36-32=4>0$ (autovalores reais), e $T>0$ → **nó instável**

Podemos calcular os autovalores de $$\lambda^2-6\lambda+8 = 0$$ 

## Conclusão

**Instável (nó instável)** 

