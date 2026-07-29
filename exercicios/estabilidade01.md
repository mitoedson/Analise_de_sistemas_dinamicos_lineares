<h1>Estabilidade 01</h1>

<h3>Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:</h3>

**Questão**: pontos críticos e estabilidade local via **linearização** (matriz Jacobiana).

## Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente
2. **Calcular a matriz Jacobiana** do sistema:
   
$$J(x,y) = \begin{bmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\[4pt] \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y}\end{bmatrix}$$

3. **Avaliar $J$ em cada ponto crítico** e calcular seus **autovalores**
4. **Classificar** o ponto crítico conforme os autovalores (sela, nó, foco, centro — estável/instável)

## Item (a): $\dot x = x-y^2,\quad \dot y = x-2y+x^2$

**Passo 1 — pontos críticos**

Da primeira equação: $x=y^2$

Substituindo na segunda: $y^2-2y+(y^2)^2=0 \Rightarrow y^4+y^2-2y=0$

Fatorando $y$: $y(y^3+y-2)=0$

- $y=0 \Rightarrow x=0$ → ponto $(0,0)$
- $y^3+y-2=0$: testando $y=1$: $1+1-2=0$ ✓. Fatorando: $(y-1)(y^2+y+2)=0$. O fator $y^2+y+2$ tem discriminante $1-8=-7<0$ (sem raízes reais).
  → $y=1 \Rightarrow x=1$ → ponto $(1,1)$

**Pontos críticos: $(0,0)$ e $(1,1)$** ✓ (bate com o gabarito)

**Passo 2 — Jacobiano**

$$J(x,y)=\begin{bmatrix} 1 & -2y \\ 1+2x & -2 \end{bmatrix}$$

**Passo 3 — avaliar em $(0,0)$**

$$J(0,0)=\begin{bmatrix} 1 & 0 \\ 1 & -2 \end{bmatrix}$$

$\text{traço}=-1$, $\det = (1)(-2)-(0)(1)=-2$

Quando $\det J<0$, os autovalores são reais com **sinais opostos** → **sela** (sempre instável)

**$(0,0)$ é sela** ✓

**Passo 4 — avaliar em $(1,1)$**

$$J(1,1)=\begin{bmatrix} 1 & -2 \\ 3 & -2 \end{bmatrix}$$

$\text{traço}=-1$, $\det=(1)(-2)-(-2)(3)=-2+6=4$

Autovalores:
$$\lambda=\frac{\text{traço}\pm\sqrt{\text{traço}^2-4\det}}{2}=\frac{-1\pm\sqrt{1-16}}{2}=\frac{-1\pm\sqrt{-15}}{2}$$

Autovalores **complexos conjugados** com parte real $-\dfrac{1}{2}<0$ → **foco estável**

**$(1,1)$ é foco estável** ✓

---

Esse padrão (achar pontos críticos → Jacobiano → autovalores em cada ponto → classificar) se repete em todos os itens de (a) a (k). Quer tentar o item (b) você mesmo e eu confiro, ou prefere que eu continue mostrando mais um ou dois exemplos primeiro?
















<p>
<a href="/teoria/estabilidade.md">Ver teoria</a>

