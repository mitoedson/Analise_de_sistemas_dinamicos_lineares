<h1>Estabilidade - Funções de Lyapunov - 10</h1>

Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} 1 & 2 \\ -5 & -1 \end{bmatrix} x
```
---
Usando o fluxo: equação de Lyapunov (com $Q=I$) → checar $P$ pelos menores principais líderes → confirmar/classificar o tipo via $T$ e $D$ de $A$.

## Passo 1 — montar a equação de Lyapunov com $Q=I$

```math
A^T=\begin{bmatrix}1&-5\\2&-1\end{bmatrix}
```

Calculando $A^TP+PA$:

```math
A^TP+PA=\begin{bmatrix}2p_{11}-10p_{12} & 2p_{11}-2p_{12}-5p_{22}\\ 2p_{11}-2p_{12}-5p_{22} & 4p_{12}-2p_{22}\end{bmatrix}
```

Igualando a $-I$:

$$2p_{11}-10p_{12}=-1 \quad (i)$$
$$2p_{11}-2p_{12}-5p_{22}=0 \quad (ii)$$
$$4p_{12}-2p_{22}=-1 \quad (iii)$$

## Passo 2 — resolver o sistema

Da (i): $p_{11}=\dfrac{-1+10p_{12}}{2}=-0{,}5+5p_{12}$

Da (iii): $p_{22}=\dfrac{1+4p_{12}}{2}=0{,}5+2p_{12}$

Substituindo em (ii):
$$2(-0{,}5+5p_{12})-2p_{12}-5(0{,}5+2p_{12})=0$$
$$-1+10p_{12}-2p_{12}-2{,}5-10p_{12}=0$$
$$-2p_{12}-3{,}5=0 \;\Rightarrow\; p_{12}=-1{,}75$$

Logo:
$$p_{11}=-0{,}5+5(-1{,}75)=-0{,}5-8{,}75=-9{,}25$$
$$p_{22}=0{,}5+2(-1{,}75)=0{,}5-3{,}5=-3$$

## Passo 3 — checar se $P$ é positiva definida

$$p_{11}=-9{,}25<0$$

**Falha logo no primeiro menor** → $P$ não é positiva definida → instável.

## Passo 4 — classificar o tipo via traço e determinante de $A$

$$T=\text{traço}(A)=1+(-1)=0$$
$$D=\det(A)=(1)(-1)-(2)(-5)=-1+10=9$$

$T=0$ e $D=9>0$ → **centro**

## Conclusão

$$P \text{ falhou} \;\Rightarrow\; \text{instável (Lyapunov não confirma estabilidade)}; \qquad T=0,\ D>0 \;\Rightarrow\; \textbf{centro}$$

**Atenção a um detalhe importante nesse item:** aqui $P$ "falhou" (saiu indefinida), mas a conclusão **não é instável** — é **centro**, que é **estável** (só que não assintoticamente)! Isso é consistente com o que vimos: quando $T=0$, o sistema está na **fronteira** entre estável (centro) e instável (sela), e só o cálculo de $D$ decide qual dos dois é. A "falha" de $P$ só nos diz que "não é assintoticamente estável" — não decide sozinha entre sela e centro; para isso, sempre recorremos a $T$ e $D$ de $A$.
