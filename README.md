Projeto Conceitual de Gestão de Pedidos e Estoques

Descrição do Projeto

Este projeto tem como objetivo modelar e gerenciar um sistema de controle de pedidos, estoque e fornecedores. A estrutura foi desenvolvida para abranger desde o cadastro de clientes e fornecedores até a organização de pedidos, produtos e entregas. O modelo permite uma visão abrangente do fluxo de operações relacionadas à comercialização e distribuição de produtos.

Estrutura do Banco de Dados

O banco de dados é estruturado para atender às necessidades de um sistema de gestão de pedidos e estoques, garantindo rastreabilidade e organização. A seguir, os principais componentes do esquema:

Tabelas Principais

Fornecedor: Contém informações sobre os fornecedores de produtos.

idfornecedor (INT) - Identificador único do fornecedor.

razão social (VARCHAR) - Nome registrado do fornecedor.

CNPJ (VARCHAR) - Cadastro Nacional de Pessoa Jurídica do fornecedor.

Produto: Armazena os produtos disponíveis.

idproduto (INT) - Identificador único do produto.

categoria (VARCHAR) - Categoria do produto.

descrição (VARCHAR) - Detalhes sobre o produto.

valor (VARCHAR) - Preço do produto.

Estoque: Controla a localização e disponibilidade dos produtos.

idestoque (INT) - Identificador único do estoque.

local (VARCHAR) - Localização do estoque.

Pedido: Representa as transações realizadas.

idpedido (INT) - Identificador único do pedido.

status do pedido (VARCHAR) - Estado atual do pedido.

descrição (VARCHAR) - Informações adicionais sobre o pedido.

frete (FLOAT) - Valor do frete.

cadastro clientes_idcadastro clientes (INT) - Referência ao cliente que realizou o pedido.

pagamento_idpagamento (INT) - Forma de pagamento utilizada.

entrega_identrega (INT) - Identificação da entrega associada.

Pagamento: Gerencia os métodos de pagamento.

idpagamento (INT) - Identificador único do pagamento.

forma de pagamento (VARCHAR) - Tipo de pagamento utilizado.

Entrega: Acompanha a distribuição dos pedidos.

identrega (INT) - Identificador único da entrega.

status (VARCHAR) - Estado da entrega.

codigo de entrega (VARCHAR) - Código de rastreamento da entrega.

Clientes (Pessoa Física e Jurídica): Registra informações sobre os clientes.

Cliente PF (Pessoa Física): idcliente_pf (INT), nome (VARCHAR), CPF (INT), endereço (VARCHAR).

Cliente PJ (Pessoa Jurídica): idcliente_pj (INT), nome (VARCHAR), CNPJ (INT), endereço (VARCHAR).

Cadastro de Clientes: Relaciona clientes ao sistema.

idcadastro_clientes (INT) - Identificador do cadastro.

cliente_pf_idcliente_pf (INT) - Referência ao cliente pessoa física.

cliente_pj_idcliente_pj (INT) - Referência ao cliente pessoa jurídica.

Relacionamentos

Produto por Fornecedor: Relaciona fornecedores aos produtos fornecidos.

fornecedor_idfornecedor (INT) → produto_idproduto (INT).

Produto por Estoque: Relaciona produtos ao estoque onde estão armazenados.

produto_idproduto (INT) → estoque_idestoque (INT).

quantidade (INT) - Número de unidades disponíveis.

Produto por Pedido: Representa os produtos contidos em um pedido.

produto_idproduto (INT) → pedido_idpedido (INT).

quantidade (INT) - Quantidade do produto no pedido.

Produto por Vendedor Terceiro: Relaciona produtos vendidos por terceiros.

terceiro_vendedor_idterceiro_vendedor (INT) → produto_idproduto (INT).

quantidade (INT) - Número de unidades vendidas pelo terceiro.

Conclusão

Este projeto conceitual fornece um modelo robusto para gerenciamento de pedidos e estoques, cobrindo desde o cadastro de clientes e fornecedores até a distribuição dos produtos. O esquema apresentado possibilita a organização eficiente dos processos comerciais e logísticos, garantindo controle sobre cada etapa do fluxo de vendas.


