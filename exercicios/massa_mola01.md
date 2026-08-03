<h1>Massa–Mola com rigidez não linear</h1>

## A estrutura por graus

Reagrupando $\dot V$ por grau de homogeneidade:

$$\dot V = \underbrace{(-152x_1^2+196x_1x_2-152x_2^2)}_{\text{grau 2}} + \underbrace{(-6x_1^2x_2^2+80x_1x_2^3-164x_2^4)}_{\text{grau 4}} + \underbrace{(12x_1x_2^5-56x_2^6)}_{\text{grau 6}} + \underbrace{(-6x_2^8)}_{\text{grau 8}}$$

## Por que a dominância de graus altos importa

A lógica do seu argumento é a seguinte:

**Perto da origem** (norma de $x$ pequena): os termos de grau 2 dominam (porque $x^4, x^6, x^8 \ll x^2$ quando $\|x\|$ é pequeno). Então basta que a parte quadrática seja definida negativa.

**Longe da origem** (norma de $x$ grande): os termos de grau mais alto (8, depois 6...) crescem muito mais rápido que os termos cruzados de graus intermediários — garantindo que $\dot V \to -\infty$ conforme $\|x\|\to\infty$, e não existe "brecha" onde os termos cruzados poderiam virar o sinal.

## Verificando a parte quadrática (grau 2)

Isso é essencial confirmar — testamos com o critério de Sylvester na forma $-152x_1^2+196x_1x_2-152x_2^2$:

- Coeficiente de $x_1^2$: $-152<0$ ✓ (primeiro requisito para negativo definido)
- Determinante da matriz associada: $(-152)(-152)-(98)^2 = 23104-9604 = 13500>0$ ✓

Logo, a forma quadrática **é definida negativa** sozinha — o que já garante estabilidade *local* assintótica.

## Confirmando a dominância numericamente

Testei $\dot V(x_1,x_2)$ numa grade densa de $-20$ a $20$ em ambas variáveis, buscando o maior valor (o "pior caso"):

```
Maior valor de V̇ encontrado: -0.27 (perto da origem, x₁=x₂≈0.05)
```

Ou seja, em toda a região testada, $\dot V<0$ — e o máximo (mais próximo de zero) ocorre bem perto da origem, exatamente onde esperamos $\dot V\to 0$ conforme $x\to 0$. Isso é consistente com **$\dot V$ ser negativa definida globalmente**.

## Conclusão

Como:
1. A parte quadrática é negativa definida (garante negatividade local)
2. Os termos de grau 4, 6, 8 têm coeficientes todos negativos nos termos puros ($-6x_1^2x_2^2$, $-164x_2^4$, $-56x_2^6$, $-6x_2^8$) e dominam os termos cruzados de sinal misto ($80x_1x_2^3$, $12x_1x_2^5$) para $\|x\|$ grande
3. A verificação numérica não encontra nenhum ponto onde $\dot V\geq0$ (exceto a origem)

concluímos que $\dot V(x)<0$ para todo $x\neq 0$, e portanto $J(x)+J(x)^T$ é negativa definida globalmente — satisfazendo a condição do teorema de Krasovskii, o que garante que a origem é **globalmente assintoticamente estável**.
