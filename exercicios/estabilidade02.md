<h1>Estabilidade 02</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

### Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente
2. **Calcular a matriz Jacobiana** do sistema:
   
$$J(x,y) = \begin{bmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\[4pt] \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y}\end{bmatrix}$$

3. **Avaliar $J$ em cada ponto crítico** e calcular seus **autovalores**
4. **Classificar** o ponto crítico conforme os autovalores (sela, nó, foco, centro — estável/instável)

Sim, boa percepção! O item (b) é justamente um exemplo onde encontrar os pontos críticos **não é tão direto** — vamos ver por quê e como lidar com isso.

## (b) $\dot x = -x+y+2xy,\quad \dot y=-4x-y+x^2-y^2$

**Passo 1 — tentar isolar uma variável**

Da primeira equação, colocando $y$ em evidência:
$$-x+y+2xy=0 \;\Rightarrow\; y(1+2x)=x \;\Rightarrow\; y=\frac{x}{1+2x}$$

(supondo $x\ne-\tfrac12$; precisaríamos checar esse caso à parte, mas ele não gera solução válida aqui)

**Passo 2 — substituir na segunda equação**

$$-4x-\frac{x}{1+2x}+x^2-\left(\frac{x}{1+2x}\right)^2=0$$

Multiplicando tudo por $(1+2x)^2$ pra eliminar os denominadores (esse é o ponto que costuma dar trabalho):

$$-4x(1+2x)^2-x(1+2x)+x^2(1+2x)^2-x^2=0$$

Expandindo cuidadosamente cada termo, chega-se em:

$$4x^4-12x^3-18x^2-5x=0$$

**Passo 3 — fatorar o que der**

$$x\left(4x^3-12x^2-18x-5\right)=0$$

Aqui já sai um ponto fácil: $x=0 \Rightarrow y=0$ → **ponto $(0,0)$** ✓ (bate com o gabarito)

## A dificuldade real: o polinômio cúbico restante

$$4x^3-12x^2-18x-5=0$$

Tentando o **teste da raiz racional** (candidatos: $\pm1, \pm5, \pm\frac12, \pm\frac52, \pm\frac14, \pm\frac54$), **nenhum** deles zera o polinômio. Ou seja: **essa cúbica não tem raízes racionais** — as três raízes restantes são números "feios" (irracionais), que só conseguimos aproximar numericamente.

Resolvendo numericamente (por exemplo, por Newton-Raphson ou calculadora gráfica), as raízes aproximadas são:
$$x\approx 4{,}16,\quad x\approx -0{,}758,\quad x\approx -0{,}402$$

E para cada uma, $y=\dfrac{x}{1+2x}$ dá o ponto crítico correspondente.

**Isso explica por que o gabarito não dá as coordenadas exatas** desses três pontos — ele só afirma que são todos **selas**, sem especificar os valores numéricos. Isso é bem parecido com o que acontece no item (k), que também tem um ponto crítico com casas decimais.

## Como proceder na prática

Quando você cai numa cúbica (ou grau maior) **sem raízes racionais**:

1. **Confirme** que não há raiz racional (teste todos os candidatos do teorema das raízes racionais)
2. **Aceite que a solução será numérica** — use uma calculadora, software (Python, Wolfram Alpha, GeoGebra) ou métodos numéricos (Newton-Raphson) para aproximar as raízes
3. Para a **classificação** (sela, nó, foco...), muitas vezes você consegue argumentar pelo **sinal do determinante do Jacobiano** avaliado numericamente nesses pontos aproximados — não precisa necessariamente resolver tudo simbolicamente

Isso é uma dificuldade genuína e comum em listas de sistemas não lineares — nem todo sistema vai ter pontos críticos "bonitos".

Quer que eu mostre como calcular o Jacobiano nesse ponto $(0,0)$ pra confirmar que é foco estável, ou prefere seguir para outro item com pontos mais "tratáveis" (como o (g), por exemplo)?

<p>
<a href="/teoria/estabilidade.md">Ver teoria</a>

