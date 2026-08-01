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

## Resumo em uma frase

$$\boxed{\text{Escolher } V \text{ (guiado pela estrutura do sistema)} \to \text{Verificar } V>0 \to \text{Calcular } \dot V \to \text{Ajustar pesos se necessário} \to \text{Analisar sinal} \to \text{Concluir (LaSalle se preciso)}}$$


