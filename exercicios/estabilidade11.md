<h1>Estabilidade 10</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

### Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente  
2. **Calcular a matriz Jacobiana** do sistema:  

```math
J(x,y) = \begin{pmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\ \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y} \end{pmatrix}
```

## (k): $\dot x=2x+y+xy^3,\quad \dot y=x-2y-xy$

### Passo 1 — Pontos críticos (revisão rápida)

Da segunda equação: $x-2y-xy=0 \Rightarrow x(1-y)=2y \Rightarrow x=\dfrac{2y}{1-y}$

Da primeira equação: $2x+y+xy^3=0 \Rightarrow x(2+y^3)=-y \Rightarrow x=\dfrac{-y}{2+y^3}$

Igualando: $y=0$ dá **$(0,0)$**. Para $y\ne0$, obtemos a cúbica $2y^3-y+5=0$, resolvida numericamente: $y\approx-1{,}47970$, e substituindo, $x\approx-1{,}19345$ → **$(-1{,}19345,\ -1{,}47970)$**

### Passo 2 — Jacobiano genérico

```math
J(x,y)=\begin{pmatrix} 2+y^3 & 1+3xy^2 \\ 1-y & -2-x \end{pmatrix}
```

### Passo 3 — Avaliando em $(0,0)$

```math
J(0,0)=\begin{pmatrix} 2 & 1 \\ 1 & -2 \end{pmatrix}
```

$T=2+(-2)=0, D=(2)(-2)-(1)(1)=-4-1=-5$

$D<0$ → **sela** (direto, sem precisar resolver $\lambda$)

Conferindo com $\lambda$: $\lambda^2-5=0 \Rightarrow \lambda=\pm\sqrt5$ — reais, sinais opostos, confirma sela

### Passo 4 — Avaliando em $(-1{,}19345,\ -1{,}47970)$

Vamos calcular cada entrada do Jacobiano numericamente.

**$y^3$:** $(-1{,}47970)^3\approx-3{,}239$

**Entrada (1,1):** $2+y^3\approx2-3{,}239=-1{,}239$

**$3xy^2$:** $y^2\approx2{,}1895$; $3(-1{,}19345)(2{,}1895)\approx-7{,}838$

**Entrada (1,2):** $1+3xy^2\approx1-7{,}838=-6{,}838$

**Entrada (2,1):** $1-y\approx1-(-1{,}4797)=2{,}4797$

**Entrada (2,2):** $-2-x\approx-2-(-1{,}19345)=-0{,}80655$

```math
J \approx \begin{pmatrix} -1{,}239 & -6{,}838 \\ 2{,}4797 & -0{,}80655 \end{pmatrix}
```

**Traço e determinante:**
$$T\approx-1{,}239-0{,}80655\approx-2{,}046$$
$$D\approx(-1{,}239)(-0{,}80655)-(-6{,}838)(2{,}4797)\approx0{,}999+16{,}956\approx17{,}95$$

**Classificação:** $D>0$; $T^2-4D\approx4{,}19-71{,}8=-67{,}6<0$ → autovalores **complexos**; $T<0$ → **foco estável**

Conferindo com $\lambda$ (já mostrado antes): $\lambda\approx\dfrac{-2{,}046\pm\sqrt{-67{,}6}}{2}$ — complexos com parte real negativa, confirma foco estável

### Conclusão

$$(0,0):\ \textbf{sela} \qquad\qquad (-1{,}19345,\ -1{,}47970):\ \textbf{foco estável}$$
