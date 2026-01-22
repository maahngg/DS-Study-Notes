
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

### **Vetor**

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

### Operações com Vetores

#### Soma e  Subtração:

A soma de dois vetores é realizada somando seus componentes correspondentes. Geometricamente, isso equivale a colocar a "cauda" de um vetor na "ponta" do outro (regra do polígono ou do paralelogramo).

Sejam $\vec{u} = [u_1, u_2, ..., u_n]$ e $\vec{v} = [v_1, v_2, ..., v_n]$:

$$\vec{u} \pm \vec{v} = [u_1 \pm v_1, u_2 \pm v_2, ..., u_n \pm v_n]$$

Ex.:

$\vec{u} = [2, 5]$ e $\vec{v} = [3, 1]$

$\vec{u} + \vec{v} = [2+3, 5+1] = [5, 6]$

#### Multiplicação por Escalar:

Consiste em multiplicar um vetor por um número real (chamado de escalar). Isso altera a **magnitude** do vetor (o estica ou encolhe). Se o escalar for negativo, o **sentido** do vetor é invertido.

Seja $k$ um número real e $\vec{v} = [v_1, ..., v_n]$:

$$k \cdot \vec{v} = [k \cdot v_1, k \cdot v_2, ..., k \cdot v_n]$$

Ex.:

$\vec{v} = [2, -4]$ e $k = 3$

$3 \cdot \vec{v} = [3(2), 3(-4)] = [6, -12]$

#### Cálculo da Magnitude (Módulo ou Norma)

Como vimos nas propriedades geométricas, a **magnitude** (ou norma) representa o comprimento do vetor. Algebricamente, ela é calculada utilizando uma generalização do **Teorema de Pitágoras**.

Para um vetor $\vec{v}$, a norma é denotada por $||\vec{v}||$ (ou as vezes $|\vec{v}|$) e é definida como a raiz quadrada da soma dos quadrados de seus componentes.

Fórmula Geral ($\mathbb{R}^n$):

Dado um vetor $\vec{v} = [v_1, v_2, ..., v_n]$, sua norma é:

$$||\vec{v}|| = \sqrt{v_1^2 + v_2^2 + ... + v_n^2} = \sqrt{\sum_{i=1}^{n} v_i^2}$$

Essa fórmula também pode ser expressa através do produto escalar do vetor por ele mesmo:

$$||\vec{v}|| = \sqrt{\vec{v} \cdot \vec{v}}$$

Ex.:

1. No Plano ($\mathbb{R}^2$):

Imagine um vetor de deslocamento $\vec{v} = [3, 4]$. Para saber a distância total percorrida (o tamanho do vetor):

$$||\vec{v}|| = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5$$

Geometricamente, isso equivale a calcular a hipotenusa de um triângulo retângulo com catetos 3 e 4.

2. No Espaço ($\mathbb{R}^3$):

Para um vetor $\vec{u} = [1, 2, 2]$:

$$||\vec{u}|| = \sqrt{1^2 + 2^2 + 2^2} = \sqrt{1 + 4 + 4} = \sqrt{9} = 3$$

#### Normalização (Vetor Unitário)

Uma aplicação direta do cálculo da norma é a **Normalização**. Normalizar um vetor significa alterar sua magnitude para 1 (tornando-o um _Vetor Unitário_), mantendo sua direção e sentido originais. Isso é muito comum em algoritmos de Machine Learning para colocar dados em uma mesma escala.

Para normalizar um vetor $\vec{v}$, basta dividir cada um de seus componentes pela sua norma $||\vec{v}||$:

$$\vec{u} = \frac{\vec{v}}{||\vec{v}||}$$

Ex.: Normalizando o vetor $\vec{v} = [3, 4]$ (que sabemos ter norma 5):

$$\vec{u} = [\frac{3}{5}, \frac{4}{5}] = [0.6, 0.8]$$

Verificação: $\sqrt{0.6^2 + 0.8^2} = \sqrt{0.36 + 0.64} = \sqrt{1} = 1$.

#### Produto Escalar (Dot Product):

Esta é uma das operações mais importantes para Ciência de Dados. O produto escalar de dois vetores resulta em um **número real** (um escalar), e não em outro vetor.

Ele é calculado somando-se os produtos dos componentes correspondentes.

$$\vec{u} \cdot \vec{v} = \sum_{i=1}^{n} u_i v_i = u_1v_1 + u_2v_2 + ... + u_nv_n$$

Ex.:

$\vec{u} = [1, 3, -5]$ e $\vec{v} = [4, -2, -1]$

$\vec{u} \cdot \vec{v} = (1)(4) + (3)(-2) + (-5)(-1)$

$\vec{u} \cdot \vec{v} = 4 - 6 + 5 = 3$

**Interpretação Geométrica do Produto Escalar:**

O produto escalar nos dá informações sobre o ângulo $\theta$ entre dois vetores.

$$\vec{u} \cdot \vec{v} = ||\vec{u}|| \cdot ||\vec{v}|| \cdot \cos(\theta)$$

Isso gera propriedades fundamentais para algoritmos de Machine Learning (como similaridade de cosseno):

- Se $\vec{u} \cdot \vec{v} > 0$: O ângulo é agudo ($< 90^{\circ}$), apontam para sentidos similares.
- Se $\vec{u} \cdot \vec{v} < 0$: O ângulo é obtuso ($> 90^{\circ}$), apontam para sentidos opostos.
- Se $\vec{u} \cdot \vec{v} = 0$: Os vetores são **Ortogonais** (perpendiculares, $90^{\circ}$).

**Propriedades do Produto Escalar**

O produto escalar possui propriedades algébricas muito semelhantes à multiplicação de números reais, com algumas peculiaridades importantes.

Considere os vetores $\vec{u}, \vec{v}, \vec{w}$ e um número real (escalar) $k$.

1. Comutatividade

A ordem dos vetores não altera o resultado do produto escalar.

$$\vec{u} \cdot \vec{v} = \vec{v} \cdot \vec{u}$$

2. Distributividade em relação à soma

O produto escalar pode ser distribuído sobre uma soma de vetores.

$$\vec{u} \cdot (\vec{v} + \vec{w}) = \vec{u} \cdot \vec{v} + \vec{u} \cdot \vec{w}$$

3. Associatividade com Escalar

Ao multiplicar um produto escalar por um número real $k$, você pode associar o escalar a qualquer um dos vetores ou ao resultado final.

$$k(\vec{u} \cdot \vec{v}) = (k\vec{u}) \cdot \vec{v} = \vec{u} \cdot (k\vec{v})$$

4. Produto por si mesmo (Norma ao Quadrado)

O produto escalar de um vetor por ele mesmo é igual ao quadrado de sua magnitude (norma). O resultado é sempre não-negativo ($\geq 0$).

$$\vec{v} \cdot \vec{v} = ||\vec{v}||^2$$

Obs.: $\vec{v} \cdot \vec{v} = 0$ se, e somente se, $\vec{v}$ for o vetor nulo ($\vec{0}$).

**Propriedades Geométricas Importantes**

Essas propriedades conectam a álgebra à geometria e são a base para medir "similaridade" entre dados.

1. Condição de Ortogonalidade

Dois vetores não nulos são ortogonais (perpendiculares, formam $90^{\circ}$) se, e somente se, seu produto escalar for zero.

$$\vec{u} \perp \vec{v} \iff \vec{u} \cdot \vec{v} = 0$$

Isso ocorre pois $\cos(90^{\circ}) = 0$.

2. Desigualdade de Cauchy-Schwarz

Esta é uma das desigualdades mais famosas na matemática. Ela afirma que o módulo do produto escalar nunca supera o produto das normas dos vetores.

$$|\vec{u} \cdot \vec{v}| \leq ||\vec{u}|| \cdot ||\vec{v}||$$

Contexto em Dados: Essa propriedade garante que a correlação (ou similaridade de cosseno) esteja sempre entre -1 e 1.

3. Ângulo entre Vetores

Reorganizando a fórmula geométrica, podemos encontrar o ângulo $\theta$ entre dois vetores conhecendo apenas suas coordenadas:

$$\cos(\theta) = \frac{\vec{u} \cdot \vec{v}}{||\vec{u}|| \cdot ||\vec{v}||}$$

### Distância entre Pontos

Em Ciência de Dados, calcular a "proximidade" ou "semelhança" entre dois registros é uma tarefa fundamental (utilizada em algoritmos como _K-Nearest Neighbors_ e _K-Means_).

A forma mais intuitiva e comum de medir essa separação é através da **Distância Euclidiana**. Geomericamente, ela representa o comprimento do segmento de reta que conecta dois pontos.

#### No Plano ($\mathbb{R}^2$)

Dados dois pontos $A = (x_A, y_A)$ e $B = (x_B, y_B)$, a distância $d(A, B)$ é derivada diretamente do Teorema de Pitágoras, calculando a hipotenusa do triângulo formado pelas diferenças das coordenadas:

$$d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2}$$

#### Relação com Vetores

Existe uma conexão direta entre a distância de pontos e a norma de vetores. A distância entre dois pontos $A$ e $B$ é exatamente igual à **magnitude (norma) do vetor diferença** entre eles.

Se imaginarmos os pontos como vetores partindo da origem ($\vec{a}$ e $\vec{b}$), a distância é:

$$d(A, B) = ||\vec{b} - \vec{a}||$$

#### Generalização para $\mathbb{R}^n$

Como em dados trabalhamos com múltiplas dimensões, a fórmula se estende somando o quadrado da diferença de cada componente correspondente.

Para dois pontos $A = (a_1, a_2, ..., a_n)$ e $B = (b_1, b_2, ..., b_n)$:

$$d(A, B) = \sqrt{\sum_{i=1}^{n} (b_i - a_i)^2}$$

**Exemplo Prático:**

Vamos calcular a distância entre dois perfis de clientes (pontos no $\mathbb{R}^3$):

- Cliente A: (Idade: 25, Renda: 3, Score: 2) $\to A = (25, 3, 2)$
- Cliente B: (Idade: 28, Renda: 7, Score: 2) $\to B = (28, 7, 2)$


1. Calculamos a diferença componente a componente:
    - $28 - 25 = 3$
    - $7 - 3 = 4$
    - $2 - 2 = 0$

2. Aplicamos a fórmula:

$$d(A, B) = \sqrt{3^2 + 4^2 + 0^2}$$

$$d(A, B) = \sqrt{9 + 16 + 0}$$

$$d(A, B) = \sqrt{25} = 5$$

A "distância" (ou dissimilaridade) entre esses dois clientes é 5.

*Obs.: Apesar da distância euclidiana ser a mais comum, outas métricas podem ser mais apropriadas a depender da situação.*

## Matrizes

Uma matriz é uma estrutura matemática organizada em linhas e colunas. Enquanto um vetor é uma lista de números (unidimensional), uma matriz é uma tabela bidimensional de números.

Em Ciência de Dados, as matrizes são onipresentes. A analogia mais direta é um **DataFrame** (tabela de dados):

- Cada **linha** representa uma observação (ex.: um cliente).
    
- Cada **coluna** representa um atributo ou "feature" (ex.: idade, renda).
    

### Notação e Dimensão

Geralmente denotamos matrizes por letras maiúsculas (ex.: $A, B, W$).

Uma matriz $A$ com **$m$** linhas e **$n$** colunas é chamada de matriz de ordem $m \times n$ (lê-se "m por n").

$$A = \begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{bmatrix}$$

Cada elemento é identificado por seus índices $a_{ij}$, onde $i$ é a linha e $j$ a coluna.

Ex.: Uma matriz $2 \times 3$ (2 linhas, 3 colunas):

$$B = \begin{bmatrix} 1 & 5 & 9 \\ 2 & 6 & 0 \end{bmatrix}$$

Neste caso, o elemento $b_{21} = 2$ (2ª linha, 1ª coluna).

### Matrizes Especiais

Algumas matrizes possuem propriedades únicas fundamentais para álgebra linear computacional:

1. Matriz Quadrada

Possui o mesmo número de linhas e colunas ($m = n$).

2. Matriz Identidade ($I$)

É a "unidade" das matrizes (equivalente ao número 1 na multiplicação escalar). É uma matriz quadrada preenchida com 0s, exceto na diagonal principal, que é preenchida com 1s.

$$I_3 = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$$

Propriedade: $A \cdot I = A$

3. Matriz Transposta ($A^T$)

A transposição é uma operação que transforma as linhas de uma matriz em colunas (e vice-versa). O que era $m \times n$ vira $n \times m$.

Se $A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}$, então $A^T = \begin{bmatrix} 1 & 3 \\ 2 & 4 \end{bmatrix}$.

- **Uso em Dados:** Frequentemente precisamos transpor matrizes para alinhar dimensões antes de realizar multiplicações (ex.: rotacionar um dataset para cálculos específicos).

### Operações com Matrizes

#### Soma e Subtração

Assim como nos vetores, é feita elemento a elemento.

Condição: As matrizes devem ter exatamente as mesmas dimensões.

$$\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} + \begin{bmatrix} 10 & 1 \\ 0 & 2 \end{bmatrix} = \begin{bmatrix} 11 & 3 \\ 3 & 6 \end{bmatrix}$$

#### Multiplicação por Escalar

Multiplica-se cada elemento da matriz pelo número real $k$.

$$2 \cdot \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} = \begin{bmatrix} 2 & 4 \\ 6 & 8 \end{bmatrix}$$

#### Multiplicação de Matrizes (Produto Matricial)

Esta é a operação mais crítica e frequentemente a mais confusa. Diferente da soma, **não** multiplicamos elemento com elemento.

O produto matricial é baseado no **produto escalar** (linhas da primeira matriz $\times$ colunas da segunda matriz).

Regra de Compatibilidade:

Para multiplicar $A \cdot B$, o número de colunas de A deve ser igual ao número de linhas de B.

$$A_{(m \times \mathbf{n})} \cdot B_{(\mathbf{n} \times p)} = C_{(m \times p)}$$

A matriz resultante terá o número de linhas de A e o número de colunas de B.

Algoritmo:

O elemento $c_{ij}$ da matriz resultante é o produto escalar da Linha $i$ de A pela Coluna $j$ de B.

Ex.: $A$ ($2 \times 2$) e $B$ ($2 \times 3$)

$$A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} , \ \ B = \begin{bmatrix} 5 & 6 & 0 \\ 7 & 8 & 1 \end{bmatrix}$$

Verificação: $(2 \times \mathbf{2})$ e $(\mathbf{2} \times 3)$ $\to$ Compatível. Resultado será $2 \times 3$.

Cálculo do primeiro elemento (Linha 1 de A $\cdot$ Coluna 1 de B):

$c_{11} = (1 \cdot 5) + (2 \cdot 7) = 5 + 14 = 19$

Matriz final:

$$A \cdot B = \begin{bmatrix} (1\cdot5 + 2\cdot7) & (1\cdot6 + 2\cdot8) & (1\cdot0 + 2\cdot1) \\ (3\cdot5 + 4\cdot7) & (3\cdot6 + 4\cdot8) & (3\cdot0 + 4\cdot1) \end{bmatrix} = \begin{bmatrix} 19 & 22 & 2 \\ 43 & 50 & 4 \end{bmatrix}$$

**Atenção:** A multiplicação de matrizes **não é comutativa**. Geralmente, $A \cdot B \neq B \cdot A$.
