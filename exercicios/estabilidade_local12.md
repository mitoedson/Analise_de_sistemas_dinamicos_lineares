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

### Passo 1 — pontos críticos


```math
\dot x = ax - bxy
```
```math
\dot y = cxy - dy
```


Da primeira equação: $x-y^2=0 \Rightarrow x=y^2$

Substituindo na segunda: $y^2-2y+(y^2)^2=0 \Rightarrow y^4+y^2-2y=0$

Fatorando $y$: $y(y^3+y-2)=0$

- $y=0 \Rightarrow x=0$ → ponto $(0,0)$
- $y^3+y-2=0$: testando $y=1$: $1+1-2=0$ . Fatorando: $(y-1)(y^2+y+2)=0$. O fator $y^2+y+2$ tem discriminante $1-8=-7<0$ (sem raízes reais).
  → $y=1 \Rightarrow x=1$ → ponto $(1,1)$

**Pontos críticos: $(0,0)$ e $(1,1)$** 

### Passo 2 — Matriz Jacobiana

```math
J(x,y)=\begin{pmatrix} 1 & -2y \\ 1+2x & -2 \end{pmatrix}
```

**Passo 3 — avaliar nos pontos críticos

### Em $(0,0)$:

```math
J(0,0)=\begin{pmatrix} 1 & 0 \\ 1 & -2 \end{pmatrix}
```

$\text{traço}=-1$, $\det = (1)(-2)-(0)(1)=-2$

Quando $\det J<0$, os autovalores são reais com **sinais opostos** → **sela** (sempre instável)

Autovalores: 
$$\lambda^2+\lambda-2=0 \;\Rightarrow\; \lambda=\frac{-1\pm\sqrt{1+8}}{2}=\frac{-1\pm3}{2} \;\Rightarrow\; \lambda_1=1,\ \lambda_2=-2$$

**$(0,0)$ é ponto de sela** 


### Em  $(1,1)$:

```math
J(1,1)=\begin{pmatrix} 1 & -2 \\ 3 & -2 \end{pmatrix}
```

$\text{traço}=1+(-2)=-1$, $\det=(1)(-2)-(-2)(3)=-2+6=4$

Autovalores:
$$\lambda=\frac{\text{traço}\pm\sqrt{\text{traço}^2-4\det}}{2}=\frac{-1\pm\sqrt{1-16}}{2}=\frac{-1\pm\sqrt{-15}}{2}$$

Autovalores **complexos conjugados** com parte real $-\dfrac{1}{2}<0$ → **foco estável**

**$(1,1)$ é foco estável** 



