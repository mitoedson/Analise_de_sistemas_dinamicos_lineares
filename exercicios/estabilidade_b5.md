<h1>Estabilidade B5</h1>

## Método geral

### 1. Identificar o(s) ponto(s) de equilíbrio

Resolver $\dot x=0$ (ou, se o sistema tiver $\ddot x$, transformar em sistema de 2 variáveis primeiro — ver Passo 2).

### 2. Se a equação tiver $\ddot x$, transformar em sistema de 2 variáveis

Definir:

$x_1=x, x_2=\dot x$

Isso converte a equação de segunda ordem em um sistema:
$\dot x_1=x_2, \dot x_2=(\text{isolando } \ddot x \text{ na equação original})$

Lembrando que essa notação, que é bem comum em sistemas dinâmicos/mecânica.

### 2.1 Notação de Newton (pontos sobre a variável)

$$\dot x = \frac{dx}{dt} \qquad \text{(primeira derivada de } x \text{ em relação ao tempo — "velocidade")}$$

$$\ddot x = \frac{d^2x}{dt^2} \qquad \text{(segunda derivada de } x \text{ em relação ao tempo — "aceleração")}$$

### 2.2 Por que essa notação existe

É chamada de **notação de Newton**, e é uma alternativa mais compacta à notação de Leibniz ($\dfrac{dx}{dt}$, $\dfrac{d^2x}{dt^2}$). Ela é extremamente comum em **física** e **sistemas dinâmicos**, justamente porque o tempo $t$ é quase sempre a variável de derivação — então não precisamos escrever $\dfrac{d}{dt}$ toda vez, só colocamos um ponto em cima da variável.

### 2.3 Resumindo

$$\boxed{\dot x=\frac{dx}{dt} \quad(\text{1ª derivada}) \qquad\qquad \ddot x=\frac{d^2x}{dt^2}\quad(\text{2ª derivada})}$$

Cada ponto adicional representa mais uma derivada em relação ao tempo — $\dddot x$ seria a terceira derivada, e assim por diante (embora isso raramente apareça na prática).


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

## $\ddot x+(x-1)^2 \dot x^7+x=\text{sen}\left(\dfrac{\pi x}{2}\right)$

### Passo 1 e 2 — Transformar em sistema de 2 variáveis

$x_1 = x, x_2 = \dot x$

$\dot x_1 = \dot x = x_2$

$\dot x_2 = \ddot x = -(x_1-1)^2x_2^7-x_1+\text{sen}\left(\frac{\pi x_1}{2}\right)$

### Passo 1 (retomando) — Pontos de equilíbrio

$$x_2=0 \quad \text{e} \quad x_1=\text{sen}\left(\frac{\pi x_1}{2}\right)$$

Testando valores simples:
- $x_1=0$: $\text{sen}(0)=0$ ✓
- $x_1=1$: $\text{sen}(\pi/2)=1$ ✓
- $x_1=-1$: $\text{sen}(-\pi/2)=-1$ ✓

**Pontos de equilíbrio: $(0,0)$, $(1,0)$, $(-1,0)$** — o primeiro sistema (dessa questão) com **múltiplos** equilíbrios, por isso a conclusão só pode ser **local**.

### Passo 3 — Escolher a candidata de Lyapunov (interpretação "energia")

Repare que a equação tem a forma mecânica $\ddot x+\text{amortecimento}+\text{restauração}(x)=0$, com força restauradora $h(x_1)=x_1-\text{sen}\left(\dfrac{\pi x_1}{2}\right)$.

A candidata natural é a **energia mecânica**: cinética + potencial, onde o potencial é a integral da força restauradora:

$$P(x_1)=\int h(x_1)\,dx_1=\frac{x_1^2}{2}+\frac{2}{\pi}\cos\left(\frac{\pi x_1}{2}\right)$$

$$V(x_1,x_2)=\frac12x_2^2+P(x_1)$$

### Passo 4 — Calcular $\dot V$

$$\dot V=x_2\dot x_2+P'(x_1)\dot x_1=x_2\left[-(x_1-1)^2x_2^7-h(x_1)\right]+h(x_1)\cdot x_2$$

### Passo 5 — Simplificar

$$\dot V=-(x_1-1)^2x_2^8-h(x_1)x_2+h(x_1)x_2=-(x_1-1)^2x_2^8$$

Os termos com $h(x_1)$ **se cancelam exatamente** — resultado muito limpo:

$$\dot V=-(x_1-1)^2x_2^8\le0$$

### Passo 6 — Classificar cada ponto de equilíbrio

Como $\dot V\le0$ (semi-definida, zera em $x_2=0$ **ou** $x_1=1$), a conclusão depende da **curvatura do potencial $P$** em cada ponto — ou seja, do sinal de $P''(x_1)=1-\dfrac{\pi}{2}\cos\left(\dfrac{\pi x_1}{2}\right)$:

**Em $x_1=0$:** $P''(0)=1-\dfrac{\pi}{2}\approx-0{,}571<0$ → **máximo local** do potencial (como uma bolinha no topo de uma colina) → **instável**

**Em $x_1=1$:** $P''(1)=1-\dfrac{\pi}{2}\cos\left(\dfrac{\pi}{2}\right)=1-0=1>0$ → **mínimo local** (poço de potencial) → candidato a estável

**Em $x_1=-1$:** $P''(-1)=1-\dfrac{\pi}{2}\cos\left(-\dfrac{\pi}{2}\right)=1-0=1>0$ → **mínimo local** → candidato a estável

### Passo 7 — Confirmando estabilidade assintótica em $x_1=\pm1$ via LaSalle

Perto de $(1,0)$: o conjunto $\{\dot V=0\}$ é $\{x_2=0\}\cup\{x_1=1\}$. Se a trajetória ficasse presa em $x_2\equiv0$, precisaria também $\dot x_2\equiv0$, ou seja $h(x_1)=0$ — que localmente só ocorre em $x_1=1$. O único conjunto invariante contido em $\{\dot V=0\}$, próximo desse ponto, é o próprio $(1,0)$.

Pelo Princípio de LaSalle: **$(1,0)$ é localmente assintoticamente estável**. O mesmo argumento vale para $(-1,0)$.

### Conclusão final

$$(0,0):\ \textbf{instável} \qquad (1,0):\ \textbf{localmente assint. estável} \qquad (-1,0):\ \textbf{localmente assint. estável}$$

---

Esse item mostra a técnica mais elegante da questão 3: reconhecer a **estrutura mecânica** (cinética + potencial) por trás da equação, o que revela naturalmente a candidata $V$ certa e explica por que a estabilidade depende da **curvatura do potencial** em cada ponto de equilíbrio (mínimos → estáveis, máximos → instáveis) — exatamente a mesma lógica física que vimos no pêndulo da questão 6!


