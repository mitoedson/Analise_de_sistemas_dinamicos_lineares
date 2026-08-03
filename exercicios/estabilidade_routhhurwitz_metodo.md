<h1>Critério de Routh-Hurwitz - Método Geral</h1>

## Pelo critério de Routh:

Dado um polinômio característico

$$a_n s^n + a_{n-1}s^{n-1} + \dots + a_1 s + a_0 = 0$$

você monta a tabela de Routh-Hurwitz (as linhas $s^n, s^{n-1}, \dots, s^0$) e o critério diz:

- **Todos os elementos da primeira coluna devem ter o mesmo sinal** (sem mudança de sinal) para que o sistema seja estável (todas as raízes no semiplano esquerdo). CUIDADO PARA NÃO CONFUNDIR OS ELEMENTOS DA PRIMEIRA COLUNA COM RAÍZES, OU AUTOVALORES DO POLINÔMIO, POIS ELES APENAS SÃO VALORES AUXILIARES.
- **O número de mudanças de sinal na primeira coluna é igual ao número de raízes no semiplano direito** (instáveis).

Ou seja, não é só "verificar se não muda de sinal" — a contagem de trocas de sinal também te dá quantos polos instáveis existem, o que é útil mesmo quando o sistema já é sabidamente instável e você quer saber "quão instável".

**Duas condições necessárias antes de montar a tabela** (teste rápido, evita trabalho desnecessário):
1. Todos os coeficientes $a_i$ devem existir (nenhum estar ausente/zero).
2. Todos os coeficientes devem ter o mesmo sinal.

Se qualquer uma dessas falhar, o sistema já é instável e nem precisa montar a tabela completa.

**Casos especiais** (que costumam pegar todo mundo de surpresa):
- **Zero na primeira coluna** (mas não a linha inteira): substitui-se por $\epsilon \to 0^+$ e continua o cálculo, analisando o sinal no limite.
- **Linha inteira de zeros**: indica raízes simétricas em relação à origem (par imaginário puro, ou par real simétrico). Nesse caso usa-se o "polinômio auxiliar" da linha anterior, deriva-se, e substitui-se a linha de zeros pelos coeficientes da derivada.

### Montagem da tabela

Para $a_n s^n + a_{n-1}s^{n-1} + \dots + a_0$:

| $s^n$ | $a_n$ | $a_{n-2}$ | $a_{n-4}$ | ... |
|---|---|---|---|---|
| $s^{n-1}$ | $a_{n-1}$ | $a_{n-3}$ | $a_{n-5}$ | ... |
| $s^{n-2}$ | $b_1$ | $b_2$ | $b_3$ | ... |
| $s^{n-3}$ | $c_1$ | $c_2$ | ... | |
| $\vdots$ | | | | |
| $s^0$ | ... | | | |

As duas primeiras linhas vêm direto dos coeficientes (ímpares numa linha, pares na outra). A partir da terceira linha em diante, cada elemento é calculado por um determinante cruzado dividido pelo elemento da linha imediatamente acima na primeira coluna:

$$b_1 = \frac{a_{n-1}a_{n-2} - a_n a_{n-3}}{a_{n-1}}, \quad b_2 = \frac{a_{n-1}a_{n-4} - a_n a_{n-5}}{a_{n-1}}$$

e assim por diante, sempre usando as duas linhas anteriores.

Note também que o elemento correspondente a $s_0$, na primeira coluna, é SEMPRE o valor do coeficiente que multiplica por $a_0$. Como ela ocorre sempre, pode-se pular o último cálculo, ou fazer o cálculo e comprovar que todos os cálculos estão convergindo para o último resultado (ou está errado algum procedimento anterior, e por coincidência, o resultado aparece como correto no fim).

**Dica prática:** monte com bastante cuidado nas primeiras vezes — é fácil trocar sinal no determinante cruzado ($a_{n-1}a_{n-2} - a_n a_{n-3}$, não o contrário). Se quiser, me manda um polinômio de exemplo que eu monto a tabela passo a passo com você, ou se preferir eu posso te dar um exercício pra você tentar e eu confiro o resultado.

Resumindo:

$$\boxed{\text{Routh-Hurwitz é adequado e RECOMENDADO justamente para graus altos (}\ge3\text{), onde calcular raízes diretamente é impraticável ou impossível}}$$

$$\boxed{\text{Para graus baixos (1 ou 2), até dá pra usar fórmulas diretas — mas Routh também funciona, só que é "over-kill" nesses casos simples}}$$

$$\boxed{\text{Routh-Hurwitz determina APENAS: (1) estável ou não, e (2) quantas raízes têm parte real positiva (via contagem de trocas de sinal)}}$$


## Pelo critério de Hurwitz:

**Critério de Hurwitz:** monta a **matriz de Hurwitz** $H$, uma matriz $n \times n$ construída a partir dos coeficientes do polinômio, organizados assim (para $a_n s^n + a_{n-1}s^{n-1} + \dots + a_0$):

```math
H = \begin{pmatrix} a_{n-1} & a_{n-3} & a_{n-5} & \cdots \\ a_n & a_{n-2} & a_{n-4} & \cdots \\ 0 & a_{n-1} & a_{n-3} & \cdots \\ 0 & a_n & a_{n-2} & \cdots \\ \vdots & & & \ddots \end{pmatrix}
```

(cada coluna desce um índice, preenchendo com zero quando o coeficiente não existe)

O critério então diz: o sistema é estável se, e somente se, **todos os menores principais líderes** (os determinantes $\Delta_1, \Delta_2, \dots, \Delta_n$, tomados dos blocos superiores-esquerdos crescentes da matriz) forem **positivos**:

```math
\Delta_1 = a_{n-1} > 0, \quad \Delta_2 = \begin{vmatrix} a_{n-1} & a_{n-3} \\ a_n & a_{n-2} \end{vmatrix} > 0, \quad \dots, \quad \Delta_n > 0
```

### Relação com o critério de Sylvester:

## A resposta direta

$$\boxed{\text{O critério de Hurwitz USA a mesma FERRAMENTA MATEMÁTICA que o critério de Sylvester (menores principais líderes), mas NÃO SÃO O MESMO "método" no sentido histórico/nominal}}$$

**Critério de Sylvester:** é um resultado **geral de Álgebra Linear**, que serve para determinar se **qualquer** matriz simétrica $M$ é positiva definida — verificando se todos os seus menores principais líderes são positivos. Não tem nada a ver, originalmente, com polinômios ou estabilidade — é aplicável a qualquer matriz simétrica, em qualquer contexto (geometria, otimização, estatística, etc.)

**Critério de Hurwitz:** é uma aplicação **específica** dessa mesma ferramenta (menores principais), mas aplicada a uma matriz **construída de forma especial** a partir dos **coeficientes de um polinômio** — a Matriz de Hurwitz. O objetivo é bem específico: determinar estabilidade (raízes com parte real negativa).

## A conexão exata

$$\boxed{\text{Hurwitz} = \text{Sylvester APLICADO à Matriz de Hurwitz (construída a partir dos coeficientes do polinômio)}}$$

Ou seja: Hurwitz **usa** o teste de Sylvester como **ferramenta**, mas o "critério de Hurwitz" propriamente dito é o **pacote completo**: (1) construir a matriz específica a partir do polinômio, **e** (2) aplicar Sylvester nela.

## Resumindo com um quadro comparativo

| | Origem/propósito | Matriz analisada |
|---|---|---|
| **Sylvester** | Teste geral de Álgebra Linear | Qualquer matriz simétrica $M$ |
| **Hurwitz** | Estabilidade de polinômios | Matriz de Hurwitz (construída dos coeficientes $a_i$) |
| **Questão 4 (Lyapunov)** | Estabilidade de sistemas lineares | Matriz $P$ (resultado da equação de Lyapunov, para Positiva Definida) |

## A "moral" final, amarrando toda a lista

$$\boxed{\text{O teste de Sylvester (menores principais) é uma FERRAMENTA UNIVERSAL, reaproveitada em pelo menos DOIS contextos diferentes da nossa lista: Hurwitz (polinômios) e Lyapunov (matriz } P\text{)}}$$
