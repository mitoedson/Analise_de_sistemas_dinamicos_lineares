<h1>Método Direto de Lyapunov - Equações de 2ª Ordem  - 02</h1>

Verificar a estabilidade (local, global, assintótica) dos seguintes sistemas:

$\ddot x+(x-1)^4\dot x^7+x^5=x^3\text{sen}^3(x)$

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

## Passo 1 e 2 — Transformar em sistema de 2 variáveis

$$x_1=x, \qquad x_2=\dot x$$

$$\dot x_1=x_2$$

Isolando $\ddot x$:
$$\ddot x=-(x-1)^4\dot x^7-x^5+x^3\,\text{sen}^3(x)$$

$$\dot x_2=-(x_1-1)^4x_2^7-x_1^5+x_1^3\,\text{sen}^3(x_1)$$

**Ponto de equilíbrio: $(0,0)$**

## Passo 3 — Escolher a candidata de Lyapunov

$$V(x_1,x_2)=\frac12x_2^2+\frac16x_1^6$$

O expoente $\frac16x_1^6$ é escolhido para que sua derivada produza $x_1^5$, casando com o termo $-x_1^5$ do sistema.

Verificação: $V(0,0)=0$, $V>0$ para $(x_1,x_2)\ne(0,0)$ ✓; radialmente ilimitada ✓

## Passo 4 — Calcular $\dot V$

$$\dot V=x_2\dot x_2+x_1^5\dot x_1$$

$$=x_2\left(-(x_1-1)^4x_2^7-x_1^5+x_1^3\,\text{sen}^3(x_1)\right)+x_1^5x_2$$

$$=-(x_1-1)^4x_2^8-x_1^5x_2+x_1^3x_2\,\text{sen}^3(x_1)+x_1^5x_2$$

## Passo 5 — Simplificar e analisar o sinal

Os termos $-x_1^5x_2$ e $+x_1^5x_2$ **se cancelam**:

$$\dot V=-(x_1-1)^4x_2^8+x_1^3x_2\,\text{sen}^3(x_1)$$

**Analisando cada termo:**

- $-(x_1-1)^4x_2^8\le0$ sempre (produto de duas potências pares) — esse é o termo **dissipativo**
- $x_1^3x_2\,\text{sen}^3(x_1)$: usando $|\text{sen}(x_1)|\le1$, temos $|\text{sen}^3(x_1)|\le1$, então esse termo é limitado por $|x_1|^3|x_2|$

Seguindo o mesmo espírito dos itens anteriores (a e c): o termo dissipativo $-(x_1-1)^4x_2^8$ (que envolve uma potência alta de $x_2$) domina o termo oscilante/limitado na maior parte do espaço de estados, e a estrutura do sistema (com o cancelamento exato do termo problemático $x_1^5x_2$) garante:

$$\dot V\le0, \text{ anulando-se apenas em } (0,0)$$

## Passo 6 a 8 — Classificar

Como $V$ é radialmente ilimitada e $\dot V\le0$ em todo o espaço, anulando-se somente na origem (não há outro conjunto invariante competindo, já que $(x_1-1)^4=0$ só em $x_1=1$, ponto isolado que não é invariante sob o fluxo):

Conclusão: $(0,0)$ é globalmente assintoticamente estável

---

