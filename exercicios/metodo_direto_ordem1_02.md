<h1>Método Direto de Lyapunov - Equações de 1ª Ordem - 02</h1>

Verificar a estabilidade (local, global, assintótica) dos seguintes sistemas:

$\dot x=(5-x)^5$

---

## Método geral

### 1. Identificar o(s) ponto(s) de equilíbrio

Resolver $\dot x=0$ (ou, se o sistema tiver $\ddot x$, transformar em sistema de 2 variáveis primeiro — ver Passo 2).

### 2. Se a equação tiver $\ddot x$, transformar em sistema de 2 variáveis

Definir:
$$x_1=x, \qquad x_2=\dot x$$

Isso converte a equação de segunda ordem em um sistema:
$$\dot x_1=x_2, \qquad \dot x_2=(\text{isolando } \ddot x \text{ na equação original})$$

### 3. Escolher a candidata de Lyapunov $V$

- **Caso escalar simples:** $V(x)=x^2$ (ou $(x-x^*)^2$ se o equilíbrio não for a origem, como no item b: $V=(x-5)^2$)
- **Caso com $\ddot x$ (2 variáveis):** combinar "energia cinética" ($x_2^2$) com um termo em $x_1$ que, ao derivar, produza um expoente compatível com o termo de maior grau em $x_1$ na equação (ex: item c usava $\frac18x_1^8$ para casar com o termo $x_1^7$)

**Sempre verificar:** $V(x^*)=0$ e $V>0$ fora do equilíbrio (positiva definida). Se $V\to\infty$ quando $\|\mathbf x\|\to\infty$, ela é **radialmente ilimitada** (necessário para conclusão global).

### 4. Calcular $\dot V$ pela regra da cadeia

$$\dot V=\frac{dV}{dx}\cdot\dot x \qquad \text{(escalar)} \qquad \text{ou} \qquad \dot V=\frac{\partial V}{\partial x_1}\dot x_1+\frac{\partial V}{\partial x_2}\dot x_2 \qquad \text{(2 variáveis)}$$

Substituir as expressões do sistema original.

### 5. Simplificar e analisar o sinal de $\dot V$

- Procurar **cancelamentos** entre termos (geralmente a escolha de $V$ foi feita propositalmente para gerar esses cancelamentos)
- Usar **limitações conhecidas** de funções trigonométricas: $|\text{sen}(\cdot)|\le1$, $|\cos(\cdot)|\le1$, $\text{sen}^{2n}(\cdot)\ge0$, etc.
- Comparar **ordens de grandeza**: termos de grau maior (ex: $x^4$) dominam termos limitados ou de grau menor, tanto para $|x|$ grande quanto pequeno
- Tentar reconhecer **produtos notáveis** (como $(a-b)^2=a^2-2ab+b^2$), que garantem $\dot V\le0$ de forma óbvia

### 6. Classificar o resultado

| Resultado de $\dot V$ | Conclusão |
|---|---|
| $\dot V<0$ para todo $x\ne x^*$ (estrita) | Assintoticamente estável |
| $\dot V\le0$, mas zera fora da origem também | Só "estável" pelo teorema básico — ir para o Passo 7 |
| $V$ radialmente ilimitada + $\dot V<0$ em **todo** o espaço | Estabilidade **global** |
| $\dot V<0$ só numa região limitada perto de $x^*$ | Estabilidade apenas **local** |

### 7. Se $\dot V$ for só semi-definida negativa: aplicar o Princípio de LaSalle

Verificar se o **único conjunto invariante** contido em $\{\dot V=0\}$ é o próprio ponto de equilíbrio — se sim, resgata-se a conclusão de **assintoticamente estável**.

### 8. Decidir local vs. global

- Existem **outros pontos de equilíbrio** competindo no espaço? → conclusão só pode ser **local**
- $V$ é radialmente ilimitada e $\dot V<0$ vale em **todo o espaço de estados** (sem restrição de região)? → conclusão pode ser **global**

---

## Passo 1 — Identificar o ponto de equilíbrio

$$\dot x=0 \;\Rightarrow\; (5-x)^5=0 \;\Rightarrow\; x=5$$

**Ponto de equilíbrio: $x^*=5$** (repare que **não** é a origem — isso vai importar na escolha de $V$)

## Passo 2 — Não se aplica (equação já é de primeira ordem, sem $\ddot x$)

## Passo 3 — Escolher a candidata de Lyapunov

Como o equilíbrio está em $x=5$ (não em $0$), a candidata precisa ser **centrada nesse ponto**:

$$V(x)=(x-5)^2$$

Verificação: $V(5)=0$ e $V(x)>0$ para $x\ne5$ ✓ (positiva definida em torno do equilíbrio)

Além disso, $V(x)\to\infty$ quando $|x|\to\infty$ → **radialmente ilimitada**

## Passo 4 — Calcular $\dot V$

$$\dot V=2(x-5)\cdot\dot x=2(x-5)\cdot(5-x)^5$$

## Passo 5 — Simplificar e analisar o sinal

Repare que $(x-5)=-(5-x)$, então:

$$\dot V=2\left[-(5-x)\right](5-x)^5=-2(5-x)^6$$

Como o expoente é **par** (6), $(5-x)^6\ge0$ sempre, com igualdade **apenas** quando $x=5$:

$$\dot V=-2(5-x)^6\le0, \quad \text{com } \dot V=0 \text{ apenas em } x=5$$

Ou seja, $\dot V<0$ **estritamente** para todo $x\ne5$ — não há necessidade de LaSalle aqui.

## Passo 6 — Classificar

$\dot V<0$ para todo $x\ne5$ (estrita) → **assintoticamente estável**

## Passo 7 — Não necessário (já obtivemos estrita negatividade direto)

## Passo 8 — Local vs. Global

- Não existe **nenhum outro ponto de equilíbrio** competindo (a equação $(5-x)^5=0$ só tem a raiz $x=5$, já que é uma potência ímpar de um único fator linear)
- $V$ é radialmente ilimitada, e $\dot V<0$ vale em **todo** o espaço (não há restrição de região — vale para qualquer $x\in\mathbb R$)

Conclusão: $x=5$ é globalmente assintoticamente estável

---

## Comparando com um caminho alternativo (o "atalho" direto)

Vale mostrar também o caminho mais rápido, sem passar formalmente por $V$: como o expoente de $(5-x)^5$ é **ímpar**, o sinal de $\dot x$ **acompanha** o sinal de $(5-x)$:
- $x<5 \Rightarrow \dot x>0$ (x cresce, se aproxima de 5)
- $x>5 \Rightarrow \dot x<0$ (x decresce, se aproxima de 5)

Isso já mostra diretamente que **qualquer** ponto inicial converge para $x=5$ — o mesmo resultado, mas sem precisar formalizar com $V$. Os dois caminhos são equivalentes.




