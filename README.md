# Schema Oficina Mecânica

## Objetivo

- Criar o schema conceitual para o contexto de oficina com base na narrativa fornecida.

## Narrativa

- Sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica.

- Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões periódicas.

- Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega.

- A partir da OS, calcula-se o valor de cada serviço, consultando uma tabela de referência de mão-de-obra.

- O valor de cada peça também irá compor a OS. O cliente autoriza a execução dos serviços.

- A mesma equipe avalia e executa os serviços.

- Os mecânicos possuem código, nome, endereço e especialidade.

- Cada OS possui: n°, data de emissão, um valor, status e uma data para conclusão dos trabalhos.

## Requisitos

### Entidades

**OS:** N°, Data de emissão, Preço, Status, Data de entrega

**Cliente:** Nome, ID, contato

**Veículo:** Modelo, Marca, Ano 

**Equipe:** ID_mecânicos

**Tabela:** ID, Nome do serviço, categoria
- **Concerto:** Descrição do concerto, valor concerto
- **Revisão:** Descrição da revisão, valor revisão

**Peças:**ID, Nome da peça, valor da peça

**Mecânico:** ID, Nome, Endereço, Especialidade

### Relacionamentos

- **Mecânico x Equipe (N, 1)** - Mecânicos da equipe

- **Equipe x OS (1, N)** - Equipe responsável pela OS

- **OS x Veículo (N, 1)** - Veículo da OS

- **Veículos x Cliente (N, 1)** - Veículos do cliente

- **OS x Cliente (N, 1)** - Autorização

- **OS x Tabela (N, N)** - Serviços da OS

- **OS x Peças (N, N)** - Peças da OS
