<h1>Método Direto de Lyapunov - Equações de 2ª Ordem - 05</h1>

Usando funções de Lyapunov, investigar a estabilidade do seguinte sistema:

```math
\dot x=-\dfrac12x^3+2xy^2
```
```math
\dot y=-y^3
```

## Requisito 1 — Ponto(s) de equilíbrio

Verificando: $\dot x=0$ e $\dot y=0$ simultaneamente.

Da segunda equação: $-y^3=0 \Rightarrow y=0$

Substituindo na primeira: $-\dfrac12x^3+2x(0)^2=-\dfrac12x^3=0 \Rightarrow x=0$

**Único ponto de equilíbrio: $(0,0)$** ✓ — abre espaço para conclusão global

## Requisito 2 — Candidata $V$ radialmente ilimitada

Usualmente $V=x^2+y^2$ é uma candidata, mas ela falha, apesar de ser positiva definida, quando analisamos os sinais de $\dot V$ .

Ajustamos então $V=x^2+2y^2$ .

Verificando radialmente ilimitada: como $x^2\to\infty$ conforme $|x|\to\infty$ e $2y^2\to\infty$ conforme $|y|\to\infty$, a soma $V=x^2+2y^2\to\infty$ conforme $\|(x,y)\|\to\infty$, em **qualquer** direção — ✓ radialmente ilimitada (soma de potências pares com coeficientes positivos)

## Requisito 3 — $\dot V$ negativo (ou semi-definido) em **todo** o espaço

Calculamos:
$$\dot V=-(x^2-2y^2)^2\le0$$

Válido para **todo** $(x,y)$ — sem nenhuma restrição de região! ✓

## Requisito 4 — Como $\dot V$ é só semi-definida, aplicamos LaSalle

Verificamos que o único conjunto invariante em $\{\dot V=0\}=\{x^2=2y^2\}$ é a própria origem (porque, se a trajetória tentasse ficar presa nessa reta, teríamos $\dot y=-y^3$, que só é zero em $y=0$, forçando também $x=0$).

**Confirmado: assintoticamente estável, via LaSalle** ✓

## Juntando tudo — confirmando "globalmente"

$$\boxed{\text{Único equilíbrio} + V \text{ radialmente ilimitada} + \dot V\le0 \text{ em TODO o espaço} + \text{LaSalle válido globalmente} \;\Rightarrow\; \textbf{GLOBALMENTE assintoticamente estável}}$$

Todos os quatro requisitos necessários se confirmaram, **e** — importante notar — a análise de LaSalle também foi feita **sem restrição de região** (o argumento "$\dot y=-y^3=0$ só em $y=0$" vale para qualquer $y$, não só perto da origem), então o resgate via LaSalle também se estende globalmente.



---

$$\boxed{\text{Escolher } V \text{ (guiado pela estrutura do sistema)} \to \text{Verificar } V>0 \to \text{Calcular } \dot V \to \text{Ajustar pesos se necessário} \to \text{Analisar sinal} \to \text{Concluir (LaSalle se preciso)}}$$

<a href="metodo_direto_proposito.md">Como aplicar o Método Direto de Lyapunov</a>
