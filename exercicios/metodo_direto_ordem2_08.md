<h1>Método Direto de Lyapunov - Equações de 2ª Ordem - 08</h1>

<img width="600" alt="image" src="https://github.com/user-attachments/assets/5ab4d77c-8c4d-4d1d-9888-8bf881e45c8e" />

#### Sistema: $\dot x_1=-x_1+x_2^3,\quad \dot x_2=-x_1-x_2$

#### Candidata: $V(x_1,x_2)=ax_1^2+bx_2^4$

## Passo 1 — Verificar se a candidata de Lyapunov é positiva definida

Para $V>0$ (fora da origem), precisamos de $a>0$ e $b>0$ (soma de potências pares com coeficientes positivos).

## Passo 2 — Calcular $\dot V$

$$\dot V=\frac{\partial V}{\partial x_1}\dot x_1+\frac{\partial V}{\partial x_2}\dot x_2=2ax_1\dot x_1+4bx_2^3\dot x_2$$

Substituindo:
$$\dot V=2ax_1(-x_1+x_2^3)+4bx_2^3(-x_1-x_2)$$

$$=-2ax_1^2+2ax_1x_2^3-4bx_1x_2^3-4bx_2^4$$

## Passo 3 — Agrupar o termo "problemático" ($x_1x_2^3$)

$$\dot V=-2ax_1^2+(2a-4b)x_1x_2^3-4bx_2^4$$

Esse termo cruzado $x_1x_2^3$ **não tem sinal controlado** (pode ser positivo ou negativo, dependendo dos sinais de $x_1$ e $x_2$) — exatamente o mesmo tipo de problema que enfrentamos no item 5(b)! A solução é **escolher $a$ e $b$ de forma que esse termo se cancele**.

## Passo 4 — Impor o cancelamento

$$2a-4b=0 \;\Rightarrow\; a=2b$$

Com essa escolha, o termo cruzado desaparece:

$$\dot V=-2ax_1^2-4bx_2^4$$

## Passo 5 — Analisar o sinal final

Com $a=2b$ e $b>0$ (o que garante $a=2b>0$ também):

$$\dot V=-2ax_1^2-4bx_2^4\le0$$

Como $a>0$ e $b>0$: $\dot V<0$ **estritamente** para todo $(x_1,x_2)\ne(0,0)$ (a soma de dois termos negativos só se anula quando ambos são zero, ou seja, $x_1=0$ e $x_2=0$).

## Conclusão

$$\boxed{a=2b, \quad \text{com } b>0 \text{ (e, portanto, } a>0\text{)}}$$

Com essa relação entre $a$ e $b$:
- $V>0$ para $(x_1,x_2)\ne(0,0)$, radialmente ilimitada ✓
- $\dot V<0$ para $(x_1,x_2)\ne(0,0)$ ✓

**O sistema é globalmente assintoticamente estável**, para qualquer $a=2b$ com $b>0$ (por exemplo, $a=2,b=1$; ou $a=4,b=2$; etc — qualquer par nessa proporção).


---

<a href="metodo_direto_proposito.md">Como aplicar o Método Direto de Lyapunov</a>

$$\boxed{\text{Escolher } V \text{ (guiado pela estrutura do sistema)} \to \text{Verificar } V>0 \to \text{Calcular } \dot V \to}$$

$$\boxed{\to \text{Ajustar pesos se necessário} \to \text{Analisar sinal} \to \text{Concluir (LaSalle se preciso)}}$$

