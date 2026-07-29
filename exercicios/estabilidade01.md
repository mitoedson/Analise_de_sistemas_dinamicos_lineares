<h1>Estabilidade 01</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

### Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente
2. **Calcular a matriz Jacobiana** do sistema:
   
```math
J(x,y) = \begin{pmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\ \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y} \end{pmatrix}
```

3. **Avaliar $J$ em cada ponto crítico** e calcular seus **autovalores**
4. **Classificar** o ponto crítico conforme os autovalores (sela, nó, foco, centro — estável/instável)

## (a) $\dot x = x-y^2,\quad \dot y = x-2y+x^2$

### Passo 1 — pontos críticos

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

**Através do polinômio característico:**

$\lambda^2+\lambda-2=0 \;\Rightarrow\; \lambda=\frac{-1\pm\sqrt{1+8}}{2}=\frac{-1\pm3}{2} \;\Rightarrow\; \lambda_1=1,\ \lambda_2=-2$

**$(0,0)$ é ponto de sela** 


### Em  $(1,1)$:

```math
J(1,1)=\begin{pmatrix} 1 & -2 \\ 3 & -2 \end{pmatrix}
```

$\text{traço}=1+(-2)=-1$, $\det=(1)(-2)-(-2)(3)=-2+6=4$

Autovalores:
$$\lambda=\frac{\text{traço}\pm\sqrt{\text{traço}^2-4\det}}{2}=\frac{-1\pm\sqrt{1-16}}{2}=\frac{-1\pm\sqrt{-15}}{2}$$

Autovalores **complexos conjugados** com parte real $-\dfrac{1}{2}<0$ → **foco estável**

**Através do polinômio característico:**

$\lambda^2+\lambda+4=0 \;\Rightarrow\; \lambda=\frac{-1\pm\sqrt{1-16}}{2}=\frac{-1\pm\sqrt{-15}}{2}$

**$(1,1)$ é foco estável** 


<p>
<a href="/teoria/estabilidade.md">Ver teoria</a>

