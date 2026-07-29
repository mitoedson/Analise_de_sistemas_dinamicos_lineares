<h1>Estabilidade 02</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

### Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente
2. **Calcular a matriz Jacobiana** do sistema:
   
```math
J(x,y) = \begin{bmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\ \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y} \end{bmatrix}
```

3. **Avaliar $J$ em cada ponto crítico** e calcular seus **autovalores**
4. **Classificar** o ponto crítico conforme os autovalores (sela, nó, foco, centro — estável/instável)

## Item (b): $\dot x=-x+y+2xy,\quad \dot y=-4x-y+x^2-y^2$

### Passo 1 — Pontos críticos

Da primeira equação, isolando $y$:
$$-x+y+2xy=0 \;\Rightarrow\; y(1+2x)=x \;\Rightarrow\; y=\frac{x}{1+2x}$$

Substituindo na segunda equação e multiplicando tudo por $(1+2x)^2$ para eliminar frações, chegamos (depois de expandir com cuidado) em:

$$4x^4-12x^3-18x^2-5x=0 \;\Rightarrow\; x\left(4x^3-12x^2-18x-5\right)=0$$

**Caso $x=0$:** $y=0$ → ponto **$(0,0)$** ✓

**Caso $4x^3-12x^2-18x-5=0$:** testando o teorema das raízes racionais (candidatos $\pm1,\pm5,\pm\frac12,\pm\frac52,\pm\frac14,\pm\frac54$) — **nenhum** zera o polinômio. As raízes são irracionais, resolvidas numericamente:

$$x\approx4{,}155,\quad x\approx-0{,}758,\quad x\approx-0{,}396$$

Substituindo cada uma em $y=\dfrac{x}{1+2x}$:

$$(4{,}155,\ 0{,}446),\qquad(-0{,}758,\ 1{,}469),\qquad(-0{,}396,\ -1{,}904)$$

**Total: 4 pontos críticos** — $(0,0)$ e três pontos numéricos.

### Passo 2 — Jacobiano genérico

$$J(x,y)=\begin{bmatrix}-1+2y & 1+2x\\-4+2x & -1-2y\end{bmatrix}$$

### Passo 3 — Classificando $(0,0)$

$$J(0,0)=\begin{bmatrix}-1&1\\-4&-1\end{bmatrix}$$

$$T=-1-1=-2,\qquad D=(-1)(-1)-(1)(-4)=1+4=5$$

$D>0$; $T^2-4D=4-20=-16<0$ (complexos); $T<0$ → **foco estável** ✓

### Passo 4 — Classificando os três pontos numéricos

**Em $(4{,}155,\ 0{,}446)$:**
$$J\approx\begin{bmatrix}-0{,}108&9{,}31\\4{,}31&-1{,}892\end{bmatrix}$$
$$D\approx(-0{,}108)(-1{,}892)-(9{,}31)(4{,}31)\approx0{,}20-40{,}13=-39{,}93<0 \;\Rightarrow\; \textbf{sela}$$

**Em $(-0{,}758,\ 1{,}469)$:**
$$J\approx\begin{bmatrix}1{,}938&-0{,}516\\-5{,}516&-3{,}938\end{bmatrix}$$
$$D\approx(1{,}938)(-3{,}938)-(-0{,}516)(-5{,}516)\approx-7{,}63-2{,}85=-10{,}48<0 \;\Rightarrow\; \textbf{sela}$$

**Em $(-0{,}396,\ -1{,}904)$:**
$$J\approx\begin{bmatrix}-4{,}808&0{,}208\\-4{,}792&2{,}808\end{bmatrix}$$
$$D\approx(-4{,}808)(2{,}808)-(0{,}208)(-4{,}792)\approx-13{,}50+1{,}00=-12{,}50<0 \;\Rightarrow\; \textbf{sela}$$

### Conclusão

$$(0,0):\ \textbf{foco estável} \qquad\qquad \text{os outros três pontos: } \textbf{selas}$$

---

**Ponto-chave desse item:** como os três pontos "extras" vêm de uma cúbica sem raízes racionais, a classificação deles depende de avaliar o Jacobiano **numericamente**. Mas repare que, mesmo sem os valores exatos, **todos deram $D<0$** — e isso não é coincidência: para pontos vindos dessa cúbica específica, o determinante do Jacobiano sempre resulta negativo, garantindo sela nos três, independentemente da precisão numérica usada.


<p>
<a href="/teoria/estabilidade.md">Ver teoria</a>

