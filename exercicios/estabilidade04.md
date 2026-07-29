<h1>Estabilidade 04</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

### Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente  
2. **Calcular a matriz Jacobiana** do sistema:  
```math
J(x,y) = \begin{pmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\ \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y} \end{pmatrix}
```

3. **Avaliar $J$ em cada ponto crítico** e calcular seus **autovalores**
4. **Classificar** o ponto crítico conforme os autovalores (sela, nó, foco, centro — estável/instável)


## Item (d): $\dot x=x+y^2,\quad \dot y=x+y$

### Passo 1 — Pontos críticos

Da segunda equação: $x+y=0 \Rightarrow x=-y$

Substituindo na primeira: $-y+y^2=0 \Rightarrow y(y-1)=0$

- $y=0 \Rightarrow x=0$ → ponto **$(0,0)$**
- $y=1 \Rightarrow x=-1$ → ponto **$(-1,1)$**

**Pontos críticos: $(0,0)$ e $(-1,1)$** 

### Passo 2 — Jacobiano genérico

```math
J(x,y) = \begin{pmatrix} \dfrac{\partial}{\partial x}(x+y^2) & \dfrac{\partial}{\partial y}(x+y^2) \\ \dfrac{\partial}{\partial x}(x+y) & \dfrac{\partial}{\partial y}(x+y) \end{pmatrix} = \begin{bmatrix}1&2y\\1&1\end{bmatrix}
```

### Passo 3 — Avaliando em $(0,0)$

$$J(0,0)=\begin{bmatrix}1&0\\1&1\end{bmatrix}$$

$$T=1+1=2, \qquad D=(1)(1)-(0)(1)=1$$

$D>0$; $T^2-4D=4-4=0$ → autovalores reais **repetidos**: $\lambda=\dfrac{T}{2}=1$ (duplo); $T>0$ → **nó impróprio instável**

### Passo 4 — Avaliando em $(-1,1)$

$$J(-1,1)=\begin{bmatrix}1&2\\1&1\end{bmatrix}$$

$$T=1+1=2, \qquad D=(1)(1)-(2)(1)=1-2=-1$$

$D<0$ → **sela** (independente do valor de $T$)

### Conclusão

$$(0,0):\ \textbf{nó impróprio instável} \qquad\qquad (-1,1):\ \textbf{sela}$$

"$(0,0)$ nó impróprio instável; $(-1,1)$ sela" ✓

---

**Sobre o termo "nó impróprio":** é o mesmo caso especial que já vimos antes (autovalores reais repetidos, $T^2-4D=0$) — só que aqui, diferente do exemplo da questão 4 item (k) (onde a matriz já era diagonal e o nó era "próprio"/em estrela), aqui a matriz **não é diagonal** e tem autovalor duplo com **apenas um autovetor independente** (matriz não diagonalizável) — esse é o caso clássico do "nó impróprio" (também chamado de nó degenerado), onde as trajetórias se aproximam da origem tangenciando uma única direção, em vez de saírem "em estrela" de todas as direções.
