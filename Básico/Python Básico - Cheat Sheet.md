
# 🐍 Python Cheat Sheet

Resumo rápido de sintaxe, estruturas de dados e comandos essenciais para o dia a dia.

## 1. Variáveis e Regras

Variáveis são espaços de memória com **tipagem dinâmica** (o tipo é definido automaticamente pelo valor atribuído na linha `variavel = valor`).

- **Nomenclatura:** Use `snake_case` (tudo minúsculo separado por _underline_).
- **Constantes:** Use `MAIUSCULAS` para indicar valores que não devem ser alterados.
- **Case-sensitive:** O Python diferencia maiúsculas de minúsculas (`texto` é diferente de `Texto`).
- **Regra de Ouro:** Nunca use nomes de funções nativas (como `print`, `list`, `str`) como nome de variável.

```python
idade = 25              # Inteiro
NOME_PADRAO = "USER"    # Constante (convenção)
nome_completo = "Ana"   # snake_case
```

## 2. Tipos de Dados Primitivos

|**Tipo**|**Descrição Prática**|**Exemplo**|
|---|---|---|
|**int**|Números inteiros (sem casa decimal)|`x = -5`, `y = 1000`|
|**float**|Números reais (com ponto flutuante/decimal)|`peso = 69.5`, `pi = 3.14`|
|**bool**|Booleano (Lógica: Verdadeiro ou Falso)|`ativo = True`, `off = False`|
|**str**|String (Texto entre aspas)|`s = "Texto"`, `n = '100'`|
|**complex**|Números complexos (usa `j` para a parte imaginária)|`z = 2 + 3j`|

## 3. Operadores

### Aritméticos

|**Símbolo**|**Ação**|**Exemplo**|**Resultado**|
|---|---|---|---|
|`+` / `-`|Soma / Subtração|`10 + 5`|15|
|`*`|Multiplicação|`2 * 3`|6|
|`/`|Divisão Real (sempre retorna float)|`10 / 2`|5.0|
|`//`|Divisão Inteira (ignora o decimal)|`10 // 3`|3|
|`%`|Módulo (Resto da divisão)|`10 % 3`|1|
|`**`|Potência / Exponenciação|`2 ** 3`|8|

### Lógicos e Comparação

O resultado dessas operações é sempre um `bool` (`True` ou `False`).

- **Comparação:** `==` (igual), `!=` (diferente), `>` (maior), `<` (menor), `>=` (maior igual), `<=` (menor igual).

- **Lógicos:**

    - `and`: Verdadeiro se **ambos** forem verdadeiros.
        
    - `or`: Verdadeiro se **pelo menos um** for verdadeiro.
        
    - `not`: Inverte o valor (True vira False).

### Identidade e Pertencimento

- **`in` / `not in`:** Verifica se um valor existe dentro de uma sequência (lista, string, tupla).
- **`is` / `is not`:** Verifica se duas variáveis apontam para o **mesmo objeto** na memória, não apenas se os valores são iguais.

```python
lista = [1, 2, 3]
print(1 in lista)    # True
print(lista is lista) # True
```

## 4. Estruturas Condicionais

O fluxo segue a lógica se-senão. O código deve ser **indentado**.

```python
if condicao:
    # Executa se True
elif outra_condicao:
    # Executa se a primeira for False e esta for True
else:
    # Executa se nenhuma anterior for True
```

## 5. Loops (Repetição)

### `for` (Iteração Determinada)

Percorre itens de uma coleção ou sequência.

Utiliza range(start, stop, step) para sequências numéricas (o valor final stop não é incluído).

```python
for i in range(0, 10, 2): # Gera: 0, 2, 4, 6, 8
    print(i)
```

### `while` (Iteração Indeterminada)

Repete enquanto a condição for `True`. Cuidado com loops infinitos.

```python
while contador < 5:
    contador += 1
```

### Controle de Loop

- **`break`**: Interrompe e sai do loop imediatamente.
- **`continue`**: Pula a iteração atual e vai para a próxima.
- **`pass`**: Placeholder (não faz nada).
- **`else` em loops**: Executa apenas se o loop terminar naturalmente (sem `break`).

## 6. Estruturas de Dados (Coleções)

### Básicas

|**Estrutura**|**Sintaxe**|**Mutável?**|**Ordenada?**|**Duplicatas?**|**Características**|
|---|---|---|---|---|---|
|**List**|`[a, b]`|Sim|Sim|Sim|Sequência geral.|
|**Tuple**|`(a, b)`|**Não**|Sim|Sim|Lista imutável (constante).|
|**Set**|`{a, b}`|Sim|Não|**Não**|Elementos únicos.|
|**Dict**|`{k: v}`|Sim|-|Chaves não|Mapeamento Chave-Valor.|

### Avançadas

- **Matrizes (Lista de Listas):** Como o Python não tem array nativo multidimensional, usamos listas aninhadas. Acesso via `matriz[linha][coluna]`.
- **List Comprehension:** Cria listas de forma concisa. Sintaxe: `[resultado for item in iteravel if condicao]`.
- **Dict Comprehension:** Cria dicionários de forma concisa. Sintaxe: `{chave: valor for item in iteravel}`.

```python
# List Comprehension: Apenas pares ao quadrado
quadrados_pares = [x**2 for x in range(10) if x % 2 == 0]

# Dict Comprehension: Nome -> Tamanho do nome
nomes = ["Ana", "Bob"]
mapa = {nome: len(nome) for nome in nomes} # {'Ana': 3, 'Bob': 3}
```

## 7. Funções

Blocos reutilizáveis definidos por `def`. Podem retornar valores com `return`.

### Argumentos

- **Posicionais:** A ordem importa.
- **Nomeados:** Usa-se o nome do parâmetro (`func(a=1)`), a ordem não importa.
- **Default:** Parâmetros com valor padrão se não forem passados.
- **`*args`:** Recebe múltiplos argumentos como uma **Tupla**.
- **`**kwargs`:** Recebe múltiplos argumentos nomeados como um **Dicionário**.

### Lambda (Anônimas)

Funções de uma linha para expressões simples.

```python
quadrado = lambda x: x ** 2
print(quadrado(5)) # 25
```

## 8. Importar Bibliotecas

Para usar códigos externos ou módulos do sistema.

- **Instalar Pacote:** No terminal, use `pip install nome_pacote`.
- **Importar no Código:**

``` python
    import math              # Importa módulo completo
    from random import seed  # Importa apenas uma função
    import pandas as pd      # Importa com apelido (alias)
```


## 9. Tratamento de Erros (`try-except`)

Previne o fechamento do programa quando ocorrem exceções (erros de execução).

```python
try:
    # Código que pode dar erro
    x = 10 / 0
except ZeroDivisionError:
    # Executa se o erro for divisão por zero
    print("Erro: Divisão por zero.")
except Exception as e:
    # Executa para qualquer outro erro genérico
    print(f"Erro desconhecido: {e}")
else:
    # Executa APENAS se o bloco 'try' não der erro
    print("Sucesso!")
finally:
    # Executa SEMPRE (útil para fechar arquivos/conexões)
    print("Fim da operação.")
```

- **`raise`:** Força um erro propositalmente. Útil para validar regras de negócio (ex: `raise ValueError("Idade inválida")`).