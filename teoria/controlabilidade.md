<h1>Controlabilidade e Observabilidade</h1>
Conceitos fundamentais de controlabilidade e observabilidade em sistemas dinâmicos lineares, introduzidos por Kalman. Estes conceitos são essenciais para o projeto de sistemas de controle no espaço de estados, pois indicam se existe uma solução completa para o problema de projeto.

## 1. Independência Linear de Vetores
Antes de entrar nos critérios de controle, o material revisa o conceito de **vetores linearmente independentes**. Um conjunto de vetores é independente se nenhum deles puder ser expresso como uma combinação linear dos outros, o que é um pré-requisito matemático para os testes de posto das matrizes de controlabilidade e observabilidade.

## 2. Controlabilidade
Um sistema é dito controlável se for possível levá-lo de qualquer estado inicial para qualquer outro estado final em tempo finito, utilizando um sinal de controle não limitado.
*   **Controlabilidade de Estado:** É verificada através da **matriz de controlabilidade** $[B \ | \ AB \ | \ \dots \ | \ A^{n-1}B]$. O sistema é completamente controlável se esta matriz tiver **posto $n$** (ordem do sistema).
*   **Controlabilidade de Saída:** Foca na capacidade de controlar a resposta $y(t)$ do sistema. É garantida se a matriz $[CB \ | \ CAB \ | \ \dots \ | \ CA^{n-1}B \ | \ D]$ tiver **posto $m$** (número de saídas).
*   **Estabilizabilidade:** Um sistema não totalmente controlável é estabilizável se os seus **modos instáveis forem controláveis** e os modos não controláveis forem naturalmente estáveis.

## 3. Observabilidade
A **observabilidade** é um conceito fundamental na teoria de controle no espaço de estados, introduzido por Rudolf Kalman, que determina se o comportamento interno de um sistema pode ser conhecido a partir de suas saídas medidas.

### 3.1. Definição e Relevância
Um sistema é considerado completamente observável no instante $t_0$ se for possível determinar unicamente o estado inicial $x(t_0)$ através da observação da saída $y(t)$ e do conhecimento da entrada $u(t)$ durante um intervalo de tempo finito.

Na engenharia, a observabilidade é crucial porque muitas variáveis de estado não podem ser medidas diretamente por sensores físicos devido a limitações técnicas ou custos proibitivos. Se o sistema for observável, essas variáveis podem ser reconstruídas matematicamente através de **estimadores ou observadores de estado**.

### 3.2. Critério Matemático (Matriz de Observabilidade)

Para um sistema linear invariante no tempo (LIT) com $n$ estados, a observabilidade é verificada através da **matriz de observabilidade** ($\mathcal{O}$), definida como:

$$ \mathcal{O} = \begin{bmatrix} C \\ CA \\ CA^2 \\ \vdots \\ CA^{n-1} \end{bmatrix} $$

*   **Condição de Rank:** O sistema é completamente observável se, e somente se, a matriz $\mathcal{O}$ possuir **posto pleno $n$** (ou seja, seu determinante deve ser diferente de zero para sistemas de única saída).
*   **Significado Físico:** A falha neste teste (posto $< n$) indica que existem subsistemas ou "modos" que estão fisicamente desconectados da saída, tornando impossível deduzir a energia armazenada nesses componentes apenas olhando para o que o sistema "mostra" externamente.

### 3.3. Dualidade e Transformações
*   **Dualidade com a Controlabilidade:** Existe uma equivalência matemática entre os problemas de controle e estimação. O problema de projetar um ganho de estimador $L$ para uma planta $(F, H)$ é o dual de projetar um ganho de controle $K$ para uma planta $(F^T, H^T)$.
*   **Forma Canônica Observável:** Se um sistema é observável, ele sempre pode ser transformado em uma estrutura específica onde os coeficientes do polinômio característico aparecem diretamente na matriz de estados, facilitando o projeto de estimadores.
*   **Invariância:** Assim como a controlabilidade, a observabilidade é uma propriedade intrínseca do estado do sistema e não muda sob transformações lineares não singulares (mudança de coordenadas).

### 3.4. Relação com a Função de Transferência
Diferente da descrição externa (função de transferência), a observabilidade analisa a estrutura interna do sistema. No entanto, elas se conectam através dos polos e zeros:
*   **Cancelamento Polo-Zero:** Um sistema perde a observabilidade (ou a controlabilidade) se houver cancelamentos de polos e zeros na sua função de transferência.
*   **Realização Mínima:** Um modelo de espaço de estados é uma "realização mínima" de uma função de transferência se for, simultaneamente, completamente controlável e observável.

### 3.5. Detectabilidade
Quando um sistema não é completamente observável, ele ainda pode ser útil se for **detectável**. Isso ocorre se todos os modos não observáveis forem **estáveis** (ou seja, seus componentes internos tendem naturalmente a zero com o tempo), permitindo que apenas os modos instáveis ou de interesse precisem ser controlados ou monitorados.
