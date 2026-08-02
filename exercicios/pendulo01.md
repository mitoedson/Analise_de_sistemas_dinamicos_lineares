<h1>Pêndulo com amortecimento</h1>

O pêndulo num campo gravitacional, sujeito a um amortecimento linear é mostrado abaixo, onde θ é o deslocamento angular do pêndulo em relação ao eixo vertical que passa pelo ponto O;
$mL^2$ é o momento de inércia da massa m; c é a constante de amortecimento; g é a aceleração da gravidade. Introduzindo as variáveis de estado:
```math
x_1 = θ
```
```math
x_2 = \frac{dθ}{dt}
```

obtemos:
```math
\frac{dx_1}{dt} = x_2
```
```math
\frac{dx_2}{dt} = -\frac{g}{L}sen(x_1)-\frac{c}{mL}x_2
```

<div align="center">
<img width="466" height="481" alt="image" src="https://github.com/user-attachments/assets/9dcc6653-ad37-4c98-9865-e9eb7f69b074" />
</div>

Analise a estabilidade para:

(a) $V(\mathbf x)=\dfrac12mL^2x_2^2+mgL(1-\cos x_1)$

(b) $V(\mathbf x)=\dfrac12x_2^2+\dfrac{b^2}{2}\left(x_1+\dfrac{x_2}{b}\right)^2+2a(1-\cos x_1)$, com $a=g/L,\ b=c/(mL)$


## Contexto do sistema

$$x_1=\theta, \qquad x_2=\dot\theta$$

$$\dot x_1=x_2, \qquad \dot x_2=-\frac{g}{L}\text{sen}(x_1)-\frac{c}{mL}x_2$$

## (a): $V(\mathbf x)=\dfrac12mL^2x_2^2+mgL(1-\cos x_1)$

## Passo 1 — Verificar positividade

- $\dfrac12mL^2x_2^2$ = energia cinética, sempre $\ge0$, zero só quando $x_2=0$
- $mgL(1-\cos x_1)$ = energia potencial, $\ge0$ (pois $\cos x_1\le1$), zero apenas em $x_1=0$ (localmente)

$V\ge0$, com $V=0$ apenas em $(0,0)$ → **positiva definida (localmente)**

## Passo 2 — Calcular $\dot V$

$$\dot V=mL^2x_2\dot x_2+mgL\,\text{sen}(x_1)\dot x_1$$

Substituindo:
$$\dot V=mL^2x_2\left(-\frac{g}{L}\text{sen}(x_1)-\frac{c}{mL}x_2\right)+mgL\,\text{sen}(x_1)\cdot x_2$$

$$=-mgLx_2\,\text{sen}(x_1)-cLx_2^2+mgLx_2\,\text{sen}(x_1)$$

Os dois primeiros/últimos termos se cancelam:

$$\dot V=-cLx_2^2$$

## Passo 3 — Analisar o sinal

$$\dot V=-cLx_2^2\le0 \quad (\text{pois } c,L>0)$$

Mas $\dot V=0$ **sempre que $x_2=0$**, independente de $x_1$ — apenas **semi-definida**.

## Passo 4 — Aplicar LaSalle

Se $x_2\equiv0$, então $\dot x_2\equiv0$ também, exigindo $\text{sen}(x_1)=0 \Rightarrow x_1=0$ (localmente). Único conjunto invariante: $(0,0)$.

**Conclusão: $(0,0)$ é localmente assintoticamente estável** ✓

---

## (b): $V(\mathbf x)=\dfrac12x_2^2+\dfrac{b^2}{2}\left(x_1+\dfrac{x_2}{b}\right)^2+2a(1-\cos x_1)$, com $a=g/L,\ b=c/(mL)$

## Passo 1 — Interpretação: três termos, dois físicos e um "artifício matemático"

- $\dfrac12x_2^2$: energia cinética (física)
- $2a(1-\cos x_1)$: energia potencial (física)
- $\dfrac{b^2}{2}\left(x_1+\dfrac{x_2}{b}\right)^2$: **termo cruzado artificial**, sem significado físico — adicionado propositalmente para gerar cancelamentos melhores

## Passo 2 — Calcular $\dot V$ (usando $w=x_1+x_2/b$)

Após o cálculo completo (regra da cadeia, substituindo o sistema, com vários cancelamentos):

$$\dot V=-b\left(x_2^2+a\,x_1\,\text{sen}(x_1)\right)$$

## Passo 3 — Analisar o sinal

Na região $|x_1|<\pi$: $x_1$ e $\text{sen}(x_1)$ têm **sempre o mesmo sinal**, então $x_1\,\text{sen}(x_1)>0$ para $x_1\ne0$.

$$x_2^2+ax_1\,\text{sen}(x_1)>0 \quad \text{para } (x_1,x_2)\ne(0,0),\ |x_1|<\pi$$

Como $a,b>0$:
$$\dot V<0 \quad \text{estritamente, para } (x_1,x_2)\ne(0,0), \text{ dentro de } |x_1|<\pi$$

## Passo 4 — Classificar

Diferente do item (a), aqui $\dot V$ já é **estritamente negativa** (localmente, pois cobre apenas o intervalo entre $-\pi$ e $+\pi$)— **não precisamos do LaSalle**.

**Conclusão: $(0,0)$ é localmente assintoticamente estável** ✓

---

## Por que ambos os itens são apenas "locais" (nunca globais)

$$\boxed{\text{O pêndulo tem MÚLTIPLOS equilíbrios: } (0,0), (\pi,0), (2\pi,0), \dots}$$

Fisicamente, $(\pi,0)$ representa o pêndulo "de cabeça para cima" (equilíbrio instável, mas existente). Como há mais de um ponto de equilíbrio competindo pelo espaço, a conclusão **nunca pode ser global** — cada análise vale apenas numa vizinhança da origem (reforçado, no item b, pela restrição explícita $|x_1|<\pi$).

## Comparando os dois itens

| | Item (a) | Item (b) |
|---|---|---|
| Candidata | Energia física pura | Energia + termo cruzado artificial |
| $\dot V$ | $-cLx_2^2$ (semi-definida) | $-b(x_2^2+ax_1\text{sen}(x_1))$ (estrita) |
| Precisa de LaSalle? | Sim | Não |
| Conclusão | Localmente assint. estável | Localmente assint. estável |

---

---

## Propósito

A questão tem como objetivo aplicar o **Método Direto de Lyapunov** para provar a estabilidade (geralmente assintótica, e frequentemente **global**) de sistemas dinâmicos **não lineares**, **sem** depender de linearização — trabalhando diretamente com a estrutura completa e exata do sistema.

O método de Lyapunov, quando bem-sucedido, pode provar propriedades **globais**, válidas para qualquer condição inicial no espaço de estados inteiro.

**Não existe fórmula automática**. Encontrar a candidata $V$ certa é, em parte, uma questão de **reconhecer padrões** na estrutura do sistema.

## Passo a passo genérico

### Passo 1 — Identificar o ponto de equilíbrio

Geralmente é a origem $(0,0)$ (verificar substituindo nas equações).

É adequado verificar o ponto de equilíbrio, pois é um indício para escolher a candidata de Lyapunov.

### Passo 2 — Escolher uma candidata $V$

Estratégia recomendada, em ordem de tentativa:

**(a) Primeira tentativa — candidata quadrática simples:**
$$V=x_1^2+x_2^2 \quad \text{(ou com pesos: } V=a x_1^2+bx_2^2\text{, se houver assimetria)}$$

**(b) Se o sistema tiver expoentes diferentes** (como $x_1^8$ ou $x_2^4$ no lugar de quadrados), **casar os expoentes** de $V$ com os termos do sistema, de forma que a derivada de $V$ produza um termo que **cancele exatamente** com um termo "incômodo" do sistema (ex: $V=\frac18x_1^8+\frac12x_2^2$ para cancelar $x_1^7$).

**(c) Se o sistema tiver interpretação física** (mecânico, como pêndulo): usar a **energia real** (cinética + potencial) como candidata.

### Passo 3 — Verificar que $V$ é positiva definida

$$V(0,0)=0 \quad \text{e} \quad V(x_1,x_2)>0 \text{ para } (x_1,x_2)\ne(0,0)$$

Geralmente óbvio por construção (soma de potências pares com coeficientes positivos).

Se possível, verificar também se $V$ é **radialmente ilimitada** ($V\to\infty$ quando $\|\mathbf x\|\to\infty$) — necessário para conclusão **global**.

### Passo 4 — Calcular $\dot V$ pela regra da cadeia

$$\dot V=\frac{\partial V}{\partial x_1}\dot x_1+\frac{\partial V}{\partial x_2}\dot x_2$$

Substituir as expressões de $\dot x_1$ e $\dot x_2$ do sistema original.

### Passo 5 — Simplificar e buscar cancelamentos

- Expandir tudo e agrupar termos semelhantes
- Procurar termos que se **cancelam exatamente** (geralmente é por isso que a candidata foi escolhida daquela forma)
- Se sobrar um **termo cruzado com sinal indefinido** (tipo $x_1x_2^3$), ajustar os **coeficientes/pesos** de $V$ (introduzindo parâmetros como $a,b$, se a questão permitir) para forçar esse termo a se cancelar

### Passo 6 — Analisar o sinal de $\dot V$

- Tentar reescrever como **soma/produto de termos sempre não-positivos** (quadrados, potências pares com sinal negativo, produtos notáveis como $-(a-b)^2$)
- Usar limitações conhecidas de funções trigonométricas ($|\text{sen}|\le1$, etc.) se aplicável

### Passo 7 — Classificar o resultado

| Resultado de $\dot V$ | Conclusão |
|---|---|
| $\dot V<0$ estritamente, para todo $\mathbf x\ne0$ | Assintoticamente estável |
| $\dot V\le0$, mas zera fora da origem também | Apenas "estável" — ir para o Passo 8 (LaSalle) |
| $V$ radialmente ilimitada + $\dot V<0$ em todo o espaço | Estabilidade **global** |



Vamos organizar todas as classificações possíveis que podem sair de uma análise pelo Método Direto de Lyapunov, com a condição exata que leva a cada uma.

## Quadro completo de classificações

| Condição sobre $V$ | Condição sobre $\dot V$ | Classificação |
|---|---|---|
| $V>0$ | $\dot V\le0$ (semi-definida negativa) | **Estável** (não necessariamente assintótico) |
| $V>0$ | $\dot V<0$ (estrita, localmente) | **Assintoticamente estável (local)** |
| $V>0$, radialmente ilimitada | $\dot V<0$ estrita, **em todo o espaço**, $(x,y) \ne (0,0)$ | **Globalmente assintoticamente estável** |
| $V>0$ | $\dot V\le0$, mas único conjunto invariante em $\{\dot V=0\}$ é a origem (LaSalle) | **Assintoticamente estável** (resgatada via LaSalle) |
| $V>0$ | $\dot V>0$ em alguma região próxima do equilíbrio | **Instável** |
| — | $V$ **não** é positiva definida | **Inconclusivo** (candidata falhou — não é uma classificação do sistema, é falha do método) |

## Detalhando cada categoria

### 1. Estável (não assintótico) — "marginalmente estável"

$\dot V\le0$, mas zera **fora** da origem também (sem resgate por LaSalle). As trajetórias não se afastam, mas também não necessariamente convergem — podem ficar orbitando/oscilando. Exemplo típico: **centro**.

### 2. Assintoticamente estável (local)

$\dot V<0$ estritamente perto do equilíbrio (mas a prova só vale numa vizinhança, ou existem outros equilíbrios competindo). Exemplo: o pêndulo (item 6), item 3(e).

### 3. Globalmente assintoticamente estável

$\dot V<0$ em **todo** o espaço + $V$ radialmente ilimitada + equilíbrio único. Exemplo: itens 3(a-d), 5(a-d).

### 4. Assintoticamente estável via LaSalle

Quando $\dot V$ é só semi-definida, mas você prova que o único conjunto invariante em $\{\dot V=0\}$ é a origem. Exemplo: item 5(b), pêndulo item 6(a).

### 5. Instável

Quando você consegue mostrar $\dot V>0$ em alguma região arbitrariamente próxima da origem (menos comum de aparecer explicitamente nos nossos exercícios, mas é uma conclusão válida do método — existe um **Teorema de Chetaev** especificamente para provar instabilidade via Lyapunov).

## O que **não** é uma classificação, mas sim uma falha do processo

$$\boxed{V \text{ não positiva definida} \;\Rightarrow\; \text{candidata FALHOU} \;\Rightarrow\; \text{tente outra candidata (nada se conclui sobre o sistema)}}$$

Isso é diferente de "instável" — é simplesmente "não consegui provar nada com essa tentativa".

## Resumo visual da árvore de decisão

```
V é positiva definida?
│
├── Não → INCONCLUSIVO (tentar outra candidata)
│
└── Sim → Qual o sinal de V̇?
          │
          ├── V̇ > 0 em alguma região → INSTÁVEL
          │
          ├── V̇ ≤ 0 (semi-definida)
          │   │
          │   ├── Único conjunto invariante em {V̇=0} é a origem (LaSalle)? 
          │   │   ├── Sim → ASSINTOTICAMENTE ESTÁVEL
          │   │   └── Não → ESTÁVEL (não assintótico)
          │
          └── V̇ < 0 estrita
              │
              ├── Vale só localmente → ASSINTOTICAMENTE ESTÁVEL (local)
              │
              └── Vale em todo espaço + V rad. ilimitada + equilíbrio único
                  → GLOBALMENTE ASSINTOTICAMENTE ESTÁVEL
```

---

Esse quadro resume todas as saídas possíveis do método!

