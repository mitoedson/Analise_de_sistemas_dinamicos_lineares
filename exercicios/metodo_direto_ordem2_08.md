<h1>Método Direto de Lyapunov - Equações de 2ª Ordem - 08</h1>

<img width="600" alt="image" src="https://github.com/user-attachments/assets/5ab4d77c-8c4d-4d1d-9888-8bf881e45c8e" />

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

## Sistema: $\dot x_1=-x_1+x_2^3,\quad \dot x_2=-x_1-x_2$

## Candidata: $V(x_1,x_2)=ax_1^2+bx_2^4$

## Passo 1 — Verificar positividade

Para $V>0$ (fora da origem), precisamos de $a>0$ e $b>0$ (soma de potências pares com coeficientes positivos).

## Passo 2 — Calcular $\dot V$

$$\dot V=\frac{\partial V}{\partial x_1}\dot x_1+\frac{\partial V}{\partial x_2}\dot x_2=2ax_1\dot x_1+4bx_2^3\dot x_2$$

Substituindo:
$$\dot V=2ax_1(-x_1+x_2^3)+4bx_2^3(-x_1-x_2)$$

$$=-2ax_1^2+2ax_1x_2^3-4bx_1x_2^3-4bx_2^4$$

## Passo 3 — Agrupar o termo "problemático" ($x_1x_2^3$)

$$\dot V=-2ax_1^2+(2a-4b)x_1x_2^3-4bx_2^4$$

Esse termo cruzado $x_1x_2^3$ **não tem sinal controlado** (pode ser positivo ou negativo, dependendo dos sinais de $x_1$ e $x_2$) — exatamente o mesmo tipo de problema que enfrentamos no item 5(b)! A solução é **escolher $a$ e $b$ de forma que esse termo se cancele**.

## Passo 4 — Impor o cancelamento

$$2a-4b=0 \;\Rightarrow\; a=2b$$

Com essa escolha, o termo cruzado desaparece:

$$\dot V=-2ax_1^2-4bx_2^4$$

## Passo 5 — Analisar o sinal final

Com $a=2b$ e $b>0$ (o que garante $a=2b>0$ também):

$$\dot V=-2ax_1^2-4bx_2^4\le0$$

Como $a>0$ e $b>0$: $\dot V<0$ **estritamente** para todo $(x_1,x_2)\ne(0,0)$ (a soma de dois termos negativos só se anula quando ambos são zero, ou seja, $x_1=0$ e $x_2=0$).

## Conclusão

$$\boxed{a=2b, \quad \text{com } b>0 \text{ (e, portanto, } a>0\text{)}}$$

Com essa relação entre $a$ e $b$:
- $V>0$ para $(x_1,x_2)\ne(0,0)$, radialmente ilimitada ✓
- $\dot V<0$ para $(x_1,x_2)\ne(0,0)$ ✓

**O sistema é globalmente assintoticamente estável**, para qualquer $a=2b$ com $b>0$ (por exemplo, $a=2,b=1$; ou $a=4,b=2$; etc — qualquer par nessa proporção).


