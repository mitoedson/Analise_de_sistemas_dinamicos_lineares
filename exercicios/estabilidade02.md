<h1>Estabilidade 02</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

$$\boxed{\text{Questão 2} = \text{Não linear} + \text{Linearização (Jacobiano)} + \text{Conclusão sempre LOCAL}}$$

## Propósito

A questão tem como objetivo **investigar a estabilidade local** de sistemas dinâmicos **não lineares** de segunda ordem (com duas variáveis, $x$ e $y$), analisando o comportamento das trajetórias **na vizinhança** de cada ponto de equilíbrio do sistema.

Como sistemas não lineares geralmente **não têm solução analítica exata** (não dá pra "resolver" a EDO diretamente), a estratégia é **indireta**: aproximar o comportamento do sistema perto de pontos específicos (os pontos críticos), usando a teoria — já conhecida e simples — de sistemas **lineares**.

## Método (passo a passo)

**1. Encontrar os pontos críticos**

Resolver $\dot x=0$ e $\dot y=0$ simultaneamente. Técnicas comuns:
- Isolar uma variável e substituir na outra equação
- Fatorar em casos (quando as equações já vêm como produtos, como $x(1-x-y)=0$)
- Combinar as soluções possíveis, testando compatibilidade entre os casos

**2. Montar a matriz Jacobiana genérica**

```math
J(x,y)=\begin{pmatrix}\dfrac{\partial f}{\partial x} & \dfrac{\partial f}{\partial y}\\[4pt]\dfrac{\partial g}{\partial x} & \dfrac{\partial g}{\partial y}\end{pmatrix}
```
Essa matriz representa a **aproximação linear** (expansão de Taylor de 1ª ordem) do sistema em torno de um ponto qualquer.

**3. Avaliar o Jacobiano em cada ponto crítico**

Substituindo as coordenadas de cada ponto na matriz genérica, obtém-se uma matriz numérica constante para cada ponto — essa matriz descreve o comportamento **linearizado**, válido apenas **naquela vizinhança específica**.

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

## Limitação fundamental do método

A conclusão obtida é **sempre local** — válida apenas numa pequena vizinhança daquele ponto crítico específico. Isso ocorre porque a linearização **descarta** os termos de ordem superior (quadráticos, cúbicos, trigonométricos, etc.) do sistema original — termos que voltam a ter influência significativa longe do ponto de equilíbrio.

Além disso, a técnica só é **plenamente confiável** quando o ponto é **hiperbólico** (nenhum autovalor com parte real exatamente zero); nos casos de fronteira (como "centro"), a linearização pode não capturar corretamente o comportamento real do sistema não linear.

---


## (b): $\dot x=-x+y+2xy,\quad \dot y=-4x-y+x^2-y^2$

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

```math
J(x,y)=\begin{pmatrix}-1+2y & 1+2x\\-4+2x & -1-2y\end{pmatrix}
```

### Passo 3 — Classificando $(0,0)$

```math
J(0,0)=\begin{pmatrix}-1&1\\-4&-1\end{pmatrix}
```

$$T=-1-1=-2,\qquad D=(-1)(-1)-(1)(-4)=1+4=5$$

$D>0$; $T^2-4D=4-20=-16<0$ (complexos); $T<0$ → **foco estável** 

Autovalores: $$\lambda^2+2\lambda+5=0 \;\Rightarrow\; \lambda=\frac{-2\pm\sqrt{4-20}}{2}=\frac{-2\pm\sqrt{-16}}{2}=-1\pm2i$$


### Passo 4 — Classificando os três pontos numéricos

**Em $(4{,}155,\ 0{,}446)$:**
```math
J \approx \begin{pmatrix}-0{,}108&9{,}31 \\ 4{,}31&-1{,}892\end{pmatrix}, D\approx(-0{,}108)(-1{,}892)-(9{,}31)(4{,}31)\approx0{,}20-40{,}13=-39{,}93<0 \;\Rightarrow\; \textbf{sela}
```

**Em $(-0{,}758,\ 1{,}469)$:**
```math
J \approx \begin{pmatrix}1{,}938&-0{,}516\\-5{,}516&-3{,}938\end{pmatrix}, D \approx(1{,}938)(-3{,}938)-(-0{,}516)(-5{,}516)\approx-7{,}63-2{,}85=-10{,}48<0 \;\Rightarrow\; \textbf{sela}
```

**Em $(-0{,}396,\ -1{,}904)$:**
```math
J \approx \begin{pmatrix}-4{,}808&0{,}208\\-4{,}792&2{,}808\end{pmatrix}, D\approx(-4{,}808)(2{,}808)-(0{,}208)(-4{,}792)\approx-13{,}50+1{,}00=-12{,}50<0 \;\Rightarrow\; \textbf{sela}
```

$D<0$ em todos → $\lambda^2-T\lambda+D=0$ sempre tem $\sqrt{T^2-4D}>|T|$, garantindo raízes reais de sinais opostos (sela), sem precisar resolver numericamente.

### Conclusão

$$(0,0):\ \textbf{foco estável} \qquad\qquad \text{os outros três pontos: } \textbf{selas}$$

<p>
<a href="/teoria/estabilidade.md">Ver teoria</a>

