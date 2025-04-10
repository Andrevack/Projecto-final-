# Projecto-final-
Dados MVP empresa

O objetivo deste trabalho é realizar uma análise exploratória com base nos dados da loja ABC, especializada na venda de produtos diversos. Os dados utilizados estavam armazenados em planilhas do Excel e foram carregados para o ambiente de análise na nuvem (Databricks).

O propósito principal da análise é extrair informações relevantes para auxiliar na definição de melhores estratégias de marketing e decisões comerciais. Para isso, foram elaboradas e respondidas algumas perguntas-chave, cujas respostas podem orientar ações estratégicas da empresa.

Qual é o cliente que mais compra ?
O cliente que mais compra tem o nome de Vania Maria
Qual é a categoria que mais vende ?
A categoria que mais vende é a categoria acessórios
Qual é o género que mais compra ?
O género que mais compra é Femenino
Qual é a cidade que mais compra ?
O maior número de vendas é realizado para clientes que vivem em Benguela
Qual é o produto mais vendido ?
O produto mais vendido é o Tapete com 4 produtos 
Qual é a faixa etária que mais compra ?
A faixa etária que mais compra é entre 20-29 anos
Qual é o produto com valor mais elevado ?
O Tapete – tem o valor mais elevado  130


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
Valor            |  Double (€)   | Preço unitário do produto.    |Mínimo: 20,00
Quantidade       | Integer       | Quantidade comprada do produto|Mínimo: 1
Valor da Compra  | Double (€)    |  Valor total da compra (Valor * Quantidade)|NA
ID_Produto       | String        | Identificador único do produto |Mínimo: 40,00

 Catálogo de Dados – ( Tabela Dim- produto)

Nome da coluna  | Tipo de Dado  | Descrição| Domínio de Valores |
|-------------- |---------------|----------|--------------------|
ID Produto      | String        |Identificador único do produto.| Ex: P001, P002, P003...
Nome do Produto | String        |Nome do produto conforme cadastro| Ex: "Tshirt", "Cueca", "Sapato", "Meia", "Cinto"
Categora        | String        | Categoria à qual o produto pertence.|Ex: "Roupas", "Calçados", "Acessórios", etc.
Valor           | Double (€)    |Preço unitário do produto.| Mínimo: 20.00 €, Máximo: 60.00 €


Catálogo de Dados – (Tabela Clientes )

Nome da Coluna | Tipo de dado   | Descrição | Domínio de Valores|
|--------------|----------------|-----------|-------------------|
ID Cliente     | String         |Identificador único do cliente.| Ex: HL001, HL002, HL003...
Nome Cliente   | String         | Nome do cliente completo      | Ex: "Ana Silva", "Carlos Mendes", etc.
Idade          | Integer        |Idade do cliente               | Mínimo: (exemplo: 18), Máximo: (exemplo: 65)
Genero         | String         |Identificação de gênero do cliente.| Ex: "Masculino", "Feminino", "Outro"
Cidade         | String         |Cidade de residência do cliente.|Ex: "Lisboa", "Porto", "Luanda", "Maputo"


 Análise

 A análise realizada evidencia que a empresa possui um público diversificado, com destaque para a faixa etária entre 20 e 29 anos, que concentra o maior volume de compras. Isso indica que as estratégias de marketing atuais têm sido eficazes para atrair esse público. No entanto, há uma oportunidade importante: expandir o alcance para outras faixas etárias, sem negligenciar o bom trabalho já feito. Campanhas direcionadas, ofertas personalizadas ou parcerias estratégicas podem ajudar a envolver outros grupos etários.

No que diz respeito ao gênero, observou-se que o público feminino realiza a maior parte das compras. Apesar disso, a empresa pode explorar ações específicas para atrair mais consumidores do sexo masculino. Uma das estratégias pode envolver o equilíbrio de gênero na equipe de atendimento, criando um ambiente mais acolhedor para todos os clientes. Além disso, a comunicação visual e as campanhas promocionais podem ser pensadas de forma mais inclusiva, abordando também os interesses do público masculino.

A cidade de Benguela é responsável pela maior parte das vendas, o que demonstra uma forte presença da marca nessa localidade. No entanto, é importante fortalecer a atuação em outras cidades para evitar dependência excessiva de um único mercado. Investimentos em publicidade local, promoções regionais ou ampliação dos canais de venda podem ajudar a equilibrar os resultados entre as regiões e aumentar o alcance da empresa.


- 

