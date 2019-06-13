# Olá Locawebers!

Nesta pasta existem dois datasets com dados de e-commerce. O primeiro contêm dados de uma loja de e-commerce do segmento de moda que vende em todo o Brasil. O segundo contêm dados de um e-commerce do ramo de construção.
Ambos os datasets tem a mesma estrutura e são compostos dos seguintes arquivos:

## pedidos.csv  
Contêm os dados históricos dos pedidos realizados na loja, ordenados por data. As colunas estão descritas abaixo.
Exemplo: `264879;2019-06-10 21:18:10.0000000;Pago;51,14;13,71;312529;Mercado Pago;1`
- PedidoId (int64): Identificador único do pedido.
- Data (datetime): Data que o pedido foi realizado.
- Situação (string): Situação atual do pedido (Pago, Cancelado, Enviado, etc)
- Valor Total do Pedido (decimal): Valor total do pedido em R$.
- Valor Frete (decimal): Soma dos custos de frete de todos os itens do pedido em R$.
- UsuarioId (int64): Identificador único do cliente que realizou a compra.
- Forma de Pagamento (string): Forma de Pagamento que o cliente optou no momento de realizar a compra.
- Número de Parcelas (int16): Número de parcelas que o cliente optou no momento de realizar a compra.

## pedidos_produtos.csv
Contêm a relação entre pedidos e produtos. Cada item do pedido possui uma linha no dataset. O campo "quantidade" representa o número de unidades que o cliente comprou.
Exemplo: `264879;256061;1`
- PedidoId (int64): Identificador único do pedido
- ProdutoVarianteId (int64): Identificador único do produto.
- Quantidade (int16): Número de unidades compradas do produto.

## produtos.csv
Contêm a lista de produtos disponíveis e indisponíveis na loja. O campo bit "valido" representa se este produto ainda é fabricado ou já saiu de linha.
Exemplo: `257431;Detergente Limpeza Piso Laminado Dr Schutz Limpeza Diária 1L;27,49;25,99;0;1;Dr Schutz;2019-06-10 16:10:38.000`

- ProdutoVarianteId (int64): Identificador único do produto.
- Nome (string): Nome do produto.
- PrecoDe (decimal): "Preço De" do produto. Normalmente utilizado para demonstrar descontos. Em R$.
- PrecoPor (decimal): Preço de venda do produto em R$.
- Disponivel (bit): Indica se o produto está disponível (tem estoque) neste momento.
- Valido (bit): Indica se o produto ainda é fabricado ou vendido pela loja.
- Fabricante (string): Marca ou Fabricante do produto.
- DataCriacao (datetime): Data em que o produto foi inserido na loja.

## produtos_atributos.csv
Contêm os atributos de cada produto. Cada produto pode conter atributos diferentes. Por exemplo: Um tênis normalmente tem ao menos dois atributos: cor e tamanho. Já um aparelho de construção pode ter atributos como Potência e Tensão Elétrica.
Exemplos: 
`254636;Potência (W);600`
`254636;Tensão Elétrica;127V`

- ProdutoVarianteId (int64): Identificador único do produto.
- Atributo (string): Nome do atributo do produto.
- Valor (string): Valor do atributo do produto.

## produtos_categorias.csv
Contêm a relação entre produtos e a árvore de categorias. Cada produto pode estar ao mesmo tempo em mais de uma árvore de categorias. O caracter `>` identifica a relação de hierarquia: `pai > filho > neto`.
Exemplo: `254650;Pisos > Pisos Laminados > Pisos Laminados Eucafloor`

- ProdutoVarianteId (int64): Identificador único do produto
- Arvore (string): Árvore de categorias.

## clientes.csv
Contêm a lista de clientes da loja e seu endereço principal.
Exemplo: `312529;Karina;M;1900-01-01 00:00:00.000;Física;12525000;Potim;SP;Brasil;2019-06-10 22:58:14.140`

- UsuarioId (int64): Identificador único do cliente.
- Nome (string): Nome do cliente.
- Sexo (char): Sexo do cliente (M/F).
- DataNascimento (datetime): Data de Nascimento informada pelo cliente.
- Tipo (string): Tipo de pessoa (Física/Jurídica).
- CEP (string): CEP do endereço principal do cliente.
- Cidade (string): Cidade do endereço principal do cliente.
- Estado (string): Estado do endereço principal do cliente.
- Pais (string): País do endereço principal do cliente.

# APIs de Integração

O conjunto de APIs REST estão nesta documentação online: https://api.fbits.net/
Para utilizar as APIs, será necessário informar um token de autentição e autorização.

Token loja moda: `hacka-e312b2bf-c7ca-420b-9e02-cce40374deb9`
Token loja construção: `hacka-8ccc5a2c-75cf-4b42-819b-220dabd87742`

Header de Autenticação: `Authorization: BASIC hacka-e312b2bf-c7ca-420b-9e02-cce40374deb9`

# Boa sorte!
