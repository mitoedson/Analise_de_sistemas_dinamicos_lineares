<h1>Estabilidade Local (Método Indireto de Lyapunov) - 09</h1>

Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

```math
\dot x=-(x-y)(1-x-y)
```
```math
\dot y=x(2+y)
```

---

### Passo 1 — Pontos críticos

Da segunda equação: $x(2+y)=0 \Rightarrow x=0$ ou $y=-2$

Da primeira equação: $-(x-y)(1-x-y)=0 \Rightarrow x=y$ ou $x+y=1$

Combinando (4 casos, todos compatíveis):

- $x=0$ e $x=y$ → $y=0$ → **$(0,0)$**
- $x=0$ e $x+y=1$ → $y=1$ → **$(0,1)$**
- $y=-2$ e $x=y$ → $x=-2$ → **$(-2,-2)$**
- $y=-2$ e $x+y=1$ → $x=3$ → **$(3,-2)$**

**Pontos críticos: $(0,0)$, $(0,1)$, $(-2,-2)$, $(3,-2)$**

### Passo 2 — Jacobiano genérico

Expandindo $f(x,y)=-(x-y)(1-x-y)=-x+x^2+y-y^2$ e $g(x,y)=x(2+y)=2x+xy$:

```math
J(x,y) = \begin{pmatrix} -1+2x & 1-2y\\2+y & x \end{pmatrix}
```

### Passo 3 — Avaliando nos pontos críticos

### Em $(0,0):$

```math
J(0,0) = \begin{pmatrix} -1 & 1 \\ 2 & 0 \end{pmatrix}
```

$T=-1+0=-1$, $D=(-1)(0)-(1)(2)=-2$

Autovalores: $$\lambda_1=1,\ \lambda_2=-2$$

$D<0$ → **sela** 

### Em $(0,1):$

```math
J(0,1) = \begin{pmatrix} -1 & -1 \\ 3 & 0 \end{pmatrix}
```

$T=-1+0=-1$, $D=(-1)(0)-(-1)(3)=3$

Autovalores: $$\lambda^2+\lambda+3=0 \;\Rightarrow\; \lambda=\frac{-1\pm\sqrt{1-12}}{2}=\frac{-1\pm\sqrt{-11}}{2}$$

$D>0$; $T^2-4D=1-12=-11<0$ (complexos); $T<0$ → **foco estável** 

### Em $(-2,-2):$

```math
J(x,y) = \begin{pmatrix} -5 & -3 \\ 0 & -2 \end{pmatrix}
```

$T=-5+(-2)=-7$, $D=(-5)(-2)-(-3)(0) = 10$

Autovalores: $$\lambda^2+7\lambda+10=0 \;\Rightarrow\; \lambda=\frac{-7\pm\sqrt{49-40}}{2}=\frac{-7\pm3}{2} \;\Rightarrow\; \lambda_1=-2,\ \lambda_2=-5$$

$D>0$; $T^2-4D=49-40=9>0$ (reais); $T<0$ → **nó estável** 

### Em $(3,-2):$

```math
J(x,y) = \begin{pmatrix} 5 & 5 \\ 0 & 3 \end{pmatrix}
```

$T= 5 + 3 = 8$, $D= (5)(3)-(5)(0) = 15$

Autovalores: $$\lambda^2-8\lambda+15=0 \;\Rightarrow\; \lambda=\frac{8\pm\sqrt{64-60}}{2}=\frac{8\pm2}{2} \;\Rightarrow\; \lambda_1=5,\ \lambda_2=3$$

$D>0$; $T^2-4D=64-60=4>0$ (reais); $T>0$ → **nó instável** 

### Conclusão

$$(0,0):\textbf{sela} \quad (0,1):\textbf{foco estável} \quad (-2,-2):\textbf{nó estável} \quad (3,-2):\textbf{nó instável}$$


