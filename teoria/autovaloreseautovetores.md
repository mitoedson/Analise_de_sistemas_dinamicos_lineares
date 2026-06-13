<h1>Autovalores e Autovetores</h1>

## 1. Introdução e Motivação
Em sistemas dinâmicos lineares representados por equações de estado da forma $\dot{X} = AX$, os **autovalores** e **autovetores** são ferramentas fundamentais para entender o comportamento do sistema sem necessariamente resolver as equações diferenciais por integração direta.
*   **Autovalores ($\lambda$):** Determinam a **estabilidade** do sistema e a taxa de decaimento ou crescimento da resposta.
*   **Autovetores ($K$):** Definem a **geometria** da resposta, indicando as direções preferenciais (modos naturais) no espaço de estados.

## 2. Fundamentação Matemática
Para um sistema homogêneo $\dot{X} = AX$, procuramos uma solução na forma exponencial $X = Ke^{\lambda t}$. Ao derivar essa expressão e substituir na equação original, chegamos à identidade:
$$AK e^{\lambda t} = \lambda K e^{\lambda t} \implies (A - \lambda I)K = 0$$
Esta é a equação fundamental do problema de autovalor/autovetor.

### 2.1. Como obter os Autovalores
Os autovalores são as raízes da **equação característica**, obtida pelo determinante:
$$\det(A - \lambda I) = 0$$
Para um sistema de dimensão 2 ($2 \times 2$), a equação resulta em um polinômio de segundo grau:
$$\lambda^2 - (a_{11} + a_{22})\lambda + (a_{11}a_{22} - a_{12}a_{21}) = 0$$.

### 2.2. Como obter os Autovetores
Uma vez encontrado um autovalor $\lambda_i$, substituímos seu valor de volta na equação $(A - \lambda_i I)K = 0$ para encontrar o vetor não nulo $K_i$ correspondente.

## 3. Classificação de Soluções (Casos para Sistemas de 2ª Ordem)
O comportamento do sistema depende da natureza das raízes da equação característica:

1.  **Raízes Reais e Distintas ($\lambda_1 \neq \lambda_2$):** A solução geral é uma combinação linear:
    $X(t) = c_1 K_1 e^{\lambda_1 t} + c_2 K_2 e^{\lambda_2 t}$.
2.  **Raízes Reais Repetidas ($\lambda_1 = \lambda_2$):** Se houver apenas um autovetor independente, a segunda solução assume a forma $X_2 = Kte^{\lambda t} + Pe^{\lambda t}$, onde o vetor $P$ é encontrado por $(A - \lambda I)P = K$.
3.  **Raízes Complexas Conjugadas ($\lambda = \sigma \pm j\omega$):** As soluções envolvem termos de seno e cosseno multiplicados por uma exponencial $e^{\sigma t}$, descrevendo comportamentos oscilatórios.

## 4. Análise de Estabilidade e Retrato de Fase
A estabilidade de um ponto de equilíbrio (geralmente a origem) é estabelecida pelo sinal da parte real dos autovalores:
*   **Assintoticamente Estável:** Se **todos** os autovalores têm parte real negativa ($\text{Re}\{\lambda_i\} < 0$).
*   **Instável:** Se **pelo menos um** autovalor tem parte real positiva ($\text{Re}\{\lambda_i\} > 0$).

**Classificação Visual (Retrato de Fase):**
*   **Nó:** Autovalores reais de mesmo sinal.
*   **Sela:** Autovalores reais com sinais opostos (sempre instável).
*   **Foco:** Autovalores complexos com parte real não nula.
*   **Centro:** Autovalores puramente imaginários (estabilidade marginal).

## 5. Ferramentas Computacionais
Em softwares como **MATLAB** ou **Octave**, a extração é simplificada pelo comando:
*   `p = eig(A)`: Retorna apenas os autovalores.
*   `[V, D] = eig(A)`: Retorna os autovetores nas colunas de `V` e os autovalores na diagonal de `D`.

---
## Exemplo Prático de Fixação
Considere o sistema: $\frac{dx}{dt} = 2x + 3y$ e $\frac{dy}{dt} = 2x + y$.
<p><br>
**Matriz:**
<p>
$$A = \begin{bmatrix} 2 & 3 \\ 2 & 1 \end{bmatrix}$$
<p>
**Autovalores:** Resolvendo $\det(A-\lambda I)=0$, obtemos $\lambda_1 = -1$ (estável) e $\lambda_2 = 4$ (instável). O sistema total é 
<b>instável</b>.
<p>
**Autovetores:** Para $\lambda_1 = -1$, o autovetor é 
<p>
$$K_1 = \begin{bmatrix} 1 \\ -1 \end{bmatrix}$$
<p>Para $\lambda_2 = 4$, o autovetor é:
<p>
$$K_2 = \begin{bmatrix} 3 \\ 2\end{bmatrix}$$
<p><br>
<a href="/exercicios/autovaloreseautovetores01.md">Ver exercícios 01</a>
<a href="/exercicios/autovaloreseautovetores01.md">Ver exercícios 02</a>
<a href="/exercicios/autovaloreseautovetores01.md">Ver exercícios 03</a>



