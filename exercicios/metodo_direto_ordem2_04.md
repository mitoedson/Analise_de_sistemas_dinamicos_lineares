<h1>Método Direto de Lyapunov - Equações de 2ª Ordem - 04</h1>

Usando funções de Lyapunov, investigar a estabilidade do seguinte sistema:

```math
\frac{dx}{dt}=-x^3+xy^2
```
```math
\frac{dy}{dt}=-2x^2y-y^3
```
assintoticamente.

---

## Propósito

A questão tem como objetivo aplicar o **Método Direto de Lyapunov** para provar a estabilidade (geralmente assintótica, e frequentemente **global**) de sistemas dinâmicos **não lineares**, **sem** depender de linearização — trabalhando diretamente com a estrutura completa e exata do sistema.

O método de Lyapunov, quando bem-sucedido, pode provar propriedades **globais**, válidas para qualquer condição inicial no espaço de estados inteiro.

## O desafio central

Ao contrário da questão 4 (sistemas lineares, onde existe um método **sistemático e garantido** — resolver a equação de Lyapunov $A^TP+PA=-Q$), aqui **não existe fórmula automática**. Encontrar a candidata $V$ certa é, em parte, uma questão de **reconhecer padrões** na estrutura do sistema.

## Passo a passo genérico

### Passo 1 — Identificar o ponto de equilíbrio

Geralmente é a origem $(0,0)$ (verificar substituindo nas equações).

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

### Passo 8 — Se necessário, aplicar o Princípio de LaSalle

Quando $\dot V$ é só semi-definida negativa: verificar se o **único conjunto invariante** contido em $\{\dot V=0\}$ é a própria origem. Se sim, resgata-se a conclusão de assintoticamente estável.

---

$$\boxed{\text{Escolher } V \text{ (guiado pela estrutura do sistema)} \to \text{Verificar } V>0 \to \text{Calcular } \dot V \to \text{Ajustar pesos se necessário} \to \text{Analisar sinal} \to \text{Concluir (LaSalle se preciso)}}$$

## Passo 1 — Identificar o ponto de equilíbrio

Verificando a origem: $\dot x(0,0)=0$, $\dot y(0,0)=0$ ✓ → **$(0,0)$ é ponto de equilíbrio**

## Passo 2 — Escolher a candidata de Lyapunov

Como o sistema tem uma estrutura simétrica entre $x$ e $y$ (termos $x^2y^2$ "cruzados" em ambas as equações), a candidata mais natural para tentar primeiro é:

$$V(x,y)=x^2+y^2$$

**Verificação de positividade:** $V(0,0)=0$ e $V(x,y)>0$ para $(x,y)\ne(0,0)$ ✓ (soma de quadrados)

**Radialmente ilimitada:** $V\to\infty$ quando $\|\mathbf x\|\to\infty$ ✓ (abre espaço para conclusão global)

## Passo 3 — Calcular $\dot V$ pela regra da cadeia

$$\dot V=\frac{\partial V}{\partial x}\dot x+\frac{\partial V}{\partial y}\dot y=2x\dot x+2y\dot y$$

Substituindo as expressões do sistema:

$$\dot V=2x(-x^3+xy^2)+2y(-2x^2y-y^3)$$

## Passo 4 — Expandir

$$\dot V=2x(-x^3)+2x(xy^2)+2y(-2x^2y)+2y(-y^3)$$

$$=-2x^4+2x^2y^2-4x^2y^2-2y^4$$

## Passo 5 — Simplificar (agrupando os termos $x^2y^2$)

$$\dot V=-2x^4+(2-4)x^2y^2-2y^4=-2x^4-2x^2y^2-2y^4$$

## Passo 6 — Analisar o sinal

Colocando $-2$ em evidência:

$$\dot V=-2\left(x^4+x^2y^2+y^4\right)$$

Analisando o termo entre parênteses:
- $x^4\ge0$ sempre
- $x^2y^2\ge0$ sempre  
- $y^4\ge0$ sempre

A soma dos três só é **zero** quando **todos** são zero simultaneamente, ou seja, apenas em $x=0$ **e** $y=0$. Para qualquer outro ponto, pelo menos um dos três termos é estritamente positivo, tornando a soma positiva.

$$\dot V<0 \quad \text{para todo } (x,y)\ne(0,0)$$

## Passo 7 — Classificar

- $V>0$ para $(x,y)\ne(0,0)$, radialmente ilimitada ✓
- $\dot V<0$ estritamente, para todo $(x,y)\ne(0,0)$ ✓

**Conclusão: a origem é globalmente assintoticamente estável** ✓ — bate com o gabarito.

---

## Por que essa candidata funcionou "de primeira" (sem precisar ajustar pesos)

Repare que, diferente do item (b) (onde $V=x^2+y^2$ falhava e precisamos ajustar para $V=x^2+2y^2$), aqui a candidata simples **já funcionou direto** — porque o sistema tem uma **simetria perfeita** entre $x$ e $y$ nos termos cruzados ($xy^2$ na primeira equação, $x^2y$ na segunda, com coeficientes que se combinam bem: $2\times1=2$ e $2\times(-2)=-4$, dando $2-4=-2$, um resultado **negativo e limpo**, sem precisar de ajuste extra).


