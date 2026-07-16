<h1>Controlabilidade e Observabilidade</h1>
Conceitos fundamentais de controlabilidade e observabilidade em sistemas dinâmicos lineares, introduzidos por Kalman. Estes conceitos são essenciais para o projeto de sistemas de controle no espaço de estados, pois indicam se existe uma solução completa para o problema de projeto.

### 1. Independência Linear de Vetores
Antes de entrar nos critérios de controle, o material revisa o conceito de **vetores linearmente independentes**. Um conjunto de vetores é independente se nenhum deles puder ser expresso como uma combinação linear dos outros, o que é um pré-requisito matemático para os testes de posto das matrizes de controlabilidade e observabilidade.

### 2. Controlabilidade
Um sistema é dito controlável se for possível levá-lo de qualquer estado inicial para qualquer outro estado final em tempo finito, utilizando um sinal de controle não limitado.
*   **Controlabilidade de Estado:** É verificada através da **matriz de controlabilidade** $[B \ | \ AB \ | \ \dots \ | \ A^{n-1}B]$. O sistema é completamente controlável se esta matriz tiver **posto $n$** (ordem do sistema).
*   **Controlabilidade de Saída:** Foca na capacidade de controlar a resposta $y(t)$ do sistema. É garantida se a matriz $[CB \ | \ CAB \ | \ \dots \ | \ CA^{n-1}B \ | \ D]$ tiver **posto $m$** (número de saídas).
*   **Estabilizabilidade:** Um sistema não totalmente controlável é estabilizável se os seus **modos instáveis forem controláveis** e os modos não controláveis forem naturalmente estáveis.

### 3. Observabilidade
A observabilidade refere-se à capacidade de determinar o estado inicial $x(t_0)$ de um sistema apenas observando sua saída $y(t)$ em um intervalo de tempo finito.
*   **Importância:** É crucial para a **estimação de variáveis de estado** que não podem ser medidas diretamente por sensores físicos.
*   **Critério:** Um sistema é completamente observável se a **matriz de observabilidade** tiver **posto $n$**.
*   **Detectabilidade:** Conceito análogo à estabilizabilidade; um sistema é detectável se os seus **modos não observáveis forem estáveis**.
