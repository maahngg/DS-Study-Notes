
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

$$A = \begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} \cr a_{21} & a_{22} & \cdots & a_{2n} \cr \vdots & \vdots & \ddots & \vdots \cr a_{m1} & a_{m2} & \cdots & a_{mn} \end{bmatrix}$$

Cada elemento é identificado por seus índices $a_{ij}$, onde $i$ é a linha e $j$ a coluna.

Ex.: Uma matriz $2 \times 3$ (2 linhas, 3 colunas):

$$B = \begin{bmatrix} 1 & 5 & 9 \\
2 & 6 & 0 \end{bmatrix}$$

Neste caso, o elemento $b_{21} = 2$ (2ª linha, 1ª coluna).

### Matrizes Especiais

Algumas matrizes possuem propriedades únicas fundamentais para álgebra linear computacional:

1. Matriz Quadrada

Possui o mesmo número de linhas e colunas ($m = n$).

2. Matriz Identidade ($I$)

É a "unidade" das matrizes (equivalente ao número 1 na multiplicação escalar). É uma matriz quadrada preenchida com 0s, exceto na diagonal principal, que é preenchida com 1s.

$$I_3 = \begin{bmatrix} 1 & 0 & 0 \cr 0 & 1 & 0 \cr 0 & 0 & 1 \end{bmatrix}$$

Propriedade: $A \cdot I = A$

3. Matriz Transposta ($A^T$)

A transposição é uma operação que transforma as linhas de uma matriz em colunas (e vice-versa). O que era $m \times n$ vira $n \times m$.

Se  $A = \left[\matrix{1&2\cr 3&4}\right]$ , então  $A^T = \left[\matrix{1&3\cr 2&4}\right]$ .

- **Uso em Dados:** Frequentemente precisamos transpor matrizes para alinhar dimensões antes de realizar multiplicações (ex.: rotacionar um dataset para cálculos específicos).

### Operações com Matrizes

#### Soma e Subtração

Assim como nos vetores, é feita elemento a elemento.

Condição: As matrizes devem ter exatamente as mesmas dimensões.

$$\begin{bmatrix} 1 & 2 \cr 3 & 4 \end{bmatrix} + \begin{bmatrix} 10 & 1 \cr 0 & 2 \end{bmatrix} = \begin{bmatrix} 11 & 3 \cr 3 & 6 \end{bmatrix}$$

**Propriedades da Soma Matricial:**

Considerando matrizes $A, B, C$ de mesma dimensão e $O$ como a matriz nula (preenchida por zeros):

1. **Comutatividade:** A ordem da soma não altera o resultado.

$$A + B = B + A$$  
2. **Associatividade:** O agrupamento das somas não altera o resultado.

$$(A + B) + C = A + (B + C)$$

3. **Elemento Neutro:** Somar uma matriz com a matriz nula resulta nela mesma.

$$A + O = A$$

4. **Elemento Oposto:** Para toda matriz $A$, existe uma matriz $-A$ tal que a soma é nula.

$$A + (-A) = O$$

#### Multiplicação por Escalar

Multiplica-se cada elemento da matriz pelo número real $k$.

$$2 \cdot \begin{bmatrix} 1 & 2 \cr 3 & 4 \end{bmatrix} = \begin{bmatrix} 2 & 4 \cr 6 & 8 \end{bmatrix}$$

**Propriedades da Multiplicação por Escalar:**

Considerando matrizes $A, B$, e escalares (números reais) $k, c$:

1. **Distributividade em relação à soma de matrizes:**

$$k(A + B) = kA + kB$$

2. **Distributividade em relação à soma de escalares:**

$$(k + c)A = kA + cA$$

3. **Associatividade mista:**

$$k(cA) = (kc)A$$

4. **Identidade:** Multiplicar pelo escalar 1 não altera a matriz.

$$1 \cdot A = A$$

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

$$A = \begin{bmatrix} 1 & 2 \cr 3 & 4 \end{bmatrix} , \ \ B = \begin{bmatrix} 5 & 6 & 0 \cr 7 & 8 & 1 \end{bmatrix}$$

Verificação: $(2 \times \mathbf{2})$ e $(\mathbf{2} \times 3)$ $\to$ Compatível. Resultado será $2 \times 3$.

Cálculo do primeiro elemento (Linha 1 de A $\cdot$ Coluna 1 de B):

$c_{11} = (1 \cdot 5) + (2 \cdot 7) = 5 + 14 = 19$

Matriz final:

$$A \cdot B = \begin{bmatrix} (1\cdot5 + 2\cdot7) & (1\cdot6 + 2\cdot8) & (1\cdot0 + 2\cdot1) \cr (3\cdot5 + 4\cdot7) & (3\cdot6 + 4\cdot8) & (3\cdot0 + 4\cdot1) \end{bmatrix} = \begin{bmatrix} 19 & 22 & 2 \cr 43 & 50 & 4 \end{bmatrix}$$

**Propriedades da Multiplicação Matricial:**

Considerando as dimensões compatíveis para que as operações existam:

1. **Não Comutatividade:** Esta é a propriedade mais importante. A ordem importa.

$$A \cdot B \neq B \cdot A$$

_(Exceto em casos muito específicos, como multiplicação pela inversa ou identidade)._

2. **Associatividade:** Podemos agrupar as multiplicações, o que é vital para otimização de algoritmos.

$$(A \cdot B) \cdot C = A \cdot (B \cdot C)$$

3. **Distributividade:** A multiplicação se distribui sobre a soma.

$$A \cdot (B + C) = A \cdot B + A \cdot C$$
$$(A + B) \cdot C = A \cdot C + B \cdot C$$

4. **Elemento Neutro (Identidade):** A matriz Identidade $I$ funciona como o "1" da multiplicação.

$$A \cdot I = A \quad \text{e} \quad I \cdot A = A$$

5. **Transposta do Produto:** A transposta de um produto é o produto das transpostas em **ordem inversa**. (Muito usada em derivações de Machine Learning).

$$(A \cdot B)^T = B^T \cdot A^T$$

### Determinantes

O determinante é um escalar que pode ser calculado a partir de uma **matriz quadrada**. Ele resume propriedades importantes da matriz, como se ela possui inversa e como ela transforma volumes e áreas no espaço.

Denotamos o determinante de uma matriz $A$ como $\text{det}(A)$ ou $|A|$.

#### Cálculo de Determinantes

##### Matriz $2 \times 2$

Para uma matriz de ordem 2, o determinante é a diferença entre o produto dos elementos da diagonal principal e o da diagonal secundária.

Se $A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}$, então:

$$\text{det}(A) = (a \cdot d) - (b \cdot c)$$

##### Matriz $3 \times 3$ (Regra de Sarrus)

Para matrizes $3 \times 3$, uma técnica comum é repetir as duas primeiras colunas ao lado da matriz e somar os produtos das diagonais principais, subtraindo os produtos das diagonais secundárias.

#### Propriedades e Significados

1. **Inversibilidade:** Uma matriz $A$ só possui inversa se $\text{det}(A) \neq 0$. Se o determinante for zero, a matriz é chamada de **singular**.
2. **Transformação Linear:** Geometricamente, o valor absoluto do determinante representa o fator de escala pelo qual a matriz aumenta ou diminui áreas (em $\mathbb{R}^2$) ou volumes (em $\mathbb{R}^3$).
3. **Sinal:** O sinal do determinante indica se a transformação preserva ou inverte a orientação dos eixos.

#### Aplicações em Ciência de Dados

Toda a teoria de vetores, matrizes e determinantes não é apenas acadêmica; ela forma o motor matemático por trás dos algoritmos modernos.

##### 1. Representação de Dados

Como vimos, cada registro em um banco de dados é um **vetor** em um espaço $n$-dimensional. O conjunto de dados inteiro é uma grande **matriz**, onde as linhas são observações e as colunas são as características (_features_).

##### 2. PCA (Análise de Componentes Principais)

O PCA é uma técnica de redução de dimensionalidade. Quando temos dados com centenas de colunas (dimensões), o PCA utiliza a álgebra linear para encontrar novas direções (vetores) chamadas **Componentes Principais** que retêm a maior parte da informação original.

- **Autovetores e Autovalores:** O PCA calcula os autovetores da matriz de covariância dos dados. Esses vetores definem os novos eixos.
- **Redução de Ruído:** Ao descartar componentes com baixos "autovalores" (determinados via operações matriciais), simplificamos o modelo sem perder o padrão essencial.


##### 3. Sistemas de Recomendação

Empresas como Netflix e Amazon utilizam a **Decomposição de Matrizes** para prever suas preferências. Eles decompõem uma matriz gigante de "Usuários vs. Itens" em matrizes menores que representam gostos latentes, permitindo encontrar padrões ocultos entre o que você gosta e o que o sistema deve recomendar.

##### 4. Machine Learning e Otimização

Algoritmos de Regressão Linear, por exemplo, resolvem equações matriciais para encontrar os pesos ideais de um modelo. A operação base é muitas vezes a inversão de uma matriz ou o cálculo de um produto escalar em larga escala.

---

## Funções

Em Matemática e Ciência de Dados, o conceito de função é fundamental para modelar relacionamentos entre variáveis. Uma função descreve como uma entrada (input) é transformada em uma saída (output).

Formalmente, dados dois conjuntos $A$ e $B$, uma função $f$ é uma regra que associa cada elemento $x \in A$ a um **único** elemento $y \in B$.

Notação:

$$f: A \to B$$

$$y = f(x)$$

Onde:

- **Domínio ($A$):** Conjunto de todos os valores de entrada possíveis. 
- **Contradomínio ($B$):** Conjunto que contém todos os valores de saída possíveis.
- **Imagem:** Subconjunto de $B$ contendo apenas os valores efetivamente alcançados pela função.

**No contexto de Dados:**

Podemos encarar um modelo de Machine Learning como uma função $f(x)$ que tenta mapear características de entrada ($x$, as _features_) para uma predição ($y$, o _target_).

### Função de 1º grau (Função Afim)

Também conhecida como função linear ou afim, descreve um comportamento de crescimento ou decrescimento constante. É a base para algoritmos de **Regressão Linear**.

Sua lei de formação é dada por:

$$f(x) = ax + b$$

Onde $a, b \in \mathbb{R}$ e $a \neq 0$.

- **$a$ (Coeficiente Angular):** Determina a inclinação da reta.

	- Se $a > 0$: Função crescente.
    - Se $a < 0$: Função decrescente.
    - Em dados, $a$ representa o "peso" ou a importância da variável $x$.

- **$b$ (Coeficiente Linear):** Indica onde a reta corta o eixo $y$ (quando $x=0$). Em Machine Learning, é chamado de **Viés (Bias)** ou Intercepto.

**Gráfico:**

O gráfico de uma função de 1º grau é sempre uma **reta**.

**Raiz da função:**

O valor de $x$ que torna $f(x) = 0$.

$$x = -\frac{b}{a}$$

### Função de 2º grau (Função Quadrática)

Uma função quadrática é caracterizada pela presença de um termo elevado ao quadrado. Ela é crucial em Otimização e Ciência de Dados, pois muitas **Funções de Custo** (que medem o erro de um modelo) possuem formato quadrático (parábolas).

Sua lei de formação é:

$$f(x) = ax^2 + bx + c$$

Onde $a, b, c \in \mathbb{R}$ e $a \neq 0$.

**Gráfico:**

O gráfico é uma **parábola**.

- **Concavidade:**

    - Se $a > 0$: Concavidade para cima (sorriso). Possui um ponto de **Mínimo**.
    - Se $a < 0$: Concavidade para baixo (triste). Possui um ponto de **Máximo**.

**Vértice da Parábola:**

O vértice é o ponto de virada da função (o ponto máximo ou mínimo global). Em algoritmos como o _Gradient Descent_, o objetivo é justamente encontrar o ponto mínimo da função de erro.

As coordenadas do vértice $V = (x_v, y_v)$ são:

$$x_v = -\frac{b}{2a}$$

$$y_v = -\frac{\Delta}{4a}$$

**Fórmula de Bhaskara (Raízes):**

Para encontrar onde a parábola corta o eixo $x$ (fazer $f(x)=0$):

$$x = \frac{-b \pm \sqrt{\Delta}}{2a}$$

Onde o discriminante é $\Delta = b^2 - 4ac$.

### Função Polinomial

As funções de 1º e 2º grau são casos específicos de uma família maior chamada Funções Polinomiais.

Um polinômio é uma expressão algébrica formada pela soma de monômios (termos da forma $a \cdot x^n$).

A forma geral de uma função polinomial de grau $n$ é:

$$P(x) = a_n x^n + a_{n-1} x^{n-1} + \dots + a_1 x + a_0$$

Onde:

- $n$ é um número inteiro não negativo (o **grau** do polinômio).
- $a_n, a_{n-1}, \dots, a_0$ são constantes reais chamadas de **coeficientes**.
- $a_n \neq 0$ (o coeficiente dominante).

**Resumo sobre Polinômios em Dados:**

Polinômios de graus mais altos podem desenhar curvas extremamente complexas e cheias de curvas.

- **Grau 1:** Reta (Simples).
- **Grau 2:** Parábola (Curva simples).
- **Grau Alto (ex: 5):** Curva muito sinuosa.

_Atenção:_ Em Machine Learning, usar polinômios de grau muito alto para modelar dados pode levar ao **Overfitting** (o modelo "decora" o ruído dos dados ao invés de aprender o padrão geral).

#### Raízes de polinômios

As raízes (ou zeros) de um polinômio são os valores de $x$ tal que $P(x) = 0$. Geometricamente, são os pontos onde o gráfico intercepta o eixo horizontal ($x$).

**Propriedades Importantes:**

1. **Teorema Fundamental da Álgebra:** Todo polinômio de grau $n$ ($n \geq 1$) possui exatamente $n$ raízes complexas (podendo algumas ser reais e outras não, ou raízes repetidas).
2. **Decomposição:** Se conhecermos as raízes $r_1, r_2, \dots, r_n$ de um polinômio, podemos reescrevê-lo na forma fatorada:

$$P(x) = a_n(x - r_1)(x - r_2)\dots(x - r_n)$$

Isso é útil para simplificar equações e entender o comportamento da função perto de seus zeros.

---

## Cálculo diferencial

O Cálculo Diferencial é o ramo da matemática que estuda como as coisas mudam. Ele foca nas **taxas de variação** de grandezas e na inclinação de curvas.

Em Ciência de Dados e Machine Learning, o cálculo diferencial é a "espinha dorsal" do treinamento de modelos. A maioria dos algoritmos "aprende" através de um processo de otimização (como o _Gradient Descent_), onde o objetivo é encontrar o ponto mínimo de uma função de erro. O cálculo fornece as ferramentas para determinar a direção e o tamanho do passo necessário para alcançar esse mínimo.

### Limites

O conceito de limite é a base fundamental sobre a qual todo o cálculo é construído (incluindo derivadas e integrais). Informalmente, o limite descreve o comportamento de uma função à medida que sua entrada ($x$) se aproxima arbitrariamente de um determinado valor, independentemente do que acontece no ponto exato.

**Notação:**

$$\lim_{x \to a} f(x) = L$$

Lê-se: "O limite de $f(x)$ quando $x$ tende a $a$ é igual a $L$".

Isso significa que podemos tornar o valor de $f(x)$ tão próximo de $L$ quanto quisermos, desde que escolhamos um $x$ suficientemente próximo de $a$ (mas diferente de $a$).

**Existência do Limite:**

Para que um limite exista, o comportamento da função deve ser o mesmo, independentemente de nos aproximarmos de $a$ por valores maiores (direita) ou menores (esquerda).

- **Limite à Esquerda ($x \to a^-$):** Aproximação por valores menores que $a$.
- **Limite à Direita ($x \to a^+$):** Aproximação por valores maiores que $a$.

Para o limite existir, é necessário que:

$$\lim_{x \to a^-} f(x) = \lim_{x \to a^+} f(x) = L$$

**Exemplos:**

1. **Substituição Direta (Funções Contínuas):**
    Se a função não apresenta problemas no ponto $a$ (como divisão por zero), o limite é simplesmente o valor da função no ponto.

    Seja $f(x) = x^2 + 2$:

$$\lim_{x \to 3} (x^2 + 2) = 3^2 + 2 = 11$$

2. **Indeterminações (A base da derivada):**
    Limites tornam-se poderosos quando lidam com situações onde a substituição direta resulta em erros matemáticos, como $\frac{0}{0}$.

    Seja $f(x) = \frac{x^2 - 1}{x - 1}$. Se tentarmos calcular para $x=1$, teremos $\frac{0}{0}$.

    Usando fatoração algébrica para simplificar:

$$\lim_{x \to 1} \frac{(x-1)(x+1)}{(x-1)} = \lim_{x \to 1} (x+1) = 2$$

**Importância para Dados:**

Embora raramente calculemos limites manualmente em scripts de Python, o conceito é vital para entender **Derivadas**. A derivada é definida formalmente como um limite de uma taxa de variação média:

$$f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$$

Sem o conceito de limite (aproximar $h$ de 0 sem que ele seja 0), não poderíamos calcular gradientes, e consequentemente, não conseguiríamos treinar redes neurais.

### Derivada

A derivada é a ferramenta matemática que quantifica a sensibilidade de mudança de uma função. Se uma função $f(x)$ descreve um fenômeno, a sua derivada $f'(x)$ descreve **como** esse fenômeno está mudando em um instante específico.

Geometricamente, a derivada de uma função em um ponto é igual à **inclinação (coeficiente angular) da reta tangente** à curva naquele ponto.

**Notação:**

Existem duas notações principais que você encontrará em livros e artigos de Machine Learning:

- **Lagrange:** $f'(x)$ ou $y'$

- **Leibniz:** $\frac{df}{dx}$ ou $\frac{dy}{dx}$ (Lê-se "derivada de f em relação a x")

**Interpretação do Sinal:**

O valor da derivada em um ponto nos diz muito sobre o comportamento da função:

- **$f'(x) > 0$:** A função é **crescente** naquele ponto.
- **$f'(x) < 0$:** A função é **decrescente** naquele ponto.
- **$f'(x) = 0$:** A função está em um ponto estacionário (possivelmente um **Máximo** ou **Mínimo** local).

Em Ciência de Dados, nosso principal interesse é encontrar onde a derivada é zero, pois isso indica que podemos ter encontrado o erro mínimo do nosso modelo.

#### Interpretação Geométrica: A Reta Tangente

A forma mais intuitiva de visualizar a derivada é através da geometria analítica. Para entender isso, precisamos revisitar o conceito de inclinação (coeficiente angular) de uma reta.

Se tivermos dois pontos em um gráfico, a inclinação da reta que os conecta é dada pela razão entre a variação vertical e a variação horizontal:

$$m = \frac{\Delta y}{\Delta x} = \frac{y_2 - y_1}{x_2 - x_1}$$

Quando esses dois pontos estão distantes na curva de uma função $f(x)$, a reta que os une é chamada de **Reta Secante**. Ela representa a _taxa média_ de variação naquele intervalo.

**O Pulo para a Derivada**

A derivada surge quando tentamos calcular essa inclinação usando dois pontos que estão **infinitamente próximos**.

Imagine que começamos a aproximar o segundo ponto em direção ao primeiro. A distância horizontal ($\Delta x$) começa a diminuir.

1. À medida que $\Delta x$ se aproxima de zero, a Reta Secante começa a girar.
2. No limite, quando $\Delta x \to 0$, essa reta toca a curva em apenas um ponto. Ela se torna a **Reta Tangente**.

Assim, a derivada $f'(x)$ nada mais é do que a inclinação dessa reta tangente. Matematicamente, definimos isso como o limite da razão $\frac{\Delta y}{\Delta x}$:

$$f'(x) = \lim_{\Delta x \to 0} \frac{\Delta y}{\Delta x} = \lim_{\Delta x \to 0} \frac{f(x+\Delta x) - f(x)}{\Delta x}$$

**Resumo visual:**

- **$\frac{\Delta y}{\Delta x}$ (sem limite):** Inclinação média entre dois pontos (Secante).

- **$\frac{dy}{dx}$ (com limite):** Inclinação exata em um ponto (Tangente/Derivada).

#### Regras Básicas de Derivação

Para calcular derivadas, raramente usamos a definição de limite. Usamos regras práticas. As mais comuns são:

**1. Derivada de uma Constante:**

A derivada de um número fixo é sempre zero (pois ele não muda).

$$f(x) = k \implies f'(x) = 0$$

**2. Regra da Potência (Regra do Tombo):**

Essa é a regra mais utilizada para polinômios.

$$f(x) = x^n \implies f'(x) = n \cdot x^{n-1}$$

Ex.:

Se $f(x) = x^2$ (Função Quadrática/Parábola):

$f'(x) = 2x^{2-1} = 2x$

**3. Derivada da Soma:**

A derivada de uma soma de funções é a soma das derivadas.

$$h(x) = f(x) + g(x) \implies h'(x) = f'(x) + g'(x)$$

**4. Regra da Cadeia (Chain Rule):**

Fundamental para **Redes Neurais** (algoritmo _Backpropagation_). Serve para derivar funções compostas (função dentro de função).

$$h(x) = f(g(x)) \implies h'(x) = f'(g(x)) \cdot g'(x)$$

"Deriva a de fora (mantendo a de dentro) e multiplica pela derivada da de dentro".

#### Máximos e Mínimos

Uma das aplicações mais importantes das derivadas em Ciência de Dados é a **Otimização**. Otimizar um modelo significa, na maioria das vezes, encontrar os melhores parâmetros para minimizar o erro. Para isso, precisamos identificar os pontos de Máximo e Mínimo de uma função.

Como vimos anteriormente, a derivada $f'(x)$ representa a inclinação da reta tangente. Imagine o pico de uma montanha (máximo) ou o fundo de um vale (mínimo): nestes pontos exatos, a inclinação é nula (a reta tangente é horizontal).

Portanto, a condição necessária para um ponto ser um máximo ou um mínimo local é:

$$f'(x) = 0$$

Esses pontos onde a derivada é zero são chamados de **Pontos Críticos**.

**Classificação:**

Embora $f'(x) = 0$ indique um ponto crítico, precisamos saber se ele é um topo ou um fundo.

1. **Máximo Local:** O gráfico sobe antes do ponto e desce depois. A derivada muda de positiva para negativa.
2. **Mínimo Local:** O gráfico desce antes do ponto e sobe depois. A derivada muda de negativa para positiva.

**No contexto de Dados (Função de Custo):**

Em Machine Learning, definimos uma "Função de Custo" (ou _Loss Function_) que mede o quão ruim é o nosso modelo. O gráfico dessa função geralmente se assemelha a um vale.

- Nosso objetivo é encontrar o **Mínimo Global** dessa função (o ponto mais baixo do vale).
- Nesse ponto mínimo, o erro é o menor possível e a derivada é zero.
- Algoritmos de otimização utilizam a derivada para "saber para onde descer" até encontrar esse ponto onde a inclinação se anula.

#### Derivadas Parciais e o Gradiente

Na maioria dos problemas de dados, trabalhamos com funções de **múltiplas variáveis** (ex.: erro dependendo de vários pesos $w_1, w_2, ...$).

Quando derivamos em relação a uma variável específica, tratamos todas as outras como se fossem constantes. Isso é chamado de **Derivada Parcial**.

Notação: $\frac{\partial f}{\partial x}$ (usa-se o símbolo "del" $\partial$).

Ex.: Seja $f(x, y) = x^2 + 3y$.

- Derivada em relação a $x$: $\frac{\partial f}{\partial x} = 2x$ (o termo $3y$ é tratado como constante e vira 0).
- Derivada em relação a $y$: $\frac{\partial f}{\partial y} = 3$ (o termo $x^2$ vira 0, e a derivada de $3y$ é 3).

**O Gradiente ($\nabla$):**

O Gradiente é um **vetor** que agrupa todas as derivadas parciais de uma função.

$$\nabla f = \left[ \frac{\partial f}{\partial x_1}, \frac{\partial f}{\partial x_2}, ..., \frac{\partial f}{\partial x_n} \right]$$

**Aplicação Fundamental:** O vetor gradiente sempre aponta na direção de **maior crescimento** da função.

Por isso, no algoritmo de **Gradient Descent**, nós andamos na direção oposta ao gradiente ($-\nabla f$) para "descer a montanha" e encontrar o erro mínimo.