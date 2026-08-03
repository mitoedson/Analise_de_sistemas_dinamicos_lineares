<h1>Massa–Mola com rigidez não linear</h1>

Considere o sistema mecânico não linear
```math
\ddot x + c\dot x + kx + αx^3 = 0
```

com c > 0, k > 0, α > 0.

Na forma de estados:

```math
\dot x = y, \dot y = cy - kx - αx^3
```

Prove, usando uma função de energia, que a origem é globalmente assintoticamente estável.

## 1. Construindo a função de energia

Fisicamente, a energia total do sistema massa-mola é:

Energia cinética: 

$$E_c=\frac{1}{2}y^2$$

A força restauradora é:

$$f(x)= kx+\alpha x^3$$

A parte potencial vem de integrar a força restauradora $kx+\alpha x^3$ em relação a $x$:

$$E_p = \int_0^x (k\sigma+\alpha \sigma^3)d\sigma = \frac{1}{2}kx^2+\frac{1}{4}\alpha x^4$$

A escolha de V é:

$$V(x,y) = \underbrace{\frac{1}{2}y^2}_{\text{energia cinética}} + \underbrace{\frac{1}{2}kx^2 + \frac{1}{4}\alpha x^4}_{\text{energia potencial}}$$


## 2. Verificando que V é positiva definida

Como $k>0$ e $\alpha>0$, cada termo de $V$ é não-negativo, e só se anula simultaneamente quando $x=0$ **e** $y=0$. Logo:

$$V(x,y) = \frac{1}{2}y^2 + \frac{1}{2}kx^2+\frac{1}{4}\alpha x^4> 0 \ \text{ para } (x,y)\neq(0,0), \qquad V(0,0)=0$$

V é positiva definida.

$V$ é **radialmente ilimitada** (isto é, $V\to\infty$ conforme $\|(x,y)\|\to\infty$, em qualquer direção) — o termo $x^4$ garante isso mesmo quando $x\to\infty$ com $y$ fixo. Essa propriedade será essencial para a conclusão **global**.

## 3. Calculando $\dot V$ ao longo das trajetórias

Usando a regra da cadeia e substituindo $\dot x=y$, $\dot y=-cy-kx-\alpha x^3$:

$$\dot V = y\dot y + kx\dot x+\alpha x^3\dot x = y(-cy-kx-\alpha x^3) + kxy+\alpha x^3y$$

$$= -cy^2 -kxy-\alpha x^3y+kxy+\alpha x^3y$$

Os termos cruzados ($-kxy$ com $+kxy$, e $-\alpha x^3y$ com $+\alpha x^3y$) se cancelam perfeitamente:

$$\boxed{\dot V = -cy^2}$$

## 4. O problema: $\dot V$ é só semi-definida negativa

Aqui está a sutileza que torna esse exemplo diferente dos anteriores: como $c>0$, temos $\dot V\leq 0$ sempre — **mas** $\dot V=0$ não só na origem, e sim em **toda a reta** $y=0$ (para qualquer $x$). Isso significa que **o teorema clássico de Lyapunov não é suficiente** aqui (ele exige $\dot V<0$ estritamente fora da origem).

## 5. Aplicando o Princípio de Invariância de LaSalle

Esse teorema resolve exatamente esse tipo de situação. Ele diz: se $\dot V\leq0$ (não precisa ser estrito) e $V$ é radialmente ilimitada, então toda trajetória converge para o **maior conjunto invariante** contido em

$$E = \{(x,y) : \dot V(x,y)=0\} = \{(x,y):y=0\}$$

**Passo chave:** precisamos achar o maior conjunto invariante *dentro* de $E$ — ou seja, quais pontos com $y=0$ permanecem com $y=0$ **para sempre**, seguindo a dinâmica do sistema.

Se $y(t)\equiv 0$ para todo $t$, então necessariamente $\dot y = 0$ também. Substituindo $y=0$ na equação de $\dot y$:

$$\dot y = -c(0)-kx-\alpha x^3 = 0 \implies -x(k+\alpha x^2)=0$$

Como $k>0$ e $\alpha>0$, temos $k+\alpha x^2>0$ para **qualquer** $x$ real (nunca zera) — então a única solução é:

$$x=0$$

## 6. Conclusão

O maior conjunto invariante dentro de $E$ é **só a origem**: $\{(0,0)\}$.

Pelo Princípio de Invariância de LaSalle, toda trajetória do sistema converge para esse conjunto invariante — ou seja, converge para $(0,0)$. Como isso vale para **qualquer** condição inicial (usamos a radial ilimitação de $V$ para garantir isso globalmente), concluímos:

$$\text{A origem é globalmente assintoticamente estável.}$$

---

**Por que esse exemplo é pedagogicamente importante:** ele mostra a diferença entre Lyapunov "puro" (exige $\dot V<0$ estrito) e LaSalle (permite $\dot V\leq0$, desde que se analise cuidadosamente onde a igualdade ocorre). Fisicamente, faz todo sentido: o amortecedor ($-cy$) só dissipa energia quando há velocidade ($y\neq0$); quando $y=0$ momentaneamente mas $x\neq0$, a mola ainda "empurra" o sistema, então ele não fica parado ali — e é exatamente esse argumento que a análise do conjunto invariante captura formalmente.



