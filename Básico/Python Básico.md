
Para uma explicação rápida, acesse: [[Python Básico - Cheat Sheet]]

# Variáveis

Variáveis são espaços alocados na memória do computador para armazenar dados.

Em Python, o tipo de dado não precisa ser declarado antes (tipagem dinâmica). Uma variável é definida por `=`, sendo este o sinal de atribuição.

- A nomenclatura padrão para variáveis Python, por convenção, é a **snake_case** (tudo minúsculo separado por *underline*).
- É preferível que a declaração de uma variável seja semântica (o nome deve explicar o que a variável carrega).
- Se uma variável nasce para **nunca mudar de valor** (uma constante), escreva o nome todo em maiúsculo. Isso avisa ao programador: "Não altere esse valor".
- Nunca dê a uma variável o nome de uma função nativa do Python. Isso "quebra" a função original, impedindo que você a use depois.


```python
texto = 'TEXTO'
Texto = 'Texto com inicial maiúscula'
numeros_megasena = [1, 14, 59, 23, 11, 5]
saudacao = 'Opa! Tudo bem?'
```
**Obs.:** O Python é uma linguagem _case-sensitive_, ou seja, diferencia maiúsculas de minúsculas. Portanto, as variáveis **Texto** e **texto** são interpretadas como espaços de memória totalmente diferentes.

## Tipos de dados

### integer

Os tipos `int` representam o conjunto dos números inteiros (positivos, negativos e zero), sem parte decimal:

$$\mathbb{Z} = \{...,-3,-2,-1,0,1,2,3,...\}$$

As variáveis do tipo `int` são assim:

```python
idade = 25
temperatura = -5
quantidade_habitantes = 8000000000  # Python lida com inteiros arbitrariamente grandes
```

### float

Os tipos `float` representam o conjunto dos números reais (com ponto flutuante):

$$\mathbb{R} = \{ ...,-1.0 ,...,-0.75,..., -\frac{1}{2}, ...,0,...,0.5,..., \frac{1}{4},...,1.0,...\}$$

As variáveis do tipo `float` são assim:

```python
altura_metros = 1.75
peso_kg = 69.5
```

### boolean

O tipo `bool` representa a Álgebra Booleana, contendo apenas dois valores lógicos possíveis, frequentemente associados a verdadeiro (1) e falso (0):

$$\mathbb{B} = \{True, False\} \equiv \{1, 0\}$$

As variáveis do tipo `bool` são assim (note as iniciais maiúsculas, obrigatórias em Python):

```python
usuario_ativo = True
pagamento_aprovado = False
```

### complex

O tipo `complex` representa o conjunto dos números complexos. Em Python, a unidade imaginária ($i$) é representada pela letra `j`:

$$\mathbb{C} = \{ a + bi \mid a, b \in \mathbb{R} \text{ e } i = \sqrt{-1} \}$$

As variáveis do tipo `complex` são assim:

```python
numero_complexo = 2 + 3j
corrente_eletrica = 5j
```

### string

O tipo `str` (String) representa uma sequência finita de caracteres pertencentes a um alfabeto $\Sigma$ (no caso do Python 3, o padrão Unicode). Se $S$ é o conjunto de todas as strings possíveis:

$$S = \{ (c_1, c_2, ..., c_n) \mid n \in \mathbb{N}_0, c_i \in \Sigma \}$$

As variáveis do tipo `str` são delimitadas por aspas:

```python
nome = "Gemini"
frase = 'Python é fascinante'
numero_como_texto = "100"  # Isso não é um int, é uma str
```

## Estrutura de dados

### list

A lista (`list`) é uma sequência finita ordenada de elementos, onde a repetição é permitida e a ordem de inserção é preservada. Matematicamente, pode ser vista como uma ênupla (n-tuple) mutável de tamanho $n$:

$$L = (a_0, a_1, ..., a_{n-1}) \quad \text{onde } a_i \in \mathbb{U} \text{ (Universo de tipos)}$$

As variáveis do tipo `list` são definidas por colchetes:

```python
numeros_primos = [2, 3, 5, 7, 11]
elementos_mistos = [10, "Python", 3.14, True] # Listas aceitam tipos variados
matriz = [[1, 0], [0, 1]] # Lista de listas
```

### tuple

A tupla (`tuple`) é estruturalmente idêntica à lista (uma sequência ordenada finita), porém com a propriedade de **imutabilidade**. Uma vez definida, seus elementos não podem ser alterados. É um vetor constante:

$$T = (a_0, a_1, ..., a_{n-1}) \quad \text{sujeito a } \Delta T = \emptyset$$

As variáveis do tipo `tuple` são definidas por parênteses (ou apenas vírgulas):

```python
ponto_gps = (-23.5505, -46.6333)
cores_rgb = (255, 0, 0)
uma_constante = 10, 20 # Parênteses são opcionais em alguns contextos
```

### set

O conjunto (`set`) é uma coleção não ordenada de elementos únicos. Ele segue estritamente a definição matemática de conjuntos, não permitindo duplicatas. Se $S$ é um set:

$$S = \{ x \mid x \in \mathbb{U} \} \quad \text{onde } \forall a, b \in S, a \neq b$$

As variáveis do tipo `set` são definidas por chaves (exceto para conjuntos vazios, onde se usa `set()`):

```python
vogais = {'a', 'e', 'i', 'o', 'u'}
numeros_sem_repeticao = {1, 2, 2, 3, 3, 3} # O Python reduzirá para {1, 2, 3}
```

### dict

O dicionário (`dict`) representa um mapeamento (ou função finita) entre um conjunto de chaves ($K$) e um conjunto de valores ($V$). Cada chave deve ser única e imutável (hashable).

$$D = \{ (k, v) \mid k \in K, v \in V \} \quad \text{onde } f(k) = v$$

As variáveis do tipo `dict` são definidas por pares chave-valor dentro de chaves:

```python
pessoa = {
    "nome": "Carlos",
    "idade": 30,
    "admin": False
}
codigos_erro = {404: "Not Found", 500: "Server Error"}
```

## Operadores

Operadores são símbolos especiais que realizam computações em operandos.

### Aritméticos

Realizam operações matemáticas fundamentais. Dado $x, y \in \mathbb{R}$:

| **Operador** | **Nome**        | **Descrição Matemática**                        |
| ------------ | --------------- | ----------------------------------------------- |
| `+`          | Adição          | $x + y$                                         |
| `-`          | Subtração       | $x - y$                                         |
| `*`          | Multiplicação   | $x \times y$                                    |
| `/`          | Divisão Real    | $\frac{x}{y}$ (sempre retorna float)            |
| `//`         | Divisão Inteira | $\lfloor \frac{x}{y} \rfloor$ (piso da divisão) |
| `%`          | Módulo          | Resto da divisão de $x$ por $y$                 |
| `**`         | Exponenciação   | $x^y$                                           |


``` python
soma = 10 + 5        # 15
potencia = 2 ** 3    # 8
resto = 10 % 3       # 1
divisao_int = 10 // 3 # 3
```

### Comparação (Relacionais)

Comparam dois valores e retornam sempre um tipo `bool` (`True` ou `False`).

| **Operador** | **Descrição**  | **Exemplo (x=5,y=3)** |
| ------------ | -------------- | --------------------- |
| `==`         | Igual a        | `x == y` $\to$ False  |
| `!=`         | Diferente de   | `x != y` $\to$ True   |
| `>`          | Maior que      | `x > y` $\to$ True    |
| `<`          | Menor que      | `x < y` $\to$ False   |
| `>=`         | Maior ou igual | `x >= y` $\to$ True   |
| `<=`         | Menor ou igual | `x <= y` $\to$ False  |

```python
x = 10
y = 20
resultado = x != y  # True
```

### Lógicos

Usados para combinar declarações condicionais, baseados na lógica booleana.

| **Operador** | **Lógica**          | **Resultado**                                                 |
| ------------ | ------------------- | ------------------------------------------------------------- |
| `and`        | Conjunção ($\land$) | Retorna `True` se **ambas** as sentenças forem verdadeiras.   |
| `or`         | Disjunção ($\lor$)  | Retorna `True` se **pelo menos uma** sentença for verdadeira. |
| `not`        | Negação ($\neg$)    | Inverte o resultado (True vira False e vice-versa).           |

```python
tem_saldo = True
tem_limite = False

pode_comprar = tem_saldo or tem_limite  # True
negacao = not tem_saldo                 # False
```

### Pertencimento (Membership)

Operadores usados para verificar a existência de um valor dentro de uma sequência (como listas, strings, tuplas). Matematicamente, testam a relação de pertinência em conjuntos: $x \in A$.

| **Operador** | **Descrição**                                          | **Exemplo (L=[1,2,3])** |
| ------------ | ------------------------------------------------------ | ----------------------- |
| `in`         | Retorna `True` se o valor for encontrado na sequência. | `2 in L` $\to$ True     |
| `not in`     | Retorna `True` se o valor **não** for encontrado.      | `5 not in L` $\to$ True |
```python
lista_convidados = ["Ana", "Pedro", "João"]
print("Ana" in lista_convidados)   # True
print("Maria" in lista_convidados) # False
```

### Identidade

Operadores usados para comparar a localização na memória de dois objetos. Eles não verificam apenas se os _valores_ são iguais (para isso usa-se `==`), mas se as variáveis referenciam o **mesmo objeto**.

Seja $id(x)$ o endereço de memória da variável $x$:

|**Operador**|**Descrição**|**Lógica**|
|---|---|---|
|`is`|Retorna `True` se as variáveis apontam para o mesmo objeto.|$id(x) = id(y)$|
|`is not`|Retorna `True` se as variáveis apontam para objetos distintos.|$id(x) \neq id(y)$|
```python
# Listas iguais em conteúdo, mas objetos diferentes na memória
x = [1, 2, 3]
y = [1, 2, 3]

print(x == y)  # True (conteúdos iguais)
print(x is y)  # False (endereços de memória diferentes)

# Atribuição por referência
z = x
print(x is z)  # True (z aponta para o mesmo local de x)
```

---

