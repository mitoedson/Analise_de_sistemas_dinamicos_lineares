<h1>Método Direto de Lyapunov - Equações de 2ª Ordem - 07</h1>

Usando funções de Lyapunov, investigar a estabilidade do seguinte sistema:

$\dot x=x^3-y^3,\quad \dot y=2xy^2+4x^2y+2y^3$

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

## Passo 1 — Ponto de equilíbrio

Verificando a origem: $\dot x(0,0)=0$, $\dot y(0,0)=0$ ✓ → **$(0,0)$ é ponto de equilíbrio**

(Não vamos nos aprofundar em achar outros pontos, porque, como veremos, a estratégia de resolução aqui é diferente — vamos direto tentar provar **instabilidade**, seguindo o gabarito.)

## Passo 2 — Por que a estratégia aqui é diferente dos itens anteriores

Repare que, diferente dos itens (a), (b), (c) — todos "assintoticamente estável" ou "estável" — o **gabarito deste item afirma "instável"**. Isso significa que, em vez de buscar uma candidata $V$ que prove $\dot V\le0$, a estratégia é **mostrar diretamente** que as trajetórias se afastam da origem em alguma direção específica — não precisamos necessariamente de uma função de Lyapunov completa para isso.

## Passo 3 — Analisando o sistema restrito ao eixo $y=0$

A técnica aqui é examinar o comportamento do sistema **sobre um eixo específico**, para ver se ele "empurra" as trajetórias para longe da origem.

**Substituindo $y=0$ nas duas equações:**

$$\dot x\Big|_{y=0}=x^3-0^3=x^3$$

$$\dot y\Big|_{y=0}=2x(0)^2+4x^2(0)+2(0)^3=0$$

## Passo 4 — Interpretando esse resultado

No eixo $y=0$, o sistema se reduz a:
$$\dot x=x^3, \qquad \dot y=0$$

Ou seja: **sobre o eixo $y=0$, o sistema fica "preso" nesse eixo** (já que $\dot y=0$ ali), e a dinâmica de $x$ sozinha é:

$$\dot x=x^3$$

## Passo 5 — Analisando essa dinâmica escalar restrita

Para $x_0>0$ pequeno (próximo da origem, mas positivo): $\dot x=x^3>0$ → **$x$ está crescendo**, afastando-se da origem, permanecendo sempre em $y=0$

Para $x_0<0$ pequeno: $\dot x=x^3<0$ → **$x$ está decrescendo** (ficando mais negativo), também se afastando da origem

## Passo 6 — Conclusão sobre instabilidade

$$\boxed{\text{Existem trajetórias, começando ARBITRARIAMENTE PERTO da origem (sobre o eixo } y=0\text{), que se AFASTAM da origem}}$$

Isso é **exatamente** a definição de instabilidade: não importa quão pequeno você escolha um raio $\epsilon$ ao redor da origem, sempre existe uma condição inicial dentro desse raio (por exemplo, $x_0=\epsilon/2, y_0=0$) cuja trajetória **eventualmente sai** dessa vizinhança.

## Conclusão final

**A origem é instável**: *"No eixo y=0, o sistema vira $\dot x=x^3$, $\dot y=0$, e soluções com $x_0>0$ pequeno se afastam da origem. Logo: instável."*

---

## Por que essa abordagem foi diferente das anteriores (sem usar $V$ diretamente)

Esse item ilustra uma técnica alternativa dentro do Método Direto de Lyapunov: em vez de construir uma função $V$ completa, às vezes é mais direto **encontrar uma direção/subespaço específico** (aqui, o eixo $y=0$) onde o comportamento do sistema já revela claramente a instabilidade — evitando o trabalho de montar e testar candidatas $V$ que, de qualquer forma, não serviriam para provar instabilidade da forma usual (lembra que $\dot V>0$ só perto da origem já basta para instabilidade, mas encontrar isso diretamente através de uma "restrição de eixo" é frequentemente mais simples).

Isso também se conecta com o **Teorema de Chetaev** (uma variante do método de Lyapunov especificamente desenhada para provar instabilidade), embora aqui tenhamos usado uma versão mais informal e direta desse tipo de raciocínio.

