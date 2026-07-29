<h1>Estabilidade 09</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

### Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente  
2. **Calcular a matriz Jacobiana** do sistema:  

```math
J(x,y) = \begin{pmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\ \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y} \end{pmatrix}
```

3. **Avaliar $J$ em cada ponto crítico** e calcular seus **autovalores**
4. **Classificar** o ponto crítico conforme os autovalores (sela, nó, foco, centro — estável/instável)

## (i): $\dot x=-(x-y)(1-x-y),\quad \dot y=x(2+y)$

### Passo 1 — Pontos críticos

Da segunda equação: $x(2+y)=0 \Rightarrow x=0$ ou $y=-2$

Da primeira equação: $-(x-y)(1-x-y)=0 \Rightarrow x=y$ ou $x+y=1$

Combinando (4 casos, todos compatíveis):

- $x=0$ e $x=y$ → $y=0$ → **$(0,0)$**
- $x=0$ e $x+y=1$ → $y=1$ → **$(0,1)$**
- $y=-2$ e $x=y$ → $x=-2$ → **$(-2,-2)$**
- $y=-2$ e $x+y=1$ → $x=3$ → **$(3,-2)$**

**Pontos críticos: $(0,0)$, $(0,1)$, $(-2,-2)$, $(3,-2)$**

### Passo 2 — Jacobiano genérico (corrigido)

Expandindo $f(x,y)=-(x-y)(1-x-y)=-x+x^2+y-y^2$ e $g(x,y)=x(2+y)=2x+xy$:

```math
J(x,y) = \begin{pmatrix} -1+2x & 1-2y\\2+y & x \end{pmatrix}
```

**Traço e determinante genéricos:**
$$T=3x-1$$
$$D=(-1+2x)(x)-(1-2y)(2+y)=2x^2-x-(2-3y-2y^2)=2x^2+2y^2-x+3y-2$$

### Passo 3 — Avaliando em $(0,0)$

$$T=3(0)-1=-1$$
$$D=0+0-0+0-2=-2$$

$D<0$ → **sela** 

### Passo 4 — Avaliando em $(0,1)$

$$T=3(0)-1=-1$$
$$D=0+2(1)-0+3(1)-2=2+3-2=3$$

$D>0$; $T^2-4D=1-12=-11<0$ (complexos); $T<0$ → **foco estável** 

### Passo 5 — Avaliando em $(-2,-2)$

$$T=3(-2)-1=-7$$
$$D=2(4)+2(4)-(-2)+3(-2)-2=8+8+2-6-2=10$$

$D>0$; $T^2-4D=49-40=9>0$ (reais); $T<0$ → **nó estável** 

### Passo 6 — Avaliando em $(3,-2)$

$$T=3(3)-1=8$$
$$D=2(9)+2(4)-3+3(-2)-2=18+8-3-6-2=15$$

$D>0$; $T^2-4D=64-60=4>0$ (reais); $T>0$ → **nó instável** 

### Conclusão

$$(0,0):\textbf{sela} \quad (0,1):\textbf{foco estável} \quad (-2,-2):\textbf{nó estável} \quad (3,-2):\textbf{nó instável}$$


---

Esse item mostra bem por que vale a pena conferir a **regra do produto** com cuidado quando a equação original vem em forma de produto (como $-(x-y)(1-x-y)$) — um deslize ali afeta todo o resultado do Jacobiano. Quer revisar mais algum item?
