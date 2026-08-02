<h1>Método Direto de Lyapunov - Equações de 1ª Ordem - 01</h1>

Verificar a estabilidade (local, global, assintótica) dos seguintes sistemas:

$\dot x=-x^3+\text{sen}^4(x)$

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

### Passo 1 — Identificar o ponto de equilíbrio

$$\dot x=0 \;\Rightarrow\; -x^3+\text{sen}^4(x)=0$$

Testando $x=0$: $-0+\text{sen}^4(0)=0$ ✓ → **$x=0$ é ponto de equilíbrio**

### Passo 2 — Escolher a candidata de Lyapunov

$$V(x)=x^2$$

Verificação: $V(0)=0$ e $V(x)>0$ para $x\ne0$ ✓ (positiva definida)

Além disso, $V(x)\to\infty$ quando $|x|\to\infty$ → **radialmente ilimitada** (abre espaço para conclusão global)

### Passo 3 — Calcular $\dot V$

$$\dot V=2x\dot x=2x\left(-x^3+\text{sen}^4(x)\right)=-2x^4+2x\ \text{sen}^4(x)$$

### Passo 4 — Analisar o sinal de $\dot V$

Usamos a limitação $0\le\text{sen}^4(x)\le1$ para todo $x$, então:
$$\left|2x\,\text{sen}^4(x)\right|\le2|x|$$

Comparando os dois termos:
- $-2x^4$ é sempre $\le0$, e cresce em módulo como $x^4$
- $2x\,\text{sen}^4(x)$ é limitado em módulo por $2|x|$ (cresce só como $x^1$)

Para $|x|$ **grande**: $2x^4$ domina completamente $2|x|$, então $\dot V<0$

Para $x$ **pequeno** (perto de 0): usando $\text{sen}(x)\approx x$, temos $\text{sen}^4(x)\approx x^4$, então $2x\,\text{sen}^4(x)\approx2x^5$ — de ordem **superior** a $-2x^4$, logo $-2x^4$ domina localmente também

**Em ambos os regimes, $-2x^4$ domina**, garantindo:
$$\dot V<0 \quad \text{para todo } x\ne0$$

### Passo 5 — Conclusão

Temos:
- $V>0$ para $x\ne0$, radialmente ilimitada
- $\dot V<0$ para todo $x\ne0$ 

$x=0$ é globalmente assintoticamente estável** 


**Resumo da lógica:** o termo $-x^3$ (que dá origem ao $-2x^4$ em $\dot V$) sempre "puxa" o sistema de volta para zero, e cresce mais rápido que o termo oscilante e limitado $\text{sen}^4(x)$ — tanto para $x$ grande quanto para $x$ pequeno — garantindo convergência a partir de **qualquer** ponto inicial (por isso a conclusão é **global**).

