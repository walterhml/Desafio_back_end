# Desafio_back_end
Solução do Desafio de Desenvolvedor Back-End! 

# Documentação do Banco de Dados do Hotel

---

## Introdução

Este documento apresenta a documentação detalhada do banco de dados do sistema de gerenciamento de um hotel. O banco de dados foi desenvolvido para atender às necessidades de registro e gestão de clientes, chalés, hospedagens, serviços e itens.

## Objetivo

O objetivo deste banco de dados é fornecer uma estrutura robusta para o gerenciamento eficiente das operações do hotel, incluindo o registro de clientes, reserva de chalés, acompanhamento de hospedagens, serviços adicionais e itens disponíveis.

## Entidades

1. **Cliente**: Representa os clientes que fazem reservas no hotel.
2. **Telefone**: Armazena os números de telefone dos clientes.
3. **Chalé**: Descreve os chalés disponíveis para hospedagem.
4. **Hospedagem**: Registra as hospedagens dos clientes nos chalés.
5. **Item**: Lista os itens disponíveis para uso durante a hospedagem.
6. **Serviço**: Lista os serviços adicionais oferecidos pelo hotel.
7. **Hospedagem_Servico**: Relaciona os serviços utilizados durante as hospedagens.
8. **Chale_Item**: Relaciona os itens disponíveis em cada chalé.

## Descrição das Tabelas

1. **Cliente**:
   - `codCliente`: Identificador único do cliente.
   - `nomeCliente`: Nome do cliente.
   - `rgCliente`: Número de identidade do cliente.
   - `enderecoCliente`: Endereço do cliente.
   - `bairroCliente`: Bairro do cliente.
   - `cidadeCliente`: Cidade do cliente.
   - `estadoCliente`: Estado do cliente.
   - `CEPCliente`: CEP do cliente.
   - `nascimentoCliente`: Data de nascimento do cliente.

2. **Telefone**:
   - `telefone`: Número de telefone.
   - `codCliente`: Chave estrangeira referenciando o cliente.
   - `tipoTelefone`: Tipo de telefone (residencial, celular, etc.).

3. **Chalé**:
   - `codChale`: Identificador único do chalé.
   - `localizacao`: Localização do chalé.
   - `capacidade`: Capacidade máxima de pessoas no chalé.
   - `valorAltaEstacao`: Valor do chalé na alta estação.
   - `valorBaixaEstacao`: Valor do chalé na baixa estação.

4. **Hospedagem**:
   - `codHospedagem`: Identificador único da hospedagem.
   - `codChale`: Chave estrangeira referenciando o chalé.
   - `codCliente`: Chave estrangeira referenciando o cliente.
   - `dataInicio`: Data de início da hospedagem.
   - `dataFim`: Data de término da hospedagem.
   - `qtdPessoas`: Quantidade de pessoas na hospedagem.
   - `desconto`: Valor do desconto aplicado.
   - `valorFinal`: Valor final da hospedagem.

5. **Item**:
   - `nomeItem`: Nome do item.
   - `descricaoItem`: Descrição do item.

6. **Serviço**:
   - `codServico`: Identificador único do serviço.
   - `nomeServico`: Nome do serviço.
   - `valorServico`: Valor do serviço.

7. **Hospedagem_Servico**:
   - `codHospedagem`: Chave estrangeira referenciando a hospedagem.
   - `codServico`: Chave estrangeira referenciando o serviço.
   - `dataServico`: Data em que o serviço foi utilizado.

8. **Chale_Item**:
   - `codChale`: Chave estrangeira referenciando o chalé.
   - `nomeItem`: Chave estrangeira referenciando o item.

## Relacionamentos

- A tabela `Telefone` possui uma relação de um para muitos com a tabela `Cliente`.
- A tabela `Hospedagem` possui relações de muitos para um com as tabelas `Chalé` e `Cliente`.
- A tabela `Hospedagem_Servico` relaciona muitos para muitos entre `Hospedagem` e `Serviço`.
- A tabela `Chale_Item` relaciona muitos para muitos entre `Chalé` e `Item`.

## Conclusão

O banco de dados do hotel oferece uma estrutura completa para o gerenciamento de clientes, hospedagens, chalés, itens e serviços. Com esta documentação, os desenvolvedores podem entender a estrutura do banco de dados e utilizá-lo efetivamente para desenvolver sistemas de gestão hoteleira robustos e eficientes.
