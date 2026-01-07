
Para uma explicação e procura rápida, acesse:
[Python Básico - Cheat Sheet](https://github.com/maahngg/DS-Study-Notes/blob/main/B%C3%A1sico/Python%20B%C3%A1sico%20-%20Cheat%20Sheet.md) - (GitHub: link externo)
[[Python Básico - Cheat Sheet]] - (Obsidian: link interno) 

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

# Estruturas

## Estruturas Condicionais

### Declaração `if` (Se)

É a estrutura fundamental de decisão. O bloco de código indentado só será executado se, e somente se, a condição testada for avaliada como `True`.

Matematicamente, seja $P$ a proposição (condição) e $A$ a ação:

$$P \implies A \quad (\text{Se } P \text{ é verdade, então } A \text{ acontece})$$

```python
temperatura = 30

if temperatura > 25:
    # Este bloco só executa se a condição for True
    print("Está calor, ligue o ar condicionado.")
```

### Declaração `if-else` (Se-Senão)

Esta estrutura introduz uma bifurcação exclusiva. Ela garante que **exatamente um** dos dois blocos de código será executado. Se a condição for verdadeira, executa o primeiro bloco; caso contrário ($\neg P$), executa o segundo.

Lógica proposicional:

$$(P \implies A) \land (\neg P \implies B)$$

```python
saldo = 50.00
preco_produto = 120.00

if saldo >= preco_produto:
    print("Compra aprovada.")
else:
    # Executa se saldo < preco_produto
    print("Saldo insuficiente.")
```

### Declaração `elif` (Senão-Se)

O `elif` (abreviação de _else if_) permite verificar múltiplas condições sequencialmente. O Python testa as condições de cima para baixo. Assim que encontra uma condição `True`, ele executa o bloco correspondente e **ignora** todo o restante da estrutura.

Sejam $P_1, P_2, ..., P_n$ as condições:

1. Se $P_1$ é verdade $\to$ Ação 1.
2. Senão, se $P_2$ é verdade $\to$ Ação 2.
3. Senão (nenhuma anterior) $\to$ Ação Padrão (else final).

```python
pontuacao = 85

if pontuacao >= 90:
    nota = "A"
elif pontuacao >= 80:
    nota = "B" # O código entra aqui e para, ignorando o resto
elif pontuacao >= 70:
    nota = "C"
else:
    nota = "D"

print(f"Sua nota é {nota}")
```

## Estruturas de Repetição (Loops)

### O Laço `for`

O laço `for` em Python é usado para iteração **determinada**. Ele percorre itens de qualquer objeto iterável (como listas, strings, tuplas ou dicionários) na ordem em que aparecem.

Matematicamente, dado um conjunto sequencial $S = \{x_1, x_2, ..., x_n\}$:

$$\forall x_i \in S, \text{ execute } f(x_i)$$
#### Iterando sobre coleções

A variável de iteração assume o valor de cada elemento da coleção, um por vez.

```python
tecnologias = ["Python", "Django", "Pandas"]

for tech in tecnologias:
    print(tech) 
    # 1ª iteração: tech = "Python"
    # 2ª iteração: tech = "Django"...
```

#### A função `range()`

Para gerar sequências numéricas, utiliza-se a função `range(start, stop, step)`.

- **start**: Início da sequência (inclusivo). Padrão é 0.
- **stop**: Fim da sequência (**exclusivo** - o número final não entra).
- **step**: Passo (incremento). Padrão é 1.


$$R = \{ k \in \mathbb{Z} \mid start \le k < stop \}$$

```python
# Gera: 0, 1, 2, 3, 4
for i in range(5):
    print(i)

# Gera: 10, 20, 30, 40 (De 10 até 50, pulando de 10 em 10)
for i in range(10, 50, 10):
    print(i)
```

### O Laço `while`

O laço `while` é usado para iteração **indeterminada**. Ele repete o bloco de código enquanto uma condição lógica (booleana) for verdadeira. É ideal quando não sabemos quantas vezes precisaremos repetir a ação (ex: aguardar input do usuário).

Lógica:

$$Enquanto \ P(estado) \text{ for Verdadeiro} \implies \text{Execute e Atualize } estado$$

**Atenção:** É crucial garantir que a condição eventualmente se torne `False`, caso contrário, cria-se um **Loop Infinito** (travamento do programa).

```python
contador = 0

while contador < 3:
    print(f"Contagem: {contador}")
    contador += 1  # Incremento essencial para quebrar o loop eventualmente
```

### Controle de Fluxo em Loops

Existem instruções específicas para alterar o comportamento natural de uma repetição.

#### `break`

Interrompe o laço imediatamente, ignorando qualquer código restante no bloco e saindo da estrutura de repetição.

```python
# Procura o número 5 e para ao encontrar
for numero in range(10):
    if numero == 5:
        print("Encontrado!")
        break 
    print(numero)
```

#### `continue`

Interrompe apenas a **iteração atual** e salta para a próxima verificação (no `while`) ou próximo elemento (no `for`).

```python
# Imprime apenas números ímpares (pula os pares)
for i in range(10):
    if i % 2 == 0:
        continue # Volta para o início do loop com o próximo 'i'
    print(i)
```

#### `pass`

É uma operação nula (placeholder). É usada quando a sintaxe exige um comando, mas você não quer executar nada naquele momento.

```python
for i in range(5):
    if i == 3:
        pass # Não faz nada, apenas "passa"
    else:
        print(i)
```

### Cláusula `else` em Loops

Python possui uma característica única onde loops podem ter um bloco `else`. Este bloco é executado **apenas se o loop terminar naturalmente** (ou seja, sem ser interrompido por um `break`).

```python
procurar = 11
numeros = [1, 5, 8, 10]

for n in numeros:
    if n == procurar:
        print("Achei!")
        break
else:
    # Só executa se o loop percorrer toda a lista sem dar 'break'
    print("Número não encontrado na lista.")
```
## Estruturas de Dados

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


---
# Importar Bibliotecas

O Python possui uma vasta biblioteca padrão ("batteries included"). Para utilizar funcionalidades que não estão carregadas nativamente, utilizamos a declaração `import`. Isso carrega módulos externos para o _namespace_ atual.

As principais formas de importação são:

1. **Importação Completa:** Importa todo o módulo.
2. **Importação Específica:** Importa apenas uma função ou classe específica.
3. **Aliasing (Apelido):** Renomeia o módulo para facilitar a escrita.

```python
import math              # Importa o módulo de matemática completo
from random import seed  # Importa apenas a função 'seed'
import pandas as pd      # Importa pandas com o apelido 'pd' (convenção em Data Science)

print(math.sqrt(16))     # Uso: modulo.funcao()

"""
Quando usamos:
from random import seed

Já estamos dizendo de onde ela vem, então só usamos seed, no código.
"""
seed(42)
```

## Gerenciamento de Pacotes (PIP)

O **PIP** (_Pip Installs Packages_) é o gerenciador de pacotes padrão do Python. Ele conecta sua máquina ao **PyPI** (Python Package Index), um repositório público que hospeda centenas de milhares de bibliotecas de terceiros.

**Importante:** Os comandos do PIP devem ser executados no **Terminal** (CMD, PowerShell ou Bash), e **não** dentro do interpretador Python (onde se escreve o código).

### Instalação Básica

Para instalar uma biblioteca, utilize a sintaxe:

```
pip install nome_do_pacote
```

Exemplo prático (instalando a biblioteca `requests` para requisições HTTP):

```
pip install requests
```
*Após a conclusão (download e instalação), você poderá utilizar `import requests` no seu script Python.*

# Funções

Uma função é um bloco de código reutilizável projetado para realizar uma tarefa específica. Matematicamente, uma função computacional pode ser vista como um mapeamento de um domínio de entrada para uma imagem de saída (embora em programação, funções possam ter efeitos colaterais e não retornar valores).

Seja $f$ a função, $x$ os argumentos (input) e $y$ o retorno (output):

$$y = f(x)$$

## Built-in (Funções Nativas)

O interpretador Python já traz consigo diversas funções pré-definidas disponíveis globalmente.

|**Função**|**Descrição**|**Exemplo Matemático / Lógico**|
|---|---|---|
|`print()`|Exibe dados na saída padrão (console).|$Output \leftarrow x$|
|`input()`|Captura dados da entrada padrão como **string**.|$x \leftarrow Input$|
|`len()`|Retorna o comprimento (cardinalidade) de um objeto.|$|
|`type()`|Retorna a classe (tipo) do objeto.|$x \in \mathbb{Z} \implies \text{<class 'int'>}$|
|`abs()`|Retorna o valor absoluto.|$|
|`sum()`|Retorna a soma de um iterável numérico.|$\sum_{i=1}^{n} x_i$|
|`help()`|Invoca o sistema de ajuda integrado.|Documentação|

```python
texto = "Física"
tamanho = len(texto)      # 6
tipo = type(tamanho)      # <class 'int'>
print(f"A palavra tem {tamanho} letras.")
```

## Criar Funções (`def`)

Para definir novas funções, utiliza-se a palavra-chave `def`, seguida do nome da função, parênteses com parâmetros e dois pontos. O corpo da função deve ser **indentado**.

A estrutura básica é:

```python
def nome_da_funcao(parametro1, parametro2):
    """Docstring: Explicação do que a função faz."""
    resultado = parametro1 + parametro2
    return resultado # O valor que sai da função
```

### Tipos de Argumentos e Parâmetros

Na definição e chamada de funções, a passagem de parâmetros pode ocorrer de diferentes formas:

1. **Posicionais:** A ordem dos argumentos importa. $f(a, b) \neq f(b, a)$ (geralmente).
2. **Nomeados (Keyword):** Explicita-se o nome do parâmetro na chamada. A ordem torna-se irrelevante.
3. **Padrão (Default):** O parâmetro assume um valor pré-definido se nenhum argumento for enviado.

```python
def velocidade_media(deslocamento, tempo=1):
    # 'tempo' tem valor padrão de 1 se não for informado
    return deslocamento / tempo

# Chamada Posicional
v1 = velocidade_media(100, 2)  # 50.0

# Chamada Nomeada (Keyword)
v2 = velocidade_media(tempo=2, deslocamento=100) # 50.0

# Uso do valor Default
v3 = velocidade_media(50) # 50.0 (dividiu por 1)
```

### Classificação de Funções (Argumentos e Retorno)

Podemos classificar as funções em quatro categorias fundamentais, baseadas no fluxo de dados de entrada ($Input$) e saída ($Output$).

Seja $f$ a função, $A$ o conjunto de argumentos (Input) e $R$ o conjunto de retorno (Output).

#### 1. Sem Argumento e Sem Retorno

Estas funções executam uma rotina fixa e não comunicam um resultado ao programa principal. Elas dependem apenas de efeitos colaterais (como imprimir na tela ou escrever em um log).

- **Matematicamente:** $f: \emptyset \to \emptyset$ (Ação pura)
- **Uso:** Menus, mensagens de boas-vindas estáticas, configurações iniciais.

```python
def exibir_logo():
    print("--- SISTEMA INICIADO ---")
    print("Bem-vindo ao Python")
    # Não há 'return', logo retorna None implicitamente

exibir_logo() # Chamada simples
```

#### 2. Com Argumento e Sem Retorno

A função recebe dados externos para modular seu comportamento, mas ainda opera baseada em efeitos colaterais, sem devolver um valor utilizável para uma variável.

- **Matematicamente:** $f(x) \to \text{Ação}(x)$
- **Uso:** Enviar um pacote de rede (onde o sucesso é logado, mas não retornado), salvar dados em arquivo, exibir mensagens personalizadas.

```python
def saudacao_personalizada(nome):
    print(f"Olá, {nome}. Acesso liberado.")

saudacao_personalizada("Carlos") # O input "Carlos" altera a execução
# variavel = saudacao_personalizada("Carlos") -> 'variavel' seria None
```

#### 3. Sem Argumento e Com Retorno

A função não precisa de dados externos para trabalhar. Geralmente, ela recupera um estado interno do sistema, gera um valor aleatório ou retorna uma constante. É uma função "geradora".

- **Matematicamente:** $y = f(\emptyset)$ ou $y = constant$
- **Uso:** Obter data/hora atual, ler um sensor conectado, gerar números aleatórios, retornar valor de $\pi$.

```python
import random

def jogar_dado():
    # Não precisa de input, ela gera o dado internamente
    return random.randint(1, 6)

resultado = jogar_dado() # O valor capturado é armazenado na variável
print(f"O dado caiu em: {resultado}")
```

#### 4. Com Argumento e Com Retorno

É a definição clássica de função em matemática e computação. Ela recebe dados brutos, processa (transforma) e devolve um novo dado. É considerada uma **Função Pura** se o mesmo input sempre gerar o mesmo output sem efeitos colaterais.

- **Matematicamente:** $y = f(x)$
- **Uso:** Cálculos físicos, conversão de unidades, tratamento de strings.

```python
def calcular_forca(massa, aceleracao):
    """Calcula a força baseada na 2ª Lei de Newton (F = m * a)"""
    f = massa * aceleracao
    return f

# O fluxo de dados é completo: Entrada -> Processamento -> Saída
f_resultante = calcular_forca(10, 9.8)
print(f"A força resultante é {f_resultante} N")
```

##### Argumentos Arbitrários (`*args` e `**kwargs`)

Utilizados quando não se sabe antecipadamente quantos argumentos serão passados.

- `*args`: Recebe múltiplos argumentos posicionais como uma **tupla**.
- `**kwargs`: Recebe múltiplos argumentos nomeados como um **dicionário**.

```python
def somar_todos(*args):
    # args é tratado como uma tupla: (1, 2, 3, 4)
    return sum(args)

print(somar_todos(1, 2, 3, 4)) # 10
```

### Funções Lambda (Anônimas)

As funções lambda são pequenas funções anônimas (sem nome) definidas em uma única linha. São restritas a uma única expressão.

Sintaxe matemática análoga ($\lambda$-calculus):

$$x \mapsto x^2 \quad (\text{Mapeia } x \text{ para } x^2)$$

Sintaxe Python:

lambda argumentos: expressao

Elas são frequentemente usadas onde objetos de função são necessários (como em `map`, `filter` ou ordenação personalizada), ou para encapsular fórmulas matemáticas simples de forma concisa.

```python
# Função tradicional
def quadrado(x):
    return x ** 2

# Função Lambda equivalente
quadrado_lambda = lambda x: x ** 2

print(quadrado_lambda(5)) # 25

# Exemplo prático: Cálculo rápido em lista
numeros = [1, 2, 3, 4]
# Eleva todos ao quadrado usando map()
ao_quadrado = list(map(lambda x: x**2, numeros)) 
# Resultado: [1, 4, 9, 16]
```

---

# Estrutura de Dados II

## Matrizes (Lista de Listas)

Em Python, não existe um tipo de dado primitivo exclusivo para arrays multidimensionais (como em C ou Fortran). Para representar uma **Matriz** matemática, utilizamos o conceito de aninhamento (_nesting_): uma lista onde cada elemento é, por sua vez, outra lista.

Matematicamente, seja $A$ uma matriz de ordem $m \times n$ (m linhas e n colunas):

$$A = \begin{pmatrix} a_{0,0} & a_{0,1} & \cdots & a_{0,n-1} \\ a_{1,0} & a_{1,1} & \cdots & a_{1,n-1} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m-1,0} & a_{m-1,1} & \cdots & a_{m-1,n-1} \end{pmatrix}$$

Para acessar um elemento $a_{i,j}$ (linha $i$, coluna $j$), utilizamos a sintaxe de duplo índice: `matriz[i][j]`.

```python
# Representação de uma Matriz Identidade 3x3
# Cada sub-lista representa uma linha da matriz
identidade = [
    [1, 0, 0],  # Linha 0
    [0, 1, 0],  # Linha 1
    [0, 0, 1]   # Linha 2
]

# Acessando o elemento da linha 1, coluna 1 (o centro)
elemento_central = identidade[1][1]  # 1

# Percorrendo uma matriz (Iteração aninhada)
for linha in identidade:
    for elemento in linha:
        print(elemento, end=' ')
    print() # Quebra de linha visual
```

## Lista de Tuplas

Esta estrutura é frequentemente utilizada para representar conjuntos de dados estruturados e imutáveis dentro de uma coleção mutável. É análoga a uma tabela em um banco de dados relacional, onde a **Lista** representa a tabela e cada **Tupla** representa um registro (linha) fixo.

Seja $L$ a lista de pares ordenados $(x, y)$:

$$L = [ (x_0, y_0), (x_1, y_1), \dots, (x_n, y_n) ]$$

Como tuplas são imutáveis, isso garante a integridade dos dados individuais, enquanto a lista permite ordenar ou filtrar os registros.

```python
# Lista de coordenadas GPS (Latitude, Longitude)
coordenadas = [
    (-23.5505, -46.6333), # São Paulo
    (40.7128, -74.0060),  # Nova York
    (35.6895, 139.6917)   # Tóquio
]

# Acessando dados
primeira_cidade = coordenadas[0] # (-23.5505, -46.6333)
latitude_sp = coordenadas[0][0]  # -23.5505
```

## List Comprehension (Compreensão de Lista)

A _List Comprehension_ é uma construção sintática que permite criar listas a partir de iteráveis existentes de forma concisa. Ela é diretamente inspirada na **Notação de Construção de Conjuntos** da matemática.

Seja $S$ o conjunto que desejamos criar, formado aplicando uma função $f(x)$ a elementos de um domínio $D$, tal que uma condição $P(x)$ seja verdadeira:

$$S = \{ f(x) \mid x \in D \land P(x) \}$$

Em Python, a sintaxe reflete quase exatamente essa definição: `[ f(x) for x in D if P(x) ]`

### Vantagens

- **Concisão:** Substitui blocos de `for` e `append` de múltiplas linhas. 
- **Performance:** Geralmente mais rápida que laços `for` tradicionais, pois a iteração é otimizada internamente em C.

```python
numeros = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Método Clássico (Imperativo)
quadrados_pares = []
for x in numeros:
    if x % 2 == 0:
        quadrados_pares.append(x ** 2)

# List Comprehension (Declarativo)
# "Gere x ao quadrado PARA CADA x EM numeros SE x for par"
quadrados_pares_comp = [x**2 for x in numeros if x % 2 == 0]

# Resultado: [0, 4, 16, 36, 64]
```

## Dict Comprehension

Seguindo a mesma lógica matemática, podemos construir dicionários (mapeamentos) de forma programática.

Seja $M$ um mapeamento de chaves $k$ para valores $v$:

$$M = \{ k: v \mid k \in K, v = f(k) \}$$

Sintaxe: `{ chave: valor for item in iteravel if condicao }`

```python
nomes = ['Ana', 'Bruno', 'Carla']

# Cria um dicionário mapeando o nome ao seu tamanho (len)
# { 'Ana': 3, 'Bruno': 5, 'Carla': 5 }
mapa_nomes = {nome: len(nome) for nome in nomes}

# Exemplo: Invertendo chaves e valores de um dicionário existente
original = {'a': 1, 'b': 2}
invertido = {valor: chave for chave, valor in original.items()}
# Resultado: {1: 'a', 2: 'b'}
```


---

# Erros e Exceções

Na programação, assim como na física experimental, nem tudo ocorre em condições ideais. Existem dois tipos principais de erros que interrompem a execução de um programa:

1. **Erros de Sintaxe (_Parsing Errors_):** Ocorrem quando o código viola a gramática da linguagem (ex: esquecer os dois pontos `:` após um `if`). O interpretador nem chega a executar o programa.
2. **Exceções (_Runtime Errors_):** Ocorrem durante a execução. A sintaxe está correta, mas a instrução gera um estado inválido ou impossível (ex: tentar dividir por zero ou acessar um índice inexistente em uma lista).

Matematicamente, uma exceção é um evento que desvia o fluxo de controle do caminho normal ($N$) para um caminho de tratamento de erro ($E$).

## Tipos de Exceções

O Python possui uma hierarquia de classes de exceção. Abaixo estão as mais comuns no contexto de ciência de dados e TI:

|**Exceção**|**Descrição**|**Analogia Matemática/Física**|
|---|---|---|
|`ZeroDivisionError`|Tentativa de divisão por zero.|Singularidade ($x \to \infty$).|
|`IndexError`|Acesso a um índice fora dos limites de uma sequência.|$v_i$ onde $i \ge \text{dim}(v)$.|
|`KeyError`|Tentativa de acessar uma chave inexistente em um dicionário.|$f(k)$ onde $k \notin \text{Dom}(f)$.|
|`TypeError`|Operação aplicada a um objeto de tipo inadequado.|Somar um vetor com um escalar não definido ($\vec{v} + c$).|
|`ValueError`|A função recebe o tipo correto, mas um valor inapropriado.|$\sqrt{x}$ onde $x < 0$ (nos Reais).|
|`NameError`|Uso de uma variável que não foi definida.|Uso de uma variável livre não declarada.|

## Tratamento

O tratamento de exceções permite que o programa lide com erros de forma elegante (_graceful degradation_) em vez de travar abruptamente (_crash_).

### Try-Except

A estrutura `try-except` define um bloco de teste e um bloco de recuperação.

Seja $P$ o bloco de código protegido.

1. O Python tenta executar $P$.
2. Se $P$ for bem-sucedido, o fluxo segue.    
3. Se ocorrer uma exceção $e$ em $P$, a execução de $P$ para imediatamente e o bloco `except` correspondente é acionado.

```python
try:
    x = int(input("Digite um numerador: "))
    y = int(input("Digite um denominador: "))
    resultado = x / y
except ZeroDivisionError:
    # Captura especificamente erro de divisão por zero
    print("Erro: Indeterminação matemática. Não é possível dividir por zero.")
except ValueError:
    # Captura erro se o usuário digitar letras em vez de números
    print("Erro: O domínio de entrada deve ser números inteiros.")
except Exception as e:
    # Captura qualquer outro erro genérico não previsto
    print(f"Ocorreu um erro desconhecido: {e}")
```

#### else

O bloco `else` é opcional e é executado **estritamente se nenhuma exceção ocorrer** dentro do bloco `try`. É útil para separar o código que pode falhar do código que deve rodar apenas após o sucesso.

Lógica: $(Sucesso(P) \implies Executar(Else))$

```python
try:
    arquivo = open("dados.txt", "r")
except FileNotFoundError:
    print("Arquivo não encontrado.")
else:
    # Só executa se o arquivo abriu com sucesso
    conteudo = arquivo.read()
    print("Leitura realizada com sucesso.")
    arquivo.close()
```

#### finally

O bloco `finally` é executado **sempre**, independentemente de ter ocorrido um erro ou não. Sua função primordial é a **limpeza de recursos** (fechar conexões de banco de dados, fechar arquivos, liberar memória), garantindo que o sistema não fique em um estado inconsistente.

Lógica: $\forall \text{resultado} (Sucesso \lor Falha), Executar(Finally)$

```python
try:
    numero = float(input("Digite um número: "))
    inverso = 1 / numero
except ZeroDivisionError:
    print("Impossível calcular o inverso de zero.")
else:
    print(f"O inverso é {inverso}")
finally:
    # Esta mensagem aparecerá em todos os casos
    print("--- Fim da operação de cálculo ---")
```

### Raise

A palavra-chave `raise` permite que o programador force a ocorrência de uma exceção. Isso é utilizado para reforçar regras de negócio ou restrições físicas que a linguagem, por si só, não barraria.

Matematicamente, é a imposição de restrições ao domínio de uma função.

Se definimos que a massa $m$ deve ser estritamente positiva ($m \in \mathbb{R}^+$), devemos "levantar" (raise) um erro se o usuário fornecer $m \le 0$.

```python
def calcular_energia_cinetica(massa, velocidade):
    if massa < 0:
        # Forçamos um erro pois massa negativa não faz sentido na mecânica clássica
        raise ValueError("A massa não pode ser negativa.")
    
    return 0.5 * massa * (velocidade ** 2)

try:
    ec = calcular_energia_cinetica(-10, 20)
except ValueError as erro:
    print(f"Erro de Física: {erro}") 
    # Saída: Erro de Física: A massa não pode ser negativa.
```