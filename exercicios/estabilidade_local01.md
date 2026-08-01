<h1>Estabilidade Local - 01</h1>

Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

$\dot x = x-y^2,\quad \dot y = x-2y+x^2$


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

$$\boxed{\text{Questão} = \text{Não linear} + \text{Linearização (Jacobiano)} + \text{Conclusão sempre LOCAL}}$$
---

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



