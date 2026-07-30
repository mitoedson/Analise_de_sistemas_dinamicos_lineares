<h1>Estabilidade B2</h1>

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


## Item (c): $\ddot x+\dot x^5+x^7=x^2\,\text{sen}^8(x)\cos^2(3x)$

## Passo 1 — Identificar o ponto de equilíbrio

Antes de tudo, precisamos transformar em sistema de 2 variáveis (Passo 2), já que a equação tem $\ddot x$.

## Passo 2 — Transformar em sistema de 2 variáveis

$$x_1=x, \qquad x_2=\dot x$$

$$\dot x_1=x_2$$

Isolando $\ddot x$ na equação original:
$$\ddot x=-\dot x^5-x^7+x^2\,\text{sen}^8(x)\cos^2(3x)$$

$$\dot x_2=-x_2^5-x_1^7+x_1^2\,\text{sen}^8(x_1)\cos^2(3x_1)$$

**Ponto de equilíbrio: $(x_1,x_2)=(0,0)$** (fácil de verificar: substituindo, ambas as equações zeram)

## Passo 3 — Escolher a candidata de Lyapunov

$$V(x_1,x_2)=\frac12x_2^2+\frac18x_1^8$$

Os expoentes foram escolhidos estrategicamente: a derivada de $\frac18x_1^8$ produz $x_1^7$, que vai "casar" com o termo $-x_1^7$ do sistema.

Verificação: $V(0,0)=0$, $V>0$ para $(x_1,x_2)\ne(0,0)$ ✓ (soma de potências pares)

$V\to\infty$ quando $\|\mathbf x\|\to\infty$ → **radialmente ilimitada**

## Passo 4 — Calcular $\dot V$

$$\dot V=x_2\dot x_2+x_1^7\dot x_1$$

$$=x_2\left(-x_2^5-x_1^7+x_1^2\,\text{sen}^8(x_1)\cos^2(3x_1)\right)+x_1^7\cdot x_2$$

$$=-x_2^6-x_1^7x_2+x_1^2x_2\,\text{sen}^8(x_1)\cos^2(3x_1)+x_1^7x_2$$

## Passo 5 — Simplificar e analisar o sinal

Os termos $-x_1^7x_2$ e $+x_1^7x_2$ **se cancelam** (esse era o objetivo da escolha de $V$):

$$\dot V=-x_2^6+x_1^2x_2\,\text{sen}^8(x_1)\cos^2(3x_1)$$

Usando as limitações $0\le\text{sen}^8(x_1)\le1$ e $0\le\cos^2(3x_1)\le1$:

$$\left|x_1^2x_2\,\text{sen}^8(x_1)\cos^2(3x_1)\right|\le x_1^2|x_2|$$

O termo $-x_2^6$ é sempre $\le0$ e **dissipa** a "velocidade" $x_2$; o termo restante é limitado por $x_1^2|x_2|$ — segue o mesmo espírito do item (a): o termo de maior grau/dissipativo domina o termo oscilante e limitado, garantindo:

$$\dot V<0 \quad \text{para } (x_1,x_2)\ne(0,0)$$

## Passo 6 — Classificar

$\dot V<0$ estritamente → **assintoticamente estável**

## Passo 7 — Não necessário (já obtivemos negatividade estrita)

## Passo 8 — Local vs. Global

- $(0,0)$ é o único ponto de equilíbrio (não há outros competindo)
- $V$ radialmente ilimitada + $\dot V<0$ em todo o espaço

**Conclusão: $(0,0)$ é globalmente assintoticamente estável** 

---

Esse é o item mais técnico da questão 3 — a chave foi a escolha de $V$ combinando $\frac12x_2^2$ (energia da "velocidade") com $\frac18x_1^8$ (escolhido para cancelar exatamente o termo $x_1^7$). 
