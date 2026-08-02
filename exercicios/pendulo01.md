<h1>Pêndulo com amortecimento</h1>

O pêndulo num campo gravitacional, sujeito a um amortecimento linear é mostrado abaixo, onde θ é o deslocamento angular do pêndulo em relação ao eixo vertical que passa pelo ponto O;
$mL^2$ é o momento de inércia da massa m; c é a constante de amortecimento; g é a aceleração da gravidade. Introduzindo as variáveis de estado:
```math
x_1 = θ
```
```math
x_2 = \frac{dθ}{dt}
```

obtemos:
```math
\frac{dx_1}{dt} = x_2
```
```math
\frac{dx_2}{dt} = -\frac{g}{L}sen(x_1)-\frac{c}{mL}x_2
```

<img width="466" height="481" alt="image" src="https://github.com/user-attachments/assets/9dcc6653-ad37-4c98-9865-e9eb7f69b074" />

Analise a estabilidade para:

(a) $V(\mathbf x)=\dfrac12mL^2x_2^2+mgL(1-\cos x_1)$

(b) $V(\mathbf x)=\dfrac12x_2^2+\dfrac{b^2}{2}\left(x_1+\dfrac{x_2}{b}\right)^2+2a(1-\cos x_1)$, com $a=g/L,\ b=c/(mL)$


## Contexto do sistema

$$x_1=\theta, \qquad x_2=\dot\theta$$

$$\dot x_1=x_2, \qquad \dot x_2=-\frac{g}{L}\text{sen}(x_1)-\frac{c}{mL}x_2$$

##(a): $V(\mathbf x)=\dfrac12mL^2x_2^2+mgL(1-\cos x_1)$

## Passo 1 — Verificar positividade

- $\dfrac12mL^2x_2^2$ = energia cinética, sempre $\ge0$, zero só quando $x_2=0$
- $mgL(1-\cos x_1)$ = energia potencial, $\ge0$ (pois $\cos x_1\le1$), zero apenas em $x_1=0$ (localmente)

$V\ge0$, com $V=0$ apenas em $(0,0)$ → **positiva definida (localmente)**

## Passo 2 — Calcular $\dot V$

$$\dot V=mL^2x_2\dot x_2+mgL\,\text{sen}(x_1)\dot x_1$$

Substituindo:
$$\dot V=mL^2x_2\left(-\frac{g}{L}\text{sen}(x_1)-\frac{c}{mL}x_2\right)+mgL\,\text{sen}(x_1)\cdot x_2$$

$$=-mgLx_2\,\text{sen}(x_1)-cLx_2^2+mgLx_2\,\text{sen}(x_1)$$

Os dois primeiros/últimos termos se cancelam:

$$\dot V=-cLx_2^2$$

## Passo 3 — Analisar o sinal

$$\dot V=-cLx_2^2\le0 \quad (\text{pois } c,L>0)$$

Mas $\dot V=0$ **sempre que $x_2=0$**, independente de $x_1$ — apenas **semi-definida**.

## Passo 4 — Aplicar LaSalle

Se $x_2\equiv0$, então $\dot x_2\equiv0$ também, exigindo $\text{sen}(x_1)=0 \Rightarrow x_1=0$ (localmente). Único conjunto invariante: $(0,0)$.

**Conclusão: $(0,0)$ é localmente assintoticamente estável** ✓

---

##(b): $V(\mathbf x)=\dfrac12x_2^2+\dfrac{b^2}{2}\left(x_1+\dfrac{x_2}{b}\right)^2+2a(1-\cos x_1)$, com $a=g/L,\ b=c/(mL)$

## Passo 1 — Interpretação: três termos, dois físicos e um "artifício matemático"

- $\dfrac12x_2^2$: energia cinética (física)
- $2a(1-\cos x_1)$: energia potencial (física)
- $\dfrac{b^2}{2}\left(x_1+\dfrac{x_2}{b}\right)^2$: **termo cruzado artificial**, sem significado físico — adicionado propositalmente para gerar cancelamentos melhores

## Passo 2 — Calcular $\dot V$ (usando $w=x_1+x_2/b$)

Após o cálculo completo (regra da cadeia, substituindo o sistema, com vários cancelamentos):

$$\dot V=-b\left(x_2^2+a\,x_1\,\text{sen}(x_1)\right)$$

## Passo 3 — Analisar o sinal

Na região $|x_1|<\pi$: $x_1$ e $\text{sen}(x_1)$ têm **sempre o mesmo sinal**, então $x_1\,\text{sen}(x_1)>0$ para $x_1\ne0$.

$$x_2^2+ax_1\,\text{sen}(x_1)>0 \quad \text{para } (x_1,x_2)\ne(0,0),\ |x_1|<\pi$$

Como $a,b>0$:
$$\dot V<0 \quad \text{estritamente, para } (x_1,x_2)\ne(0,0), \text{ dentro de } |x_1|<\pi$$

## Passo 4 — Classificar

Diferente do item (a), aqui $\dot V$ já é **estritamente negativa** — **não precisamos do LaSalle**.

**Conclusão: $(0,0)$ é localmente assintoticamente estável** ✓

---

## Por que ambos os itens são apenas "locais" (nunca globais)

$$\boxed{\text{O pêndulo tem MÚLTIPLOS equilíbrios: } (0,0), (\pi,0), (2\pi,0), \dots}$$

Fisicamente, $(\pi,0)$ representa o pêndulo "de cabeça para cima" (equilíbrio instável, mas existente). Como há mais de um ponto de equilíbrio competindo pelo espaço, a conclusão **nunca pode ser global** — cada análise vale apenas numa vizinhança da origem (reforçado, no item b, pela restrição explícita $|x_1|<\pi$).

## Comparando os dois itens

| | Item (a) | Item (b) |
|---|---|---|
| Candidata | Energia física pura | Energia + termo cruzado artificial |
| $\dot V$ | $-cLx_2^2$ (semi-definida) | $-b(x_2^2+ax_1\text{sen}(x_1))$ (estrita) |
| Precisa de LaSalle? | Sim | Não |
| Conclusão | Localmente assint. estável | Localmente assint. estável |

