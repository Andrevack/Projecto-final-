# Projecto-final-
Dados MVP empresa

O objetivo do meu trabalho é fazer um estudo com base nos dados de uma determinada loja de vendas ABC de produtos diversos e perceber alguns aspectos importantes para traçar melhor estratégias, estes dados estavam disponíveis em planilhas Excel guardados no meu computador pessoal. Para traçar melhores estratégias de marketing e não só foi necessário responder a algumas perguntas como : 

Qual é o cliente que mais compra ?
Vania Maria
Qual é a categoria que mais vende ?
A categoria que mais vende é a categoria acessórios
Qual é o género que mais compra ?
F
Qual é a cidade que mais compra ?
O maior número de vendas é realizado para clientes que vivem em Benguela
Qual é o produto mais vendido ?
Tapete com 4 produtos 
Qual é a faixa etária que mais compra ?
A faixa etária que mais compra é entre 20-29 anos
Qual é o produto com valor mais elevado ?
Tapete – tem o valor mais elevado  130


1) Os dados foram extraídos a partir de três arquivos no formato Excel (.xlsx), carregados para o ambiente Databricks:

- cliente.xlsx: Contém informações dos clientes.
- vendas.xlsx: Contém o registro de vendas.
- Dim_Produto.xlsx: Contém a descrição dos produtos (tabela dimensão).

Esses arquivos foram carregados usando o conector com.crealytics.spark.excel.


2)	  Etapa de transformação 

Durante a transformação, foram realizadas as seguintes ações:

- Padronização de nomes de colunas, removendo espaços e facilitando o uso no código.
- Remoção de duplicatas da tabela vendas com base nas colunas principais.
- Renomeação de colunas, como:
  - "Valor da Compra" → valor_da_compra etc.
 
- 3)	Etapa de carga 

As tabelas finais foram registradas como views temporárias no ambiente Spark/Databricks:

- cliente
- vendas
- dim_produto
- fato_vendas_estrela

Essas tabelas foram usadas para análise e construção do modelo estrela.



Catalogo de dados (Tabela Vendas )

Nome da Coluna   | Tipo de Dado  | Descrição |Domínio de Valores |
|----------------|---------------|-----------|-------------------|
ID_Cliente       |  String       | Identificador único do cliente| Ex: HL001, HL002, HL003
Produto          |  String       | Nome do produto comprado.     |Ex: "Tshirt", "Cueca", "Sapato", etc.
Valor            |  Double (€)   | Preço unitário do produto.    |NA
Quantidade       | Integer       | Quantidade comprada do produto|NA
Valor da Compra  | Double (€)    |  Valor total da compra (Valor * Quantidade)|NA
ID_Produto       | String        | Identificador único do produto |NA





 
- 

