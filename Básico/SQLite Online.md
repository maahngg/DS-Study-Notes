# SQLite Online

## SQL

SQL vem do inglês _Structured Query Language_ que, traduzindo para o português, seria uma Linguagem de Consulta Estruturada.

Mais do que apenas uma linguagem de programação, o SQL é o **padrão internacional** para interagir com bancos de dados. Diferente de linguagens como Python ou Java, onde você diz ao computador _como_ fazer algo passo a passo, o SQL é uma linguagem declarativa: você diz ao banco de dados _o que_ você quer, e ele decide a melhor maneira de buscar essa informação.

As principais operações realizadas com SQL são conhecidas pelo acrônimo **CRUD**:

- **Create (INSERT):** Inserir novos dados.
- **Read (SELECT):** Consultar ou ler dados existentes.
- **Update (UPDATE):** Atualizar dados.
- **Delete (DELETE):** Remover dados.


**Bancos de Dados Relacionais**

Para entender o poder do SQL, é fundamental entender onde ele é aplicado: nos **Bancos de Dados Relacionais**.

A ideia central deste modelo, proposto por Edgar F. Codd na década de 70, é organizar os dados em **tabelas** (semelhantes a planilhas de Excel), que possuem:

- **Colunas (Atributos):** Definem o tipo de dado (ex: Nome, Idade, Preço).
- **Linhas (Registros):** Contêm os dados reais de cada item.

### Por que o SQL funciona bem aqui?

O termo "Relacional" vem da capacidade de criar relacionamentos entre essas tabelas através de **chaves**. Por exemplo, uma tabela de _Vendas_ pode se relacionar com uma tabela de _Clientes_ através do ID do cliente.

O SQL foi desenhado especificamente para navegar nessas estruturas rígidas. Ele permite "cruzar" (fazer _joins_) dados de múltiplas tabelas instantaneamente, garantindo a integridade dos dados (por exemplo, impedindo que você venda um produto para um cliente que não existe).

### O que é um SGBD?

Enquanto o SQL é a _linguagem_ que falamos, o **SGBD** (Sistema Gerenciador de Banco de Dados) é o _software_ que escuta essa linguagem e executa o trabalho pesado.

O SGBD serve como uma interface entre o usuário final (ou uma aplicação) e os dados armazenados fisicamente no disco. Suas responsabilidades incluem:

1. **Segurança:** Controlar quem pode acessar ou alterar os dados.
2. **Concorrência:** Permitir que milhares de usuários acessem os dados ao mesmo tempo sem conflitos.
3. **Recuperação:** Garantir que os dados não sejam perdidos em caso de falha de energia ou erro do sistema.

#### Exemplos de SGBD

Existem diversos SGBDs no mercado que "falam" SQL, cada um com suas peculiaridades:

- **SQLite:** Um motor de banco de dados leve e autônomo (foco deste documento).
- **PostgreSQL:** Um sistema _open-source_ muito robusto e avançado.
- **MySQL:** Muito popular na web.
- **Oracle Database** e **SQL Server:** Soluções corporativas de grande porte.

### Comandos Essenciais: Estrutura e Consulta

Agora que entendemos o conceito de banco de dados relacional e o papel do SGBD, vamos colocar a mão na massa com os comandos fundamentais do SQL.

#### CREATE TABLE (Criando a Estrutura)

Antes de podermos inserir ou consultar qualquer dado, precisamos definir a estrutura onde esses dados viverão. No modelo relacional, isso significa criar uma **Tabela**.

O comando `CREATE TABLE` define o "esqueleto" da tabela. Você precisa dar um nome à tabela e definir quais colunas (atributos) ela terá, bem como o tipo de dado de cada coluna.

**Sintaxe Básica:**

```sql
CREATE TABLE nome_da_tabela (
    coluna1 tipo_do_dado,
    coluna2 tipo_do_dado,
    coluna3 tipo_do_dado
);
```

**Exemplo Prático:** Imagine criar uma tabela para guardar informações de clientes.

```sql
CREATE TABLE Clientes (
    ID INTEGER PRIMARY KEY,
    Nome TEXT,
    Idade INTEGER,
    Cidade TEXT
);
```

_Neste exemplo, definimos que o ID é um número inteiro, o Nome é texto, a Idade é um inteiro e a Cidade é texto._

#### SELECT (Consultando Dados)

O `SELECT` é, sem dúvida, o comando mais utilizado em SQL. Ele corresponde ao "Read" do acrônimo CRUD. É com ele que fazemos perguntas ao banco de dados para recuperar informações.

Podemos selecionar colunas específicas (o que é ideal para performance) ou todas as colunas de uma vez.

**Sintaxe Básica:**

```sql
SELECT coluna1, coluna2 FROM nome_da_tabela;
```

**O uso do Asterisco (*):** Muitas vezes você verá o símbolo `*`. Ele funciona como um "curinga" que significa "todas as colunas".

```sql
-- Seleciona TUDO da tabela Clientes
SELECT * FROM Clientes;

-- Seleciona APENAS o nome e a cidade (mais eficiente)
SELECT Nome, Cidade FROM Clientes;
```

#### DISTINCT (Eliminando Duplicatas)

Muitas vezes, uma tabela contém dados repetidos em certas colunas. Por exemplo, em uma tabela de `Clientes`, várias pessoas podem morar na mesma cidade.

Se você quiser saber **apenas** quais cidades possuem clientes, sem ver o nome da cidade repetido várias vezes, usamos o `DISTINCT`. Ele filtra o resultado da consulta para mostrar apenas valores únicos.

**Exemplo:**

```sql
-- Retorna uma lista de cidades únicas onde há clientes
SELECT DISTINCT Cidade FROM Clientes;
```

_Se houver 10 clientes em "São Paulo" e 5 no "Rio de Janeiro", o resultado mostrará "São Paulo" e "Rio de Janeiro" apenas uma vez cada._

#### WHERE (Filtrando Resultados)

Raramente queremos ler _todos_ os dados de uma tabela de uma só vez. Geralmente, queremos encontrar algo específico: um cliente pelo nome, produtos abaixo de um certo preço, ou vendas realizadas em uma data específica.

A cláusula `WHERE` age como um filtro. Ela diz ao banco de dados: "Traga os dados, mas **apenas** onde esta condição for verdadeira".

**Operadores Comuns:**

- `=` (Igual a)
- `<>` ou `!=` (Diferente de)
- `>` (Maior que)
- `<` (Menor que)
- `>=` (Maior ou igual a)
- `<=` (Menor ou igual a)

**Exemplos:**

1. **Filtrando por texto:**

 ```sql
 SELECT * FROM Clientes WHERE Cidade = 'Rio de Janeiro';
 ```

2. **Filtrando por número:**

 ```sql
 SELECT Nome, Idade FROM Clientes WHERE Idade > 18;
 ```

3. **Combinando filtros (AND / OR):** Você pode refinar ainda mais a busca usando `AND` (ambas as condições devem ser verdadeiras) ou `OR` (pelo menos uma deve ser verdadeira).

```sql
   -- Clientes do Rio de Janeiro QUE TAMBÉM tenham mais de 18 anos
   SELECT * FROM Clientes
   WHERE Cidade = 'Rio de Janeiro' AND Idade > 18;
```
