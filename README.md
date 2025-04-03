*ENTREGA PROJETO 1: E-COMMERCE*
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



*ENTREGA PROJETO OFICINA*

Projeto Conceitual de Gestão de Oficinas Mecânicas

Descrição do Projeto

Este projeto visa modelar e gerenciar um sistema de controle de ordens de serviço (OS), clientes, mecânicos e execução de serviços em uma oficina mecânica. A estrutura do banco de dados permite a organização eficiente dos processos de manutenção de veículos, garantindo um fluxo de trabalho claro e estruturado para os serviços prestados.

Estrutura do Banco de Dados

O banco de dados é organizado para otimizar a gestão das atividades de uma oficina mecânica, desde o cadastro de clientes e mecânicos até a emissão de ordens de serviço e controle da execução de serviços.

Tabelas Principais

Serviço: Registra informações sobre os serviços prestados.

idserviço (INT) - Identificador único do serviço.

mecanico_idmecanico (INT) - Referência ao mecânico responsável pelo serviço.

valor (VARCHAR) - Custo do serviço.

Ordem de Serviço (OS): Controla as ordens de serviço emitidas.

idOS (INT) - Identificador único da OS.

numero (VARCHAR) - Número da OS.

data de emissão (VARCHAR) - Data em que a OS foi emitida.

valor (VARCHAR) - Valor total da OS.

OScol (VARCHAR) - Informações complementares sobre a OS.

clientes_idclientes (INT) - Cliente relacionado à OS.

mecanico_idmecanico (INT) - Mecânico responsável.

mão de obra_idmão de obra (INT) - Custo da mão de obra.

Mecânico: Cadastro de mecânicos da oficina.

idmecanico (INT) - Identificador único do mecânico.

nome (VARCHAR) - Nome do mecânico.

endereço (VARCHAR) - Endereço do mecânico.

especialidade (VARCHAR) - Área de especialização do mecânico.

Cliente: Registra os clientes da oficina.

idclientes (INT) - Identificador único do cliente.

Peça: Gerencia peças utilizadas nos serviços.

idpeça (INT) - Identificador único da peça.

valor (VARCHAR) - Custo da peça.

Veículos: Cadastro de veículos atendidos pela oficina.

idveiculos (INT) - Identificador único do veículo.

cliente_idclientes (INT) - Referência ao cliente proprietário do veículo.

Execução: Registra os serviços executados em veículos.

veiculos_idveiculos (INT) - Veículo no qual o serviço foi realizado.

serviço_idserviço (INT) - Serviço executado.

mecanico_idmecanico (INT) - Mecânico responsável pela execução.

Mão de Obra: Relaciona peças e serviços à mão de obra utilizada.

peça_idpeça (INT) - Peça utilizada no serviço.

serviço_idserviço (INT) - Serviço onde a peça foi aplicada.

mão de obra_idmão de obra (INT) - Custo da mão de obra associada ao serviço.

Relacionamentos

Execução de Serviço: Relaciona mecânicos, veículos e serviços prestados.

veiculos_idveiculos → serviço_idserviço → mecanico_idmecanico

Ordem de Serviço: Conecta clientes aos serviços realizados em seus veículos.

clientes_idclientes → idOS

mecanico_idmecanico → idOS

Mão de Obra e Peças: Registra a relação entre os serviços realizados e as peças utilizadas.

peça_idpeça → serviço_idserviço

mão de obra_idmão de obra → serviço_idserviço

Conclusão

O modelo conceitual apresentado fornece uma estrutura eficiente para a gestão de oficinas mecânicas, permitindo um controle detalhado das ordens de serviço, mecânicos, peças e execuções de serviços. Esse sistema melhora a organização interna da oficina e facilita a administração das atividades operacionais.
