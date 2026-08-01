<h1>Estabilidade Local - 05</h1>

Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:
$\dot x=(2+x)(y-x),\quad \dot y=(4-x)(y+x)$

### Passo 1 — Pontos críticos

---

Cada equação já vem fatorada:
$$(2+x)(y-x)=0 \Rightarrow x=-2 \text{ ou } y=x$$
$$(4-x)(y+x)=0 \Rightarrow x=4 \text{ ou } y=-x$$

Combinando (4 casos):

- $x=-2$ e $x=4$ → impossível, descartado
- $x=-2$ e $y=-x$ → $y=2$ → **$(-2,2)$**
- $y=x$ e $x=4$ → $y=4$ → **$(4,4)$**
- $y=x$ e $y=-x$ → $x=0,y=0$ → **$(0,0)$**

**Pontos críticos: $(-2,2)$, $(0,0)$, $(4,4)$**

### Passo 2 — Jacobiano genérico

Expandindo primeiro: $f=2y-2x+xy-x^2$, $g=4y+4x-xy-x^2$

```math
J(x,y) = \begin{pmatrix} -2+y-2x & 2+x \\ 4-y-2x & 4-x \end{pmatrix}
```

### Passo 3 — Avaliando em $(-2,2)$

```math
J(-2,2) = \begin{pmatrix} -2+2+4 & 2-2\\4-2+4 & 4+2 \end{pmatrix}
```

$T=4+6=10, D=(4)(6)-(0)(6)=24$

Autovalores: $$\lambda^2-10\lambda+24=0 \;\Rightarrow\; \lambda=\frac{10\pm\sqrt{100-96}}{2}=\frac{10\pm2}{2} \;\Rightarrow\; \lambda_1=6,\ \lambda_2=4$$

$D>0$; $T^2-4D=100-96=4>0$ (reais); $T>0$ → **nó instável**

### Passo 4 — Avaliando em $(0,0)$

```math
J(0,0) = \begin{pmatrix} -2&2\\4&4 \end{pmatrix}
```

$T=-2+4=2, D=(-2)(4)-(2)(4)=-8-8=-16$

Autovalores: $$\lambda^2-2\lambda-16=0 \;\Rightarrow\; \lambda=\frac{2\pm\sqrt{4+64}}{2}=1\pm\sqrt{17}$$

$D<0$ → **sela** (independente de $T$)

### Passo 5 — Avaliando em $(4,4)$

```math
J(4,4) = \begin{pmatrix} -2+4-8 & 2+4 \\ 4-4-8 & 4-4 \end{pmatrix}
```

$T=-6+0=-6, D=(-6)(0)-(6)(-8)=0+48=48$

Autovalores: $$\lambda^2+6\lambda+48=0 \;\Rightarrow\; \lambda=\frac{-6\pm\sqrt{36-192}}{2}=-3\pm\frac{\sqrt{-156}}{2}$$

$D>0$; $T^2-4D=36-192=-156<0$ (complexos); $T<0$ → **foco estável**

### Conclusão

$$(-2,2):\ \textbf{nó instável} \qquad (0,0):\ \textbf{sela} \qquad (4,4):\ \textbf{foco estável}$$

