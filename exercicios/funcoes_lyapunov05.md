<h1>Estabilidade - Funções de Lyapunov - 05</h1>

Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} 1 & -5 \\ 1 & -3 \end{bmatrix} x
```
---
Usando o fluxo: equação de Lyapunov (com $Q=I$) → checar $P$ pelos menores principais líderes → confirmar/classificar o tipo via $T$ e $D$ de $A$.

## Passo 1 — montar a equação de Lyapunov com $Q=I$

```math
A^T=\begin{pmatrix}1&1\\-5&-3\end{pmatrix}
```

**Calculando $A^TP$:**
```math
A^TP=\begin{pmatrix}1&1\\-5&-3\end{pmatrix}\begin{pmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{pmatrix}=\begin{pmatrix}p_{11}+p_{12}&p_{12}+p_{22}\\-5p_{11}-3p_{12}&-5p_{12}-3p_{22}\end{pmatrix}
```

**Calculando $PA$** (transposta de $A^TP$, já que $P$ é simétrica):
```math
PA=\begin{pmatrix}p_{11}+p_{12}&-5p_{11}-3p_{12}\\p_{12}+p_{22}&-5p_{12}-3p_{22}\end{pmatrix}
```

**Somando $A^TP+PA$:**
```math
A^TP+PA=\begin{pmatrix}2p_{11}+2p_{12} & -5p_{11}-2p_{12}+p_{22}\\ -5p_{11}-2p_{12}+p_{22} & -10p_{12}-6p_{22}\end{pmatrix}
```

Igualando a $-I$:

$$2p_{11}+2p_{12}=-1 \quad (i)$$
$$-5p_{11}-2p_{12}+p_{22}=0 \quad (ii)$$
$$-10p_{12}-6p_{22}=-1 \quad (iii)$$

## Passo 2 — resolver o sistema

Da (i): $p_{12}=\dfrac{-1-2p_{11}}{2}=-\dfrac12-p_{11}$

Substituindo em (ii):
$$-5p_{11}-2\left(-\frac12-p_{11}\right)+p_{22}=0$$
$$-5p_{11}+1+2p_{11}+p_{22}=0$$
$$-3p_{11}+p_{22}=-1 \;\Rightarrow\; p_{22}=3p_{11}-1$$

Substituindo em (iii):
$$-10\left(-\frac12-p_{11}\right)-6(3p_{11}-1)=-1$$
$$5+10p_{11}-18p_{11}+6=-1$$
$$-8p_{11}+11=-1$$
$$-8p_{11}=-12 \;\Rightarrow\; p_{11}=\frac{12}{8}=\frac32$$

Logo:
$$p_{12}=-\frac12-\frac32=-2$$
$$p_{22}=3\left(\frac32\right)-1=\frac92-1=\frac72$$

## Passo 3 — checar se $P$ é positiva definida

```math
P=\begin{pmatrix}\dfrac32&-2\\-2&\dfrac72\end{pmatrix}
```

**Menor 1:** $p_{11}=\dfrac32>0$ ✓

**Menor 2 (determinante):**
$$\det(P)=\left(\frac32\right)\left(\frac72\right)-(-2)^2=\frac{21}{4}-4=\frac{21}{4}-\frac{16}{4}=\frac54>0 \checkmark$$

**$P$ é positiva definida!** → **assintoticamente estável**

## Passo 4 — classificar o tipo via traço e determinante de $A$

$$T=\text{traço}(A)=1+(-3)=-2$$
$$D=\det(A)=(1)(-3)-(-5)(1)=-3+5=2$$

$D=2>0$; $T^2-4D=4-8=-4<0$ (complexos); $T=-2<0$ → **foco estável**

## Conclusão

$$P>0 \;\Rightarrow\; \text{assintoticamente estável}; \qquad T<0,\ D>0,\ T^2-4D<0 \;\Rightarrow\; \textbf{foco estável}$$

