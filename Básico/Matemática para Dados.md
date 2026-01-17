
# Matemática para Dados

Considera-se implícito o conhecimento de matemática elementar.
A fim de definição, os assuntos referidos à matemática elementar são:
- Operações com números reais
- Frações, Porcentagem, Razão e Proporção
- Exponenciação, Radiciação e Logaritmo

## Conjuntos

Conjunto é uma coleção de elementos.

São matematicamente representados da forma a seguir:

$$A = \\{ a, b, c \\} ,\ \ 
B = \\{ \frac{1}{4}, 4, \pi \\}
$$

- Conjunto vazio $\emptyset$: sem nenhum elemento
- Conjunto universo $U$: contém todos os elementos possíveis em uma análise

**Pertinência**
 - Pertence $\in$: Simboliza que um elemento está presente em um conjunto
 - Não pertence $\notin$: Simboliza o não pertencimento a um conjunto

 **Subconjuntos**

Dizemos que um conjunto A é subconjunto de outro conjunto B, se todos os elementos de A pertencem a B.

Ex.: 
$A = \\{ João, Carlos \\}$ e $B = \\{ Ana,Carlos,João \\}$
	Como todos os elementos de A pertencem ao conjunto B, podemos afirmar que _A é subconjunto de B

Obs.: B não é subconjunto de A

- Está contido $\subset$ : simboliza que um conjunto é subconjunto de outro
- Não está contido $\not\subset$ : simboliza que um conjunto não é subconjunto do outro

Por tanto, $A \subset B$, porém $B \not\subset A$

### Operações

**União $\cup$:** O resultado da união de dois conjuntos é um conjunto de todos os elementos que pertencem a pelo menos um dos dois conjuntos.

Ex.: $A = \\{ 1,3,5,8,10 \\}$ e $B = \\{ 2,5,6,8,9 \\}$
	$A \cup B = \\{ 1,2,3,5,6,8,9,10 \\}$

**Interseção $\cap$:** O resultado da interseção de dois conjuntos é um conjunto de todos os elementos que pertencem aos dois conjuntos simultaneamente.

Ex.: $A = \\{ 1,3,5,8,10 \\}$ e $B = \\{ 2,5,6,8,9 \\}$
	$A \cap B = \\{ 5,8 \\}$

**Diferença $(\backslash ou -)$:** O resultado da diferença de um conjunto A por B é um conjunto de todos os elementos de A que não pertencem a B.

Ex.: $A = \\{ 1,3,5,8,10 \\}$ e $B = \\{ 2,5,6,8,9 \\}$
	$A \backslash B = A - B = \\{ 1,3,10 \\}$

#### Complementar

O complementar de um conjunto A é um conjunto de elementos que não estão em A. Pode ser entendido como a diferença entre o conjunto Universo e o conjunto A

$$
A^{c} = U \backslash A
$$

Ex.: $A = \\{ 1,3,5,8,10 \\}$,  $B = \\{ 2,5,6,8,9 \\}$ e $U = \\{ 1,2,3,4,5,6,7,8,9,10 \\}$
	$A^{c} = \\{ 2,4,6,7,9 \\}$
	$B^{c} = \\{ 1,3,4,7,10 \\}$


---
## Lógica proposicional

**Proposição?**
	Uma proposição lógica é uma declaração que pode ser verdadeira OU falsa, nunca ambas.

Ex.: 
	p: A idade do cliente é de 46 anos.
	q: existe falha no sensor.
	r: A temperatura está maior que 30ºC.
	s: A transação foi feita de um país incomum.
Cada uma dessas afirmações é uma proposição lógica, que pode ser verdadeira ou falsa.


### Conectivos Lógicos

**Disjunção ($\lor$ , ou):**
	A disjunção é avaliada a partir de duas proposições lógicas. A disjunção é verdadeira se pelo menos uma das proposições for verdadeira.


|  p  |  q  | p $\lor$ q |
| :-: | :-: | :--------: |
|  V  |  V  |     V      |
|  V  |  F  |     V      |
|  F  |  V  |     V      |
|  F  |  F  |     F      |

**Conjunção ( $\land$ | e):**
	A conjunção é avaliada a partir de duas proposições lógicas. A conjunção é verdadeira quanto todas as proposições forem verdadeiras

|  p  |  q  | p $\land$ q |
| :-: | :-: | :---------: |
|  V  |  V  |      V      |
|  V  |  F  |      F      |
|  F  |  V  |      F      |
|  F  |  F  |      F      |

**Negação ($\neg$ | ~):**
	A negação inverte o valor lógico da proposição lógica. Se for verdadeiro, se torna falso. Se for falso, se torna verdadeiro.

|  p  | ~q  |
| :-: | :-: |
|  V  |  F  |
|  F  |  V  |

**Condicional (se ... então):**
	A implicação representa uma regra condicional. Se uma proposição é verdadeira, então a outra também deve ser.

|  p  |  q  | p $\to$ q |
| :-: | :-: | :-------: |
|  V  |  V  |     V     |
|  V  |  F  |     F     |
|  F  |  V  |     V     |
|  F  |  F  |     V     |

Ex.:
	p: O tempo está quente.
	q: Vou à praia.

Para o condicional $p\to q$ ser falso, a única possibilidade é o tempo estar quente e mesmo assim eu não ter ido à praia.

 **OBS.:** *Os conectivos também são usados em expressões lógicas complexas, que podem demandar, inclusive, todos os conectivos.*
	Ex.: 
	Em uma base de dados de transações financeiras, precisamos identificar transações suspeitas que:
		- Tem valor muito alto
		- OU local incomum
		- E não são clientes com histórico suspeito
		**R.:**
		Tem valor muito alto OU local incomum E NÃO são clientes com histórico suspeito
		Tem valor muito alto OU local incomum) E NÃO são clientes com histórico suspeito
		(p OU q) E $\lnot$ r
		(p $\lor$ q) $\land$ $\lnot$ r

|  p  |  q  |  r  | p $\lor$ q | ~r  | (p $\lor$ q) $\land$ ~r |
| :-: | :-: | :-: | :--------: | :-: | :---------------------: |
|  V  |  V  |  V  |     V      |  F  |            F            |
|  V  |  V  |  F  |     V      |  V  |            V            |
|  V  |  F  |  V  |     V      |  F  |            F            |
|  V  |  F  |  F  |     V      |  V  |            V            |
|  F  |  V  |  V  |     V      |  F  |            F            |
|  F  |  V  |  F  |     V      |  V  |            V            |
|  F  |  F  |  V  |     F      |  F  |            F            |
|  F  |  F  |  F  |     F      |  V  |            F            |
