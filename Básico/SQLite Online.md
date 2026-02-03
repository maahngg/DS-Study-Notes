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

**A Hierarquia dos Dados**

Antes de criarmos objetos, precisamos entender que os SGBDs organizam as informações em níveis de contêineres:

1. **Database (Banco de Dados):** O contêiner de nível mais alto que agrupa todos os dados relacionados a um sistema ou aplicação.
2. **Schema (Esquema):** Uma camada lógica dentro do banco de dados que organiza as tabelas, funcionando como "pastas" para separar diferentes áreas (ex: esquema `vendas`, esquema `RH`).
3. **Table (Tabela):** Onde os dados residem de fato, organizados em linhas e colunas.

#### CREATE (Criando a Estrutura)

O comando `CREATE` é utilizado para dar vida a esses contêineres.

##### 1. CREATE DATABASE

Cria o ambiente principal onde tudo será armazenado.

```sql
CREATE DATABASE NomeDoBanco;
```

##### 2. CREATE SCHEMA

Utilizado para organizar grupos de tabelas dentro do banco.

```sql
CREATE SCHEMA NomeDoEsquema;
```

##### 3. CREATE TABLE

Define o "esqueleto" da tabela onde os registros serão inseridos. Você precisa definir o nome da tabela, suas colunas e os respectivos tipos de dados.

**Exemplo Prático:**

```sql
CREATE TABLE Clientes (
    ID INTEGER PRIMARY KEY,
    Nome TEXT,
    Idade INTEGER,
    Cidade TEXT
);
```

_Neste exemplo, definimos que o ID é um número inteiro, o Nome é texto, a Idade é um inteiro e a Cidade é texto._

**Entendendo a PRIMARY KEY (Chave Primária)**

Você deve ter notado o termo `PRIMARY KEY` ao lado da coluna `ID`. Este é um dos conceitos mais importantes em bancos de dados.

A **Chave Primária** é uma restrição que garante que a coluna escolhida sirva como o **identificador único** de cada linha da tabela. Ela segue duas regras de ouro:

1.  **Unicidade:** Não podem existir dois registros com o mesmo valor nesta coluna (ex: dois clientes não podem ter o mesmo ID).
2.  **Não Nulo:** O valor nunca pode ser vazio.

**Analogia:** Pense na Chave Primária como o **CPF** de uma pessoa. Podem existir várias pessoas com o nome "João Silva" e a mesma idade, mas o CPF é o que distingue um João do outro inequivocamente no sistema.

**Conectando Tabelas: A FOREIGN KEY (Chave Estrangeira)**

Se a Chave Primária identifica quem é quem, a **Chave Estrangeira** serve para criar um elo entre duas tabelas. É uma coluna (ou conjunto de colunas) em uma tabela que aponta para a Chave Primária de outra tabela.

Para ilustrar, vamos criar uma tabela de `Pedidos`. Cada pedido precisa pertencer a um cliente que já existe na tabela `Clientes` criada acima.

```sql
CREATE TABLE Pedidos (
    ID INTEGER PRIMARY KEY,
    DataPedido DATE,
    ValorTotal REAL,
    Cliente_ID INTEGER,
    FOREIGN KEY (Cliente_ID) REFERENCES Clientes(ID)
);
```

**O que este comando faz?**

- **`Cliente_ID INTEGER`:** Cria uma coluna para guardar o ID do cliente.
- **`FOREIGN KEY... REFERENCES...`:** Cria a regra de segurança (Restrição). O banco de dados agora sabe que o valor inserido em `Cliente_ID` na tabela de pedidos **OBRIGATORIAMENTE** precisa existir na coluna `ID` da tabela `Clientes`.

**Integridade Referencial:** Isso impede erros comuns, como cadastrar uma venda para um cliente que não existe ou excluir um cliente que ainda possui pedidos pendentes (o banco bloqueará a exclusão para não deixar o pedido "órfão").


#### INSERT (Inserindo Dados)

Agora que criamos o "esqueleto" das nossas tabelas, elas ainda estão vazias. O comando `INSERT` é utilizado para adicionar registros (linhas) a uma tabela. Ele corresponde ao "Create" do acrônimo CRUD.

Para inserir dados, precisamos dizer ao banco em qual tabela queremos entrar, quais colunas vamos preencher e, finalmente, quais os valores.

**Sintaxe Básica:**

```sql
INSERT INTO nome_da_tabela (coluna1, coluna2, coluna3)
VALUES (valor1, valor2, valor3);
```

**Exemplo Prático:**

Vamos inserir um novo cliente na tabela `Clientes` que criamos anteriormente.

```sql
INSERT INTO Clientes (ID, Nome, Idade, Cidade)
VALUES (1, 'Ana Pereira', 28, 'Curitiba');
```

**Pontos Importantes sobre o INSERT:**

- **Correspondência:** A ordem dos valores dentro de `VALUES` deve corresponder exatamente à ordem das colunas listadas entre parênteses após o nome da tabela.
- **Tipos de Dados:** Se a coluna espera um número (INTEGER), não envie texto. Se espera texto (TEXT), lembre-se de colocar o valor entre aspas simples (`'texto'`).
- **Inserção Múltipla:** É possível inserir vários registros de uma vez separando os grupos de valores por vírgula:

```sql
INSERT INTO Clientes (ID, Nome, Idade, Cidade)
VALUES
    (2, 'Bruno Costa', 35, 'São Paulo'),
    (3, 'Carla Diaz', 22, 'Rio de Janeiro');
```

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

#### UPDATE (Atualizando Dados)

O comando `UPDATE` é utilizado para modificar registros que já existem em uma tabela. Ele corresponde ao "Update" do acrônimo CRUD.

**Atenção:** É fundamental utilizar a cláusula `WHERE` ao executar um `UPDATE`. Se você esquecer o `WHERE`, o banco de dados atualizará **todas** as linhas da tabela de uma só vez.

**Sintaxe Básica:**

```sql
UPDATE nome_da_tabela
SET coluna1 = novo_valor1, coluna2 = novo_valor2
WHERE condicao;
```

**Exemplo Prático:** Imagine que a cliente Ana Pereira mudou de cidade. Precisamos atualizar o registro dela:

```sql
UPDATE Clientes
SET Cidade = 'Florianópolis'
WHERE ID = 1;
```

**Pontos Importantes:**

- **Múltiplas Colunas:** Você pode alterar vários campos ao mesmo tempo separando-os por vírgula. 
- **Segurança:** Sempre verifique a condição do `WHERE` (geralmente usando a Chave Primária) para garantir que está alterando apenas o registro desejado.

#### DELETE (Removendo Dados)

O comando `DELETE` é utilizado para excluir linhas de uma tabela. Ele corresponde ao "Delete" do acrônimo CRUD.

Assim como no `UPDATE`, o uso do `WHERE` é crítico. Sem ele, você apagará todos os dados da tabela (embora a estrutura da tabela, as colunas e os tipos de dados permaneçam intactos, ao contrário do comando `DROP`).

**Sintaxe Básica:**

```sql
DELETE FROM nome_da_tabela
WHERE condicao;
```

**Exemplo Prático:** Se um cliente solicitar a exclusão de sua conta ou se um registro for inserido por erro:

```sql
DELETE FROM Clientes
WHERE ID = 3;
```

**Diferença entre DELETE e DROP:**

- **DELETE:** Limpa os móveis de dentro do quarto (os dados), mas o quarto continua lá.
- **DROP:** Demole o prédio inteiro (a tabela e os dados somem).
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


**1. Operadores Lógicos (AND, OR, NOT)**

Eles funcionam como a "cola" que une múltiplas condições.

- **AND (E):** Exige que **todas** as condições sejam verdadeiras. É restritivo.
- **OR (OU):** Exige que **pelo menos uma** condição seja verdadeira. É inclusivo.
- **NOT (NÃO):** Inverte o resultado da condição. O que era verdadeiro vira falso e vice-versa.

**Exemplo Prático:** Queremos encontrar clientes que sejam de "São Paulo" **OU** do "Rio de Janeiro", mas que **NÃO** tenham 25 anos.

```sql
SELECT * FROM Clientes
WHERE (Cidade = 'São Paulo' OR Cidade = 'Rio de Janeiro')
AND NOT Idade = 25;
```

**2. O Operador IN (Listas)**

O `OR` é útil, mas imagine filtrar clientes de 10 cidades diferentes. Escrever `Cidade = 'X' OR Cidade = 'Y'...` ficaria enorme. O operador `IN` resolve isso permitindo passar uma lista de valores aceitos.

```sql
-- Seleciona clientes que moram em qualquer uma destas três cidades
SELECT * FROM Clientes
WHERE Cidade IN ('Curitiba', 'Salvador', 'Belo Horizonte');
```

**3. O Operador BETWEEN (Intervalos)**

Usado para filtrar valores dentro de um intervalo específico (incluindo os valores inicial e final). Funciona muito bem para números e datas.

```sql
-- Seleciona clientes com idade entre 20 e 30 anos (inclusive)
SELECT * FROM Clientes
WHERE Idade BETWEEN 20 AND 30;
```

**4. O Operador LIKE (Busca por Padrões)**

Às vezes, não sabemos o texto exato que estamos procurando, ou queremos encontrar partes de um texto. O `LIKE` é usado para buscar padrões dentro de colunas de texto (strings). Ele utiliza dois caracteres "curinga":

- **`%` (Porcentagem):** Representa "qualquer quantidade de caracteres" (zero ou mais).
- **`_` (Underline):** Representa "exatamente um caractere".

**Exemplos:**

- Encontrar nomes que **começam** com a letra 'A':

```sql
SELECT * FROM Clientes WHERE Nome LIKE 'A%';
```
_(Encontra: "Ana", "André", "Amanda Pereira")_

- Encontrar nomes que **terminam** com 'Silva':

```sql
SELECT * FROM Clientes WHERE Nome LIKE '%Silva';
```

- Encontrar nomes que tenham 'rla' em **qualquer parte** do texto:

```sql
SELECT * FROM Clientes WHERE Nome LIKE '%rla%';
```
_(Encontra: "Carla", "Orlando")_

#### ORDER BY (Ordenando Resultados)

Ao fazer um `SELECT`, o banco de dados não garante que os registros retornem em uma ordem específica. Para organizar a apresentação dos dados — seja alfabeticamente, por data ou por valores numéricos — utilizamos a cláusula `ORDER BY`.

Por padrão, a ordenação é **Ascendente** (do menor para o maior, ou de A a Z).

**Sintaxe Básica:**

```sql
SELECT colunas FROM tabela
WHERE condicao
ORDER BY coluna_para_ordenar;
```

**1. Ordenação Crescente (ASC) e Decrescente (DESC)**

Embora o padrão seja crescente, podemos forçar a ordem inversa usando a palavra-chave `DESC`. O `ASC` é opcional, mas pode ser usado para clareza.

- **ASC:** Ascendente (1, 2, 3... ou A, B, C...).

- **DESC:** Descendente (3, 2, 1... ou Z, Y, X...).


**Exemplo Prático:**

Vamos listar os clientes ordenados do mais velho para o mais novo.

```sql
SELECT Nome, Idade FROM Clientes
ORDER BY Idade DESC;
```

**2. Ordenando por Múltiplas Colunas**

É muito comum precisarmos ordenar por mais de um critério. Por exemplo: "Quero ver a lista de clientes organizada por Cidade e, dentro de cada cidade, quero os nomes em ordem alfabética".

Para isso, basta separar as colunas por vírgula no `ORDER BY`. O banco seguirá a ordem da esquerda para a direita.

```sql
SELECT * FROM Clientes
ORDER BY Cidade ASC, Nome ASC;
```

_Neste caso, o banco agrupa todos os clientes de "Belo Horizonte" primeiro (ordenando esses nomes entre si), depois passa para "Curitiba", e assim por diante._

#### ALIAS (Renomeando Colunas)

Muitas vezes, os nomes das colunas no banco de dados são técnicos, abreviados ou em inglês, o que dificulta a leitura em um relatório final. O SQL permite usar **Aliases** (apelidos) para dar nomes temporários e mais amigáveis a essas colunas ou tabelas nos resultados da sua consulta.

Para isso, utilizamos a palavra-chave `AS`.

**Sintaxe Básica:**

```sql
SELECT coluna_original AS novo_nome
FROM tabela;
```

**Exemplo Prático:**

Imagine que queremos gerar uma lista de preços da tabela `Pedidos`. No banco, a coluna chama-se `ValorTotal`, mas no relatório queremos que apareça escrito "Preço Final".

```sql
SELECT ID, ValorTotal AS 'Preço Final'
FROM Pedidos;
```

_Nota: Se o apelido contiver espaços (como "Preço Final"), é obrigatório o uso de aspas simples ou duplas._

**Aliases em Operações Matemáticas**

O Alias é extremamente útil quando criamos colunas calculadas que não existem fisicamente na tabela. Sem um alias, o banco daria um nome estranho para essa coluna (algo como `col_2`).

Suponha que queremos simular um desconto de 10% no valor dos pedidos:

```sql
SELECT
    ID,
    ValorTotal,
    (ValorTotal * 0.90) AS ValorComDesconto
FROM Pedidos;
```

**Combinando com ORDER BY**

Uma vantagem prática é que você pode reutilizar o apelido que acabou de criar para ordenar os resultados, deixando o código mais limpo.

```sql
SELECT Nome AS Cliente, Idade
FROM Clientes
ORDER BY Cliente ASC;
```

#### INSERT INTO com SELECT (Cópia de Dados)

Até agora, vimos como inserir dados manualmente, linha por linha. Porém, em cenários reais, frequentemente precisamos copiar dados de uma tabela para outra massivamente.

O comando `INSERT INTO ... SELECT` permite inserir dados em uma tabela de destino baseando-se diretamente nos resultados de uma consulta (`SELECT`) feita em uma tabela de origem. É ideal para criar backups, arquivar dados antigos ou popular tabelas de relatórios.

**Sintaxe Básica:**

```sql
INSERT INTO tabela_destino (coluna1, coluna2)
SELECT coluna1, coluna2
FROM tabela_origem
WHERE condicao;
```

**Regra de Ouro:** O número de colunas e os tipos de dados selecionados no `SELECT` devem corresponder exatamente às colunas listadas no `INSERT`.

**Exemplo Prático:**

Imagine que queremos criar uma tabela exclusiva apenas para clientes que moram no Rio de Janeiro, chamada `Clientes_Rio`. Supondo que a tabela já foi criada com o comando `CREATE`, podemos copiar os dados assim:

```sql
INSERT INTO Clientes_Rio (Nome, Idade)
SELECT Nome, Idade
FROM Clientes
WHERE Cidade = 'Rio de Janeiro';
```

_Neste exemplo, o banco de dados busca todos os clientes do Rio de Janeiro na tabela original e, instantaneamente, insere seus nomes e idades na nova tabela `Clientes_Rio`._

### Modificando e Excluindo Estruturas

Nem sempre a estrutura que definimos inicialmente (o esquema) permanece a mesma para sempre. Requisitos de projetos mudam, e o banco de dados precisa acompanhar essas evoluções. Para isso, utilizamos comandos que alteram o "esqueleto" das tabelas ou as removem por completo.

#### ALTER TABLE (Alterando a Estrutura)

O comando `ALTER TABLE` é utilizado quando precisamos modificar uma tabela já existente sem perder os dados que já foram inseridos nela. O uso mais comum é a adição de novas colunas para acomodar novas informações.

**Sintaxe Básica:**

```sql
ALTER TABLE nome_da_tabela ADD nome_da_coluna tipo_de_dado;
```

**Exemplo Prático:**

Imagine que, após criar a tabela `Clientes`, percebemos que esquecemos de incluir um campo para o e-mail. Podemos adicionar essa coluna agora:

```sql
ALTER TABLE Clientes ADD Email TEXT;
```

_Agora, a tabela Clientes possui uma nova coluna "Email". Os registros que já existiam ficarão com este campo vazio (NULL) até que sejam atualizados._

Para excluir uma coluna de uma tabela, usamos a sintaxe:

```sql
ALTER TABLE nome_da_tabela
DROP COLUMN nome_da_coluna;
```

Por exemplo:

```sql
ALTER TABLE Estudantes
DROP COLUMN Idade;
```

#### DROP (Excluindo Objetos)

O comando `DROP` é drástico e deve ser usado com extrema cautela. É fundamental não confundi-lo com o `DELETE`:

- **DELETE:** Remove os dados (linhas) de dentro da tabela, mas a tabela continua existindo.
- **DROP:** Remove a **tabela inteira** (o contêiner, a estrutura e todos os dados) do banco de dados. É como demolir a casa em vez de apenas tirar os móveis.

**Sintaxe Básica:**

```sql
DROP TABLE nome_da_tabela;
```

**Exemplo:**

```sql
-- Remove completamente a tabela Clientes e todos os seus registros
DROP TABLE Clientes;
```

_Uma vez executado, a tabela deixa de existir no esquema. Em muitos SGBDs, não há como desfazer (undo) essa operação facilmente._

### Tipos de Dados

Os bancos de dados armazenam uma variedade de tipos de dados. A escolha dos tipos de dados depende da natureza dos dados.

#### Texto (String)

- **CHAR:** Armazena strings de tamanho fixo. Usado quando os valores têm um comprimento constante.
- **VARCHAR:** Armazena strings de tamanho variável. Apropriado para valores com comprimentos variáveis.
- **TEXTO (TEXT):** Armazena strings muito longas, como documentos ou descrições.

#### Numérico

- **INTEGER (INT):** Armazena números inteiros.
- **FLOAT:** Armazena números de ponto flutuante, geralmente usados para valores com casas decimais.
- **NUMERIC (DECIMAL):** Armazena números com uma precisão específica, geralmente usados em aplicações financeiras.

#### Data e Hora

- **DATE:** Armazena datas sem informações de horário.
- **TIME:** Armazena informações de horário.
- **TIMESTAMP:** Combina data e horário em um único tipo.

#### Booleano

- **BOOLEAN (BOOL):** Armazena valores verdadeiros ou falsos.

#### Binário

- **BLOB (Binary Large Object):** Armazena dados binários, como imagens, vídeos ou arquivos.
- **BIT:** Armazena valores binários, como 0 ou 1.

Vale ressaltar que a escolha dos tipos de dados pode variar dependendo do sistema de gerenciamento de banco de dados (SGBD) e das necessidades específicas de um aplicativo. Além disso, alguns SGBDs também oferecem tipos de dados personalizados que podem ser adaptados para requisitos de negócios.

