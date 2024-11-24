"# Projeto_oficina_Dio_Suzano" 
 
# 🚗 Sistema de Ordem de Serviço - Modelagem de Banco de Dados

Este repositório contém a modelagem de um banco de dados relacional para um sistema de gerenciamento de ordens de serviço (OS), desenvolvido para oficinas ou empresas que trabalham com manutenção e serviços técnicos.

## 📖 Descrição do Projeto

A modelagem foi projetada para registrar clientes, veículos, funcionários, serviços prestados, produtos utilizados e os detalhes de cada ordem de serviço. Este sistema é ideal para auxiliar no gerenciamento de processos e monitoramento de informações relacionadas às ordens de serviço de forma estruturada e eficiente.

## 🗃️ Estrutura do Banco de Dados

### 🔹 Tabelas e Relacionamentos

1. **clientes**
   - **idcliente:** Identificador único do cliente.
   - **nome:** Nome completo do cliente.
   - **Tipo_doc:** Tipo de documento (CPF ou CNPJ).
   - **n_documento:** Número do documento.
   - **contato:** Informações de contato do cliente (telefone ou e-mail).
   - **cidade:** Cidade onde o cliente reside.
   - **endereco:** Endereço completo do cliente.

2. **veiculos**
   - **id:** Identificador único do veículo.
   - **marca:** Marca do veículo.
   - **modelo:** Modelo do veículo.
   - **ano:** Ano de fabricação do veículo.
   - **cor:** Cor do veículo.
   - **idcliente:** Chave estrangeira que relaciona o veículo a um cliente.

3. **ordem_de_servico**
   - **idordem:** Identificador único da ordem de serviço.
   - **descricao_os:** Descrição do serviço solicitado.
   - **numero_os:** Número da OS para controle.
   - **data_emissao:** Data de emissão da ordem de serviço.
   - **valor:** Valor total da ordem de serviço.
   - **status:** Status atual da OS (em andamento, concluída, etc.).
   - **data_conclusao:** Data de conclusão do serviço.
   - **idcliente:** Chave estrangeira que relaciona a OS ao cliente.

4. **funcionarios**
   - **idfuncionario:** Identificador único do funcionário.
   - **nome:** Nome do funcionário.
   - **especialidade:** Área de especialização do funcionário.
   - **endereco:** Endereço do funcionário.
   - **idordem:** Chave estrangeira para associar o funcionário à ordem de serviço.

5. **funcionario_e_os** (TABELA DE RELAÇÃO)
   - **idfuncionario_os:** Identificador único do vínculo.
   - **idfuncionario:** Chave estrangeira que referencia a tabela `funcionarios`.
   - **idordem:** Chave estrangeira que referencia a tabela `ordem_de_servico`.

6. **mao_de_obra**
   - **idmao_de_obra:** Identificador único da mão de obra.
   - **descricao:** Descrição detalhada da atividade realizada.
   - **valor:** Valor da mão de obra.
   - **status_aprovacao:** Status de aprovação do serviço (pendente, aprovado, rejeitado).
   - **idordem:** Chave estrangeira que referencia a tabela `ordem_de_servico`.

7. **produto**
   - **id:** Identificador único do produto.
   - **categoria:** Categoria do produto (peça, material, etc.).
   - **descricao:** Descrição do produto.
   - **marca:** Marca do produto.
   - **modelo:** Modelo do produto.
   - **idordem:** Chave estrangeira que relaciona o produto à ordem de serviço.

## 🔗 Relacionamentos

- **Cliente e Veículo:** Cada cliente pode ter vários veículos cadastrados.
- **Ordem de Serviço e Cliente:** Uma OS está associada a um único cliente.
- **Funcionário e OS:** Cada funcionário pode estar vinculado a várias ordens de serviço.
- **Mão de Obra e OS:** Uma ordem de serviço pode conter diferentes tipos de mão de obra.
- **Produtos e OS:** Produtos utilizados são associados diretamente a uma ordem de serviço.

## 🛠️ Ferramentas Utilizadas

- **Ferramenta de Modelagem:** [DBeaver](https://dbeaver.io/)
- **Banco de Dados:** MySQL

## 📌 Objetivo do Projeto

O objetivo principal é desenvolver um modelo que facilite:
- O gerenciamento de clientes e veículos.
- A rastreabilidade de produtos e serviços prestados.
- A organização de dados relacionados aos funcionários e suas especializações.


