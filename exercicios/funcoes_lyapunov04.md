<h1>Estabilidade - Funções de Lyapunov - 04</h1>

(d) Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} 1 & -4 \\ 4 & -7 \end{bmatrix} x
```
---

## Passo 1 — montar a equação de Lyapunov com $Q=I$

```math
A^T=\begin{bmatrix}1&4\\-4&-7\end{bmatrix}
```

Calculando $A^TP+PA$ (mesmo procedimento):

```math
A^TP+PA=\begin{bmatrix}2p_{11}+8p_{12} & -4p_{11}-6p_{12}+4p_{22}\\ -4p_{11}-6p_{12}+4p_{22} & -8p_{12}-14p_{22}\end{bmatrix}
```

Igualando a $-I$:

```math
2p_{11}+8p_{12}=-1 \quad (i)
```
```math
-4p_{11}-6p_{12}+4p_{22}=0 \quad (ii)
```
```math
-8p_{12}-14p_{22}=-1 \quad (iii)
```

## Passo 2 — resolver o sistema

Da (i): $p_{11}=\dfrac{-1-8p_{12}}{2}$

Substituindo em (ii):
```math
-4\left(\frac{-1-8p_{12}}{2}\right)-6p_{12}+4p_{22}=0
```
```math
(2+16p_{12})-6p_{12}+4p_{22}=0 \;\Rightarrow\; 10p_{12}+4p_{22}=-2 \;\Rightarrow\; p_{22}=\frac{-2-10p_{12}}{4}=-\frac{1+5p_{12}}{2}
```

Substituindo em (iii):
```math
-8p_{12}-14\left(-\frac{1+5p_{12}}{2}\right)=-1
```
```math
-8p_{12}+7(1+5p_{12})=-1
```
```math
-8p_{12}+7+35p_{12}=-1
```
```math
27p_{12}=-8 \;\Rightarrow\; p_{12}=-\frac{8}{27}
```

Voltando:
```math
p_{11}=\frac{-1-8\left(-\frac{8}{27}\right)}{2}=\frac{-1+\frac{64}{27}}{2}=\frac{\frac{37}{27}}{2}=\frac{37}{54}
```
```math
$$p_{22}=-\frac{1+5\left(-\frac{8}{27}\right)}{2}=-\frac{1-\frac{40}{27}}{2}=-\frac{-\frac{13}{27}}{2}=\frac{13}{54}
```

## Passo 3 — checar se $P$ é positiva definida

```math
P=\begin{bmatrix}\dfrac{37}{54} & -\dfrac{8}{27}\\[4pt] -\dfrac{8}{27} & \dfrac{13}{54}\end{bmatrix}
```

**Menor 1:** $p_{11}=\dfrac{37}{54}>0$

**Menor 2 (determinante):**
```math
\det(P)=\left(\frac{37}{54}\right)\left(\frac{13}{54}\right)-\left(-\frac{8}{27}\right)^2=\frac{481}{2916}-\frac{64}{729}
```

Convertendo $\dfrac{64}{729}=\dfrac{256}{2916}$:
```math
\det(P)=\frac{481-256}{2916}=\frac{225}{2916}>0 \checkmark$$
```

**Os dois menores são positivos → $P$ é positiva definida!**

Como $P>0$, já concluímos diretamente (sem precisar checar traço/determinante de $A$): **assintoticamente estável**

## Traço e determinante

$$T=\text{traço}(A)=1+(-7)=-6$$

$$D=\det(A)=(1)(-7)-(-4)(4)=-7+16=9$$

## Aplicando a tabela de classificação

$D=9>0$ — então autovalores têm o **mesmo sinal** (produto positivo)

Verificando o discriminante $T^2-4D$:
$$T^2-4D = (-6)^2-4(9)=36-36=0$$

**Caso especial: $T^2-4D=0$** → autovalores reais e **iguais** (raiz dupla)

$$\lambda = \frac{T}{2}=\frac{-6}{2}=-3 \quad \text{(autovalor duplo)}$$

Como $T<0$ (e $D>0$), ambos autovalores são **negativos** → **nó estável** ✓ (nesse caso especial, com autovalores repetidos, é chamado de **nó estável degenerado** ou **nó impróprio**, dependendo de a matriz ser ou não diagonalizável)

## Conclusão

$$T=-6<0, \quad D=9>0, \quad T^2-4D=0 \;\Rightarrow\; \textbf{nó estável}$$

Confirma exatamente o que o gabarito diz: "assintoticamente estável (nó estável)" ✓.

---

Esse foi um caso particular interessante: quando $T^2-4D=0$ exatamente, caímos no limite entre nó (autovalores reais distintos) e foco (autovalores complexos) — autovalores reais e **repetidos**. Vale adicionar essa linha na sua tabela de referência:

| Condição adicional | Classificação |
|---|---|
| $D>0$, $T^2-4D=0$, $T<0$ | Nó estável (degenerado/impróprio) |
| $D>0$, $T^2-4D=0$, $T>0$ | Nó instável (degenerado/impróprio) |
