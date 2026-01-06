
# 🐍 Python Cheat Sheet: Variáveis e Tipos

Resumo rápido de sintaxe e estruturas de dados básicas.

## 1. Variáveis e Convenções
O Python é **case-sensitive** (`texto` $\neq$ `Texto`).

```python
# Atribuição
x = 10                  # Tipo inferido automaticamente (Dinâmico)

# Convenções de Nomenclatura
nome_variavel = "Valor" # snake_case (Padrão para variáveis)
CONSTANTE_PI = 3.1415   # UPPER_CASE (Convenção para constantes)
_privado = "Interno"    # Começar com _ indica uso interno (convenção)
```

## 2. Tipos Primitivos

|**Tipo**|**Sintaxe Exemplo**|**Descrição**|
|---|---|---|
|**int**|`x = 10`|Inteiros (sem limite de tamanho).|
|**float**|`x = 10.5`|Ponto flutuante (Reais). Usa ponto `.`.|
|**bool**|`x = True`|Booleano. Sempre `True` ou `False`.|
|**complex**|`x = 2 + 3j`|Números complexos.|
|**str**|`x = "Olá"`|Strings. Aspas simples `'` ou duplas `"`.|
## 3. Estruturas de Dados (Coleções)

|**Estrutura**|**Sintaxe**|**Característica Principal**|**Mutável?**|
|---|---|---|---|
|**List**|`[1, "a", 3.5]`|Ordenada, permite duplicatas.|✅ Sim|
|**Tuple**|`(1, "a", 3.5)`|Ordenada, "lista constante".|❌ Não|
|**Set**|`{1, 2, 3}`|Não ordenada, **elementos únicos**.|✅ Sim|
|**Dict**|`{'chave': 'valor'}`|Mapeamento Chave $\to$ Valor.|✅ Sim|
```python
# Exemplos rápidos
lista  = [1, 2, 3]      
tupla  = (1, 2, 3)      
dados  = {'nome': 'Ana', 'id': 42}

# Acesso
print(lista[0])         # Acessa índice 0 -> 1
print(dados['nome'])    # Acessa pela chave -> 'Ana'
```

## 4. Conversão de Tipos (Casting)


```python
int("10")      # Converte string para inteiro -> 10
float(5)       # Converte int para float -> 5.0
str(100)       # Converte int para string -> "100"
list((1,2))    # Converte tupla para lista -> [1, 2]
```

## 5. Operadores

### Aritméticos

```python
x + y    # Soma
x - y    # Subtração
x * y    # Multiplicação
x / y    # Divisão (Sempre retorna float)
x // y   # Divisão Inteira (Ignora resto)
x % y    # Módulo (Resto da divisão)
x ** y   # Exponenciação
```

### Comparação (Retorna bool)

```python
x == y   # Igual
x != y   # Diferente
x > y    # Maior
x < y    # Menor
x >= y   # Maior ou igual
x <= y   # Menor ou igual
```

### Lógicos

```python
x and y  # True se ambos forem True
x or y   # True se pelo menos um for True
not x    # Inverte o valor (True vira False)
```

### Pertencimento e Identidade

```python
'a' in 'casa'    # True (verifica se existe dentro)
x is y           # True se x e y apontam para o mesmo objeto na memória
```