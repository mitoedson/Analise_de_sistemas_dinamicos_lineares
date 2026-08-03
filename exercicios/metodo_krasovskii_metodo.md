<H1>Método de Krasovskii</H1>


## O problema que o Krasovskii resolve

Para sistemas lineares $\dot x = Ax$, como vimos, é fácil: resolvemos $A^TP+PA=-Q$ e pronto. Mas para sistemas não-lineares

$$\dot x = f(x), \qquad f(0)=0$$

não existe uma matriz $A$ constante — então essa equação não se aplica diretamente. O método de Krasovskii é uma das técnicas para **construir uma candidata de Lyapunov automaticamente**, usando a própria dinâmica do sistema (a jacobiana), em vez de "adivinhar" uma $V(x)$.

## A ideia central

Em vez de trabalhar diretamente com $f(x)$, o Krasovskii trabalha com a **matriz jacobiana**:

$$J(x) = \frac{\partial f}{\partial x}$$

E propõe a seguinte candidata de Lyapunov:

$$V(x) = f(x)^Tf(x) = \|f(x)\|^2$$

(em vez do tradicional $x^TPx$).

## Condição de estabilidade (Teorema de Krasovskii)

A origem $x=0$ é **globalmente assintoticamente estável** se, para todo $x$:

```math
(x) = J(x)^T + J(x) \quad \text{é definida negativa}
```

Ou seja, a mesma lógica de "$A^TP+PA$" de antes, mas aplicada à jacobiana $J(x)$, com $P=I$ fixo (não precisamos resolver para $P$, porque aqui a candidata já está definida como $f(x)^Tf(x)$).

**Intuição:** o método usa a taxa de variação do próprio campo vetorial $f$ como "medida de energia". Se a jacobiana é "sempre bem-comportada" (simétrica negativa definida), então $f(x)$ tende a diminuir ao longo das trajetórias, empurrando o sistema de volta à origem.

## Passo a passo prático

1. Calcule a jacobiana $J(x) = \dfrac{\partial f}{\partial x}$
2. Monte $F(x) = J(x)^T + J(x)$
3. Verifique se $F(x)$ é definida negativa para todo $x$ (por exemplo, via critério de Sylvester aplicado a $-F(x)$, ou autovalores)
4. Se sim → $V(x) = f(x)^Tf(x)$ é uma função de Lyapunov válida, e a origem é globalmente assintoticamente estável

## Exemplo rápido

Considere $\dot x_1 = -x_1 + 2x_1^2x_2$, $\dot x_2 = -x_2$ (um exemplo clássico ilustrativo). Calcularíamos:

$$J(x) = \begin{bmatrix} -1+4x_1x_2 & 2x_1^2 \\ 0 & -1 \end{bmatrix}$$

E então testaríamos se $J(x)^T+J(x)$ é definida negativa para todo $x$ — se for, a origem é globalmente estável.

## Quando usar Krasovskii vs. o método "linearizado" que fizemos

| Aspecto | Nosso caso (linear) | Krasovskii (não-linear) |
|---|---|---|
| Sistema | $\dot x = Ax$ | $\dot x = f(x)$ |
| Candidata $V$ | $x^TPx$ | $f(x)^Tf(x)$ |
| O que se resolve | $A^TP+PA=-Q$ para $P$ | Checa se $J(x)^T+J(x) \prec 0$ |
| Tipo de estabilidade | Global (linear) | Pode ser só local, se a condição só vale numa região |

**Limitação importante:** o método de Krasovskii é **suficiente, mas não necessário** — se a condição falhar, isso não prova que o sistema é instável; só significa que essa candidata específica não funcionou (parecido com o que discutimos sobre candidatas de Lyapunov em geral). Nesses casos, tenta-se outras formas de $V(x)$, como o método variável-gradiente ou outras técnicas.



## Krasovskii = "gerador automático" de candidatas

Isso resolve um problema real do método de Lyapunov em geral: para sistemas não-lineares, **não existe uma receita universal** para achar $V(x)$. Normalmente você tem que "adivinhar" ou usar tentativa e erro (por isso $V$ se chama "candidata" — você propõe e testa).

O Krasovskii é uma das técnicas que **tira parte desse chute do processo**, propondo sistematicamente:

$$V(x) = f(x)^Tf(x)$$

em vez de você ter que inventar essa forma na mão.

## Colocando em perspectiva: outras alternativas

Para deixar claro o panorama, o Krasovskii é *uma* entre várias técnicas de construção de candidatas — cada uma com seu domínio de aplicação:

| Método | Ideia central | Quando ajuda |
|---|---|---|
| **Linearização + equação de Lyapunov** (o que fizemos) | Resolve $A^TP+PA=-Q$ | Sistemas lineares, ou análise local via linearização |
| **Krasovskii** | $V(x)=f(x)^Tf(x)$, testa jacobiana | Sistemas não-lineares "bem comportados" |
| **Método variável-gradiente** | Constrói $V$ a partir do gradiente $\nabla V$, impondo condições de simetria | Quando Krasovskii falha |
| **Energia física** | Usa energia cinética+potencial do sistema físico | Sistemas mecânicos, elétricos, com significado físico claro |

## O ponto-chave

Nenhum desses métodos é **necessário** (isto é, nenhum garante encontrar uma candidata válida sempre que o sistema for estável). Cada um é apenas **suficiente** quando funciona. Por isso a teoria de Lyapunov, na prática, envolve um pouco de "arsenal de técnicas" — se uma não funciona, tenta-se outra, ou parte-se para simulação numérica como último recurso.
