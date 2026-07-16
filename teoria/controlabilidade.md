<h1>Controlabilidade e Observabilidade</h1>
Conceitos fundamentais de controlabilidade e observabilidade em sistemas dinâmicos lineares, introduzidos por Kalman. Estes conceitos são essenciais para o projeto de sistemas de controle no espaço de estados, pois indicam se existe uma solução completa para o problema de projeto.

## 1. Independência Linear de Vetores
Antes de entrar nos critérios de controle, o material revisa o conceito de **vetores linearmente independentes**. Um conjunto de vetores é independente se nenhum deles puder ser expresso como uma combinação linear dos outros, o que é um pré-requisito matemático para os testes de posto das matrizes de controlabilidade e observabilidade.

## 2. Controlabilidade
A **controlabilidade**, introduzida por Rudolf Kalman, é um pilar fundamental da teoria de controle moderna que determina se é possível manipular o comportamento interno de um sistema dinâmico por meio de suas entradas.

### 2.1. Definições de Controlabilidade
*   **Controlabilidade de Estado:** Um sistema é considerado controlável no instante $t_0$ se for possível transferi-lo de **qualquer estado inicial** $x(t_0)$ para qualquer outro estado desejado em um intervalo de tempo finito, utilizando um vetor de controle não limitado.
*   **Controlabilidade de Saída:** Foca na capacidade de levar a **saída** $y(t)$ de qualquer valor inicial para qualquer valor final em tempo finito. A controlabilidade completa de estado não é necessária nem suficiente para garantir a controlabilidade de saída.
*   **Significado Físico:** Um sistema não controlável possui subsistemas ou "modos" que estão **fisicamente desconectados da entrada**, tornando impossível influenciar certas variáveis internas através dos sinais de comando.

### 2.2. Critérios Matemáticos (Matriz de Controlabilidade)
Para um sistema linear invariante no tempo (LIT) $\dot{x} = Ax + Bu$ de ordem $n$, a propriedade é verificada através da matriz de controlabilidade ($\mathcal{C}$):
$C = [B \ | \ AB \ | \ A^2B \ | \ \dots \ | \ A^{n-1}B]$
*   **Condição de Posto (Rank):** O sistema é completamente controlável de estado se, e somente se, a matriz $\mathcal{C}$ possuir **posto pleno $n$**. Isso exige que os vetores que compõem a matriz sejam linearmente independentes.
*   **Teste para Saída:** Para a saída, a matriz $[CB \ | \ CAB \ | \ \dots \ | \ CA^{n-1}B \ | \ D]$ deve ter posto $m$ (dimensão da saída).

### 2.3. Relação com Funções de Transferência
A controlabilidade está intrinsecamente ligada à estrutura interna do modelo:
*   **Cancelamento de Polo e Zero:** Se houver um cancelamento de polo e zero na função de transferência, o sistema resultante será **incontrolável, inobservável ou ambos**. O modo cancelado torna-se desacoplado da entrada.
*   **Realização Mínima:** Um modelo no espaço de estados que não apresenta cancelamentos e é, simultaneamente, completamente controlável e observável é chamado de "realização mínima".

### 2.4. Estabilizabilidade
Quando um sistema não é totalmente controlável, ele pode ainda ser útil se for **estabilizável**. Isso ocorre se os seus modos não controláveis forem naturalmente estáveis. Nesses casos, a realimentação pode ser usada para estabilizar apenas os modos instáveis que permanecem controláveis.

### 2.5. Implicações no Projeto de Controle
*   **Alocação de Polos:** Se o sistema é controlável, os polos de malha fechada podem ser alocados em **qualquer posição arbitrária** no plano complexo por meio de realimentação de estado ($u = -Kx$).
*   **Esforço de Controle:** Embora a teoria permita alocações arbitrárias, mover os polos para longe de suas posições originais ou controlar sistemas com **controlabilidade fraca** (modos pouco acoplados à entrada) exige ganhos muito elevados e grande esforço dos atuadores.
*   **Fórmulas de Projeto:** Ferramentas como a **Fórmula de Ackermann** (`acker` no MATLAB) ou o algoritmo `place` são usadas para calcular a matriz de ganho $K$ necessária para a alocação desejada.

### 2.6. Propriedades Teóricas Adicionais
*   **Invariância:** A controlabilidade é uma propriedade intrínseca do estado; uma transformação linear não singular das variáveis (mudança de coordenadas) **não altera** a controlabilidade do sistema.
*   **Dualidade:** Existe uma equivalência matemática entre controle e estimação; o problema de alocar polos via $K$ é o dual de alocar polos do estimador via $L$.
*   **Forma Canônica:** Todo sistema controlável pode ser transformado para a **forma canônica controlável**, onde os coeficientes do polinômio característico aparecem diretamente na matriz de estados.

## 3. Observabilidade
A **observabilidade** é um conceito fundamental na teoria de controle no espaço de estados, introduzido por Rudolf Kalman, que determina se o comportamento interno de um sistema pode ser conhecido a partir de suas saídas medidas.

### 3.1. Definição e Relevância
Um sistema é considerado completamente observável no instante $t_0$ se for possível determinar unicamente o estado inicial $x(t_0)$ através da observação da saída $y(t)$ e do conhecimento da entrada $u(t)$ durante um intervalo de tempo finito.

Na engenharia, a observabilidade é crucial porque muitas variáveis de estado não podem ser medidas diretamente por sensores físicos devido a limitações técnicas ou custos proibitivos. Se o sistema for observável, essas variáveis podem ser reconstruídas matematicamente através de **estimadores ou observadores de estado**.

### 3.2. Critério Matemático (Matriz de Observabilidade)
Para um sistema linear invariante no tempo (LIT) com $n$ estados, a observabilidade é verificada através da **matriz de observabilidade** ($\mathcal{O}$), definida como: $\mathcal{O} = [ C \\ CA \\ CA^2 \\ \vdots \\ CA^{n-1} ]$

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
