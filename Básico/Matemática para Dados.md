
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

---
## Álgebra Linear

### Sistema de Coordenadas

Um sistema de coordenadas permite a identificação de pontos no espaço através de um conjunto de números.

O sistema mais comum é o **Sistema Cartesiano**, formado por eixos perpendiculares que se cruzam na origem.

Plano Cartesiano ($\mathbb{R}^2$):

Formado por dois eixos reais.

- **Eixo das Abscissas ($x$):** Eixo horizontal.
- **Eixo das Ordenadas ($y$):** Eixo vertical.

Um ponto $P$ é representado por um par ordenado (Caso do $\mathbb{R}^{2}$):

$$P = (x, y)$$

<div align="center">
<img src="https://www.pngkey.com/png/full/555-5555630_open-exemplo-de-plano-cartesiano.png" width="300px"  />
</div>

***Obs.:*** Repare que a convenção padrão é $P = (x, y)$ . Caso usemos $P = (y, x)$ teremos pontos diferentes dos representados, exceto em casos que $x = y$ . Por isso, há importância em fazer uso da convenção.

Ex.: Para representar um dado de um cliente onde o eixo $x$ é a idade e o eixo $y$ é a renda mensal (em milhares):

$P = (30, 5)$ $\to$ Cliente com 30 anos e renda de 5 mil.

Espaço n-Dimensional ($\mathbb{R}^n$):

Em Ciência de Dados, raramente trabalhamos apenas com duas dimensões. Cada "feature" (coluna/atributo) de uma base de dados representa uma dimensão.

Um ponto em $\mathbb{R}^n$ é representado por uma n-upla (sequência de $n$ elementos).

$$P = (x_1, x_2, x_3, ..., x_n)$$

Ex.: Um registro contendo \[Idade, Renda, Pontuação de Crédito, Número de Filhos\] seria um ponto em um espaço de 4 dimensões ($\mathbb{R}^4$).

$A = (35, 8000, 750, 2)$

#### **Vetor**

Matematicamente, um vetor é um objeto geométrico que possui **magnitude** (tamanho/comprimento), **direção** e **sentido**. Pode ser visualizado como uma seta que parte da origem do sistema de coordenadas até um ponto $P$.

Algebricamente (e na Ciência de Dados), abstraímos a geometria e definimos um vetor simplesmente como uma **lista ordenada de números**.

Geralmente é denotado por uma letra minúscula em negrito ($\mathbf{v}$) ou com uma seta ($\vec{v}$).

Um vetor no $\mathbb{R}^n$ é definido como:

$$\vec{v} = [v_1, v_2, ..., v_n]$$

Onde cada $v_i$ é um componente (ou coordenada) do vetor.

##### Propriedades Geométricas:

Geometricamente, um vetor é caracterizado por três componentes fundamentais que definem sua existência no espaço.

**1. Magnitude (Módulo ou Norma)**

Refere-se ao "tamanho" ou "comprimento" do vetor. Matematicamente, é a distância escalar entre a origem e a extremidade do vetor.

Em Ciência de Dados, a magnitude é frequentemente associada à intensidade ou "força" da observação.

- Notação comum: $||\vec{v}||$ ou $|\vec{v}|$

**2. Direção**

Refere-se à reta suporte sobre a qual o vetor está assentado. A direção indica a inclinação do vetor em relação aos eixos do sistema de coordenadas.

Dizemos que dois vetores têm a mesma direção se forem paralelos (estiverem na mesma reta suporte ou em retas paralelas).

Ex.: Horizontal, vertical, inclinado a 30º.

**3. Sentido**

Refere-se à orientação do vetor ao longo de sua direção. Para cada direção determinada, existem apenas dois sentidos possíveis. É indicado visualmente pela ponta da seta.

Ex.: Da esquerda para a direita, de cima para baixo, positivo, negativo.

Analogia Prática:

Imagine um carro viajando em uma rodovia entre São Paulo e Rio de Janeiro.

- **Direção:** A rodovia em si (a linha que conecta as cidades).
- **Sentido:** Indo para o Rio de Janeiro (ou voltando para São Paulo).
- **Magnitude:** A velocidade do carro (ex.: 100 km/h).

_**Obs.:** É importante notar que vetores só são considerados **iguais** se compartilharem exatamente a mesma magnitude, a mesma direção e o mesmo sentido._

**Vetor Linha vs. Vetor Coluna**

Em álgebra linear computacional, a orientação é importante:

- Vetor Linha: 

$$\vec{v} = [v_1, v_2, ..., v_n]$$

- Vetor Coluna:

$$\vec{v} = \begin{bmatrix} v_1 \\ 
v_2 \\ 
\vdots \\ 
v_n \end{bmatrix}$$

