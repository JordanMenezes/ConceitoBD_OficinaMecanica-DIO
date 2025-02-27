# Esquema Conceitual para Sistema de Controle de Ordens de Serviço em Oficina Mecânica

## Descrição do Projeto

O presente esquema conceitual foi desenvolvido para um sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica. O objetivo principal do sistema é organizar e gerenciar as informações relacionadas aos serviços realizados em veículos, desde a entrada do cliente até a conclusão dos serviços, garantindo um melhor atendimento e eficiência nas operações da oficina.

## Entidades e Atributos

### 1. Cliente
- **cliente_id** (PK): Identificador único do cliente.
- **nome**: Nome do cliente.
- **endereco**: Endereço do cliente.
- **telefone**: Número de telefone para contato.

### 2. Veículo
- **veiculo_id** (PK): Identificador único do veículo.
- **modelo**: Modelo do veículo.
- **marca**: Marca do veículo.
- **ano**: Ano de fabricação do veículo.
- **cliente_id** (FK): Referência ao cliente proprietário do veículo.

### 3. Mecânico
- **mecanico_id** (PK): Identificador único do mecânico.
- **nome**: Nome do mecânico.
- **endereco**: Endereço do mecânico.
- **especialidade**: Especialidade do mecânico (ex: eletricista, funileiro, etc.).

### 4. Ordem de Serviço (OS)
- **os_id** (PK): Identificador único da ordem de serviço.
- **data_emissao**: Data em que a OS foi emitida.
- **data_entrega**: Data prevista para a conclusão dos serviços.
- **valor_total**: Valor total estimado para os serviços prestados.
- **status**: Status da OS (ex: pendente, em andamento, finalizada).
- **veiculo_id** (FK): Referência ao veículo associado a essa OS.
- **mecanico_id** (FK): Referência ao mecânico responsável pela execução da OS.

### 5. Serviço
- **servico_id** (PK): Identificador único do serviço.
- **descricao**: Descrição do serviço a ser realizado.
- **custo_mao_obra**: Custo associado à mão de obra do serviço.
- **custo_peca**: Custo das peças utilizadas no serviço.
- **os_id** (FK): Referência à OS em que o serviço será executado.

## Relacionamentos
- Um **Cliente** pode ter vários **Veículos** (1:N).
- Um **Veículo** está associado a uma única **Ordem de Serviço** (1:1).
- Uma **Ordem de Serviço** é concluída por um **Mecânico** (N:1).
- Uma **Ordem de Serviço** pode incluir vários **Serviços** (1:N).
- Um **Serviço** pertence a uma única **Ordem de Serviço** (N:1).

## Observações
- O sistema não contempla informações sobre pagamentos, mas seria uma adição interessante para futuras iterações.
- O sistema não inclui funcionalidades especificas de relatório ou avaliação pós-serviço, que também poderiam agregar valor ao projeto.
- Este projeto visa proporcionar uma melhor organização na gestão de ordens de serviço dentro da oficina, permitindo que todas as informações relevantes estejam disponíveis para consulta e gestão eficiente.
