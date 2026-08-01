<h1>Estabilidade Local - 12</h1>

Considere o sistema de segunda ordem descrito por:

```math
\dot x = ax - bxy
```
```math
\dot y = cxy - dy
```

na qual, a, b, c e d são constantes reais positivas. Determine os pontos de equilíbrio. Para cada um desses pontos de equilíbrio determine a estabilidade e o tipo de ponto
de equilíbrio (sela, foco, nó, centro).

---

**1. Encontrar os pontos críticos**

Resolver $\dot x=0$ e $\dot y=0$ simultaneamente. 

```math
\dot x = 0 \Rightarrow ax - bxy = 0 \Rightarrow ax = bxy \Rightarrow y = \frac{ax}{bx} \Rightarrow y = \frac{a}{b}\quad\text{ou x = 0}
```
```math
\dot y = 0 \Rightarrow cxy - dy = 0 \Rightarrow cxy = dy \Rightarrow cxy = dy  \Rightarrow x = \frac{dy}{cy}  \Rightarrow x = \frac{d}{c}\quad\text{ou y = 0}
```
Pontos críticos: (0,0) e ($\frac{d}{c},\frac{a}{b}$)

**2. Montar a matriz Jacobiana genérica**
```math
J(x,y)=\begin{pmatrix}\dfrac{\partial f}{\partial x} & \dfrac{\partial f}{\partial y}\\[4pt]\dfrac{\partial g}{\partial x} & \dfrac{\partial g}{\partial y}\end{pmatrix}
=\begin{pmatrix}\dfrac{\partial ax - bxy}{\partial x} & \dfrac{\partial ax - bxy}{\partial y}\\[4pt]\dfrac{\partial cxy - dy}{\partial x} & \dfrac{\partial cxy - dy}{\partial y}\end{pmatrix}
=\begin{pmatrix} a - by & -bx \\ cy & cx -d \end{pmatrix}
```

Essa matriz representa a **aproximação linear** (expansão de Taylor de 1ª ordem) do sistema em torno de um ponto qualquer.

**3. Avaliar o Jacobiano em cada ponto crítico**

**Para (0,0):** 
```math
J(0,0)=\begin{pmatrix} a - b(0) & -b(0) \\ c(0) & c(0) -d \end{pmatrix}=\begin{pmatrix} a & 0 \\ 0 & -d \end{pmatrix}
```

**Para ($\frac{d}{c},\frac{a}{b}$):**
```math
J(\frac{d}{c},\frac{a}{b})=\begin{pmatrix} a - b(\frac{a}{b})) & -b(\frac{d}{c}) \\ c(\frac{a}{b})) & c(\frac{d}{c}) -d \end{pmatrix}
=\begin{pmatrix} 0 & -\frac{bd}{c} \\ \frac{ca}{b} & 0 \end{pmatrix}
```




**4. Calcular traço ($T$) e determinante ($D$)**

$$T=\text{soma da diagonal}, \qquad D=\det(J)$$

**5. Classificar usando a tabela T-D**

| Condição | Classificação |
|---|---|
| $D<0$ | Sela (sempre instável) |
| $D>0$, $T^2-4D>0$, $T>0$ | Nó instável |
| $D>0$, $T^2-4D>0$, $T<0$ | Nó estável |
| $D>0$, $T^2-4D<0$, $T>0$ | Foco instável |
| $D>0$, $T^2-4D<0$, $T<0$ | Foco estável |
| $D>0$, $T=0$ | Centro (marginalmente estável) |
| $D>0$, $T^2-4D=0$ | Nó degenerado (próprio ou impróprio) |
