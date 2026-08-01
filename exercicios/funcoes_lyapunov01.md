<h1>Estabilidade - Funções de Lyapunov - 01</h1>

## O método sistemático (equação de Lyapunov)

Para $\dot{\mathbf x}=A\mathbf x$, escolhemos a candidata quadrática:
$$V(\mathbf x) = \mathbf x^T P \mathbf x$$

onde $P$ é uma matriz simétrica a determinar. Calculando $\dot V$:
$$\dot V = \dot{\mathbf x}^T P\mathbf x + \mathbf x^T P\dot{\mathbf x} = \mathbf x^T(A^TP+PA)\mathbf x$$

A ideia prática mais comum: **escolher $Q$ positiva definida** (geralmente $Q=I$, a identidade, por simplicidade) e resolver a **equação de Lyapunov**:
$$A^TP+PA = -Q$$

Se conseguirmos encontrar $P$ **positiva definida** que resolve essa equação, então $V=\mathbf x^TP\mathbf x$ é válida ($V>0$) e $\dot V=-\mathbf x^TQ\mathbf x<0$ → sistema **assintoticamente estável**.

---

Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} 3 & -2 \\ 2 & -2 \end{bmatrix} x
```
---
Usando o fluxo: equação de Lyapunov (com $Q=I$) → checar $P$ pelos menores principais líderes → confirmar/classificar o tipo via $T$ e $D$ de $A$.

## Passo 1 — escolher Q

```math
Q=I=\begin{bmatrix}1&0\\0&1\end{bmatrix}
```

## Passo 2 — montar P

```math
P=\begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix} (simétrica, incógnitas)
```

##Passo 3 — resolver $A^TP+PA=-I$

```math
A^T=\begin{bmatrix}3&2\\-2&-2\end{bmatrix}
```
```math
A^TP=\begin{bmatrix}3&2\\-2&-2\end{bmatrix}\begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix}=\begin{bmatrix}3p_{11}+2p_{12} & 3p_{12}+2p_{22}\\-2p_{11}-2p_{12} & -2p_{12}-2p_{22}\end{bmatrix}
```
```math
PA = (A^TP)^T=\begin{bmatrix}3p_{11}+2p_{12} & -2p_{11}-2p_{12}\\3p_{12}+2p_{22} & -2p_{12}-2p_{22}\end{bmatrix}
```

Somando $A^TP+PA$:
```math
A^TP+PA=\begin{bmatrix}6p_{11}+4p_{12} & p_{12}+2p_{22}-2p_{11}\\ p_{12}+2p_{22}-2p_{11} & -4p_{12}-4p_{22}\end{bmatrix}
```
Igualando a I, temos o sistema:

$$6p_{11}+4p_{12}=-1 \quad (i)$$
$$-2p_{11}+p_{12}+2p_{22}=0 \quad (ii)$$
$$-4p_{12}-4p_{22}=-1 \quad (iii)$$

## Passo 4 — resolver o sistema

Da (iii): $p_{22}=\dfrac{1-4p_{12}}{4}=\dfrac14-p_{12}$

Substituindo em (ii): $-2p_{11}+p_{12}+2\left(\dfrac14-p_{12}\right)=0 \Rightarrow -2p_{11}-p_{12}+\dfrac12=0 \Rightarrow p_{12}=\dfrac12-2p_{11}$

Substituindo em (i): $6p_{11}+4\left(\dfrac12-2p_{11}\right)=-1 \Rightarrow 6p_{11}+2-8p_{11}=-1 \Rightarrow -2p_{11}=-3 \Rightarrow p_{11}=\dfrac32$

Então: $p_{12}=\dfrac12-2\left(\dfrac32\right)=\dfrac12-3=-\dfrac52$

E: $p_{22}=\dfrac14-\left(-\dfrac52\right)=\dfrac14+\dfrac52=\dfrac{11}{4}$

## Passo 5 — verificar se $P$ é positiva definida

```math
P=\begin{bmatrix}\dfrac32 & -\dfrac52\\[4pt] -\dfrac52 & \dfrac{11}{4}\end{bmatrix}
```

Critério de Sylvester: $P$ é positiva definida se todos os **menores principais** ($p_{11}$ e det(P)) for positivos.

- $p_{11}=\dfrac32>0$ ✓
- $\det(P) = \left(\dfrac32\right)\left(\dfrac{11}{4}\right)-\left(-\dfrac52\right)^2 = \dfrac{33}{8}-\dfrac{25}{4}=\dfrac{33}{8}-\dfrac{50}{8}=-\dfrac{17}{8}<0$ ✗

**$\det(P)<0$ → $P$ não é positiva definida! Isso indica que o sistema não é assintoticamente estável!**

Como não conseguimos $P$ positiva definida com essa escolha de $Q=I$, isso é um **forte indício de instabilidade** (de fato, para sistemas lineares, se $A$ é Hurwitz — todos autovalores com parte real negativa —, a equação de Lyapunov com $Q>0$ **sempre** tem solução única $P>0$; então a falha aqui sugere que $A$ não é Hurwitz).

**Verificando instabilidade por meio de autovalores**

```math
\frac{dx}{dt} = \begin{bmatrix} 3 & -2 \\ 2 & -2 \end{bmatrix} x
```
 Traço (T) = 3 - 2 = 1, Determinante (D) = (3)(-2) - (-2)(2) = -6 + 4 = -2

$\lambda ^2 - T\lambda + D = 0 \Rightarrow \lambda ^2 - 1\lambda -2 = 0 \Rightarrow \lambda_1 = 1, \lambda_2 = -2 $

Portanto, o sistema é instável (ponto de sela).
