<h1>Método Direto de Lyapunov - Equações de 2ª Ordem - 07</h1>

Usando funções de Lyapunov, investigar a estabilidade do seguinte sistema:

$\dot x=x^3-y^3,\quad \dot y=2xy^2+4x^2y+2y^3$

## Passo 1 — Ponto de equilíbrio

Verificando a origem: $\dot x(0,0)=0$, $\dot y(0,0)=0$ ✓ → **$(0,0)$ é ponto de equilíbrio**

(Não vamos nos aprofundar em achar outros pontos, porque, como veremos, a estratégia de resolução aqui é diferente — vamos direto tentar provar **instabilidade**, seguindo o gabarito.)

## Passo 2 — Por que a estratégia aqui é diferente dos itens anteriores

Repare que, diferente dos itens (a), (b), (c) — todos "assintoticamente estável" ou "estável" — o **gabarito deste item afirma "instável"**. Isso significa que, em vez de buscar uma candidata $V$ que prove $\dot V\le0$, a estratégia é **mostrar diretamente** que as trajetórias se afastam da origem em alguma direção específica — não precisamos necessariamente de uma função de Lyapunov completa para isso.

## Passo 3 — Analisando o sistema restrito ao eixo $y=0$

A técnica aqui é examinar o comportamento do sistema **sobre um eixo específico**, para ver se ele "empurra" as trajetórias para longe da origem.

**Substituindo $y=0$ nas duas equações:**

$$\dot x\Big|_{y=0}=x^3-0^3=x^3$$

$$\dot y\Big|_{y=0}=2x(0)^2+4x^2(0)+2(0)^3=0$$

## Passo 4 — Interpretando esse resultado

No eixo $y=0$, o sistema se reduz a:
$$\dot x=x^3, \qquad \dot y=0$$

Ou seja: **sobre o eixo $y=0$, o sistema fica "preso" nesse eixo** (já que $\dot y=0$ ali), e a dinâmica de $x$ sozinha é:

$$\dot x=x^3$$

## Passo 5 — Analisando essa dinâmica escalar restrita

Para $x_0>0$ pequeno (próximo da origem, mas positivo): $\dot x=x^3>0$ → **$x$ está crescendo**, afastando-se da origem, permanecendo sempre em $y=0$

Para $x_0<0$ pequeno: $\dot x=x^3<0$ → **$x$ está decrescendo** (ficando mais negativo), também se afastando da origem

## Passo 6 — Conclusão sobre instabilidade

$$\boxed{\text{Existem trajetórias, começando ARBITRARIAMENTE PERTO da origem (sobre o eixo } y=0\text{), que se AFASTAM da origem}}$$

Isso é **exatamente** a definição de instabilidade: não importa quão pequeno você escolha um raio $\epsilon$ ao redor da origem, sempre existe uma condição inicial dentro desse raio (por exemplo, $x_0=\epsilon/2, y_0=0$) cuja trajetória **eventualmente sai** dessa vizinhança.

## Conclusão final

**A origem é instável**: *"No eixo y=0, o sistema vira $\dot x=x^3$, $\dot y=0$, e soluções com $x_0>0$ pequeno se afastam da origem. Logo: instável."*

---

## Por que essa abordagem foi diferente das anteriores (sem usar $V$ diretamente)

Esse item ilustra uma técnica alternativa dentro do Método Direto de Lyapunov: em vez de construir uma função $V$ completa, às vezes é mais direto **encontrar uma direção/subespaço específico** (aqui, o eixo $y=0$) onde o comportamento do sistema já revela claramente a instabilidade — evitando o trabalho de montar e testar candidatas $V$ que, de qualquer forma, não serviriam para provar instabilidade da forma usual (lembra que $\dot V>0$ só perto da origem já basta para instabilidade, mas encontrar isso diretamente através de uma "restrição de eixo" é frequentemente mais simples).

Isso também se conecta com o **Teorema de Chetaev** (uma variante do método de Lyapunov especificamente desenhada para provar instabilidade), embora aqui tenhamos usado uma versão mais informal e direta desse tipo de raciocínio.


---

$$\boxed{\text{Escolher } V \text{ (guiado pela estrutura do sistema)} \to \text{Verificar } V>0 \to \text{Calcular } \dot V \to \text{Ajustar pesos se necessário} \to \text{Analisar sinal} \to \text{Concluir (LaSalle se preciso)}}$$

<a href="metodo_direto_proposito.md">Como aplicar o Método Direto de Lyapunov</a>
