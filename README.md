# projeto-docker-mongo
Aula Banco de Dados

Exercícios
Cenário: Imagine que estamos gerenciando dados relacionados a clientes, processos e eventos em nosso sistema.

Exercício 1: Inserindo Dados



Clientes: Insira os seguintes clientes na coleção client:


JSON
{
  "full_name": "Maria Silva",
  "cpf": "12345678901",
  "email": "maria.silva@email.com",
  "phone": "11987654321",
  "address": "Rua das Flores, 123",
  "city": "São Paulo",
  "state": "SP",
  "zip_code": "01001000",
  "created_by": "user_id_do_admin_1",
  "enterprise": null,
  "cnpj_enterprise": null,
  "description": "Cliente individual"
}

JSON
{
  "full_name": "Empresa Soluções Ltda",
  "cpf": null,
  "email": "contato@solucoes.com.br",
  "phone": "21998765432",
  "address": "Avenida Principal, 456",
  "city": "Rio de Janeiro",
  "state": "RJ",
  "zip_code": "20010020",
  "created_by": "user_id_do_manager_2",
  "enterprise": "Soluções Ltda",
  "cnpj_enterprise": "12345678000190",
  "description": "Cliente corporativo"
}



Processos: Insira os seguintes processos para os clientes na coleção client_processes:


JSON
{
  "client_id": "id_do_cliente_maria_silva",
  "number": "PROC-2023-001",
  "value": 1500.00,
  "status": "ativo",
  "class": "Cobrança",
  "description": "Processo de cobrança referente a fatura em aberto.",
  "created_at": ISODate("2023-10-26T10:00:00Z")
}

JSON
{
  "client_id": "id_do_cliente_empresa_solucoes",
  "number": "PROC-2023-002",
  "value": 5500.50,
  "status": "em análise",
  "class": "Contratual",
  "description": "Análise de contrato de prestação de serviços.",
  "created_at": ISODate("2023-11-15T14:30:00Z")
}



Eventos: Insira os seguintes eventos na coleção events:


JSON
{
  "client_id": "id_do_cliente_maria_silva",
  "enterprise": null,
  "cnpj_enterprise": null,
  "freight": 50.00,
  "amount_of_cleaning": 2,
  "cleaning_date": "2023-12-10",
  "cost_of_each_cleanin": 200.00,
  "proposal_doc": "PROP-MS-001.pdf",
  "number_proposal": "PROP-2023-001-MS",
  "proposal_expiration_date": ISODate("2023-11-30T23:59:59Z"),
  "created_proposal_by": "user_id_do_sales_3",
  "address": "Rua das Camélias, 789",
  "city": "São Paulo",
  "state": "SP",
  "zip_code": "02002000",
  "proposal_status": "accepted"
}

JSON
{
  "client_id": "id_do_cliente_empresa_solucoes",
  "enterprise": "Soluções Ltda",
  "cnpj_enterprise": "12345678000190",
  "freight": 120.00,
  "amount_of_cleaning": 5,
  "cleaning_date": "2024-01-15",
  "cost_of_each_cleanin": 150.00,
  "proposal_doc": "PROP-ESL-002.pdf",
  "number_proposal": "PROP-2023-002-ESL",
  "proposal_expiration_date": ISODate("2023-12-20T23:59:59Z"),
  "created_proposal_by": "user_id_do_sales_3",
  "address": "Avenida das Palmeiras, 1011",
  "city": "Rio de Janeiro",
  "state": "RJ",
  "zip_code": "22020030",
  "proposal_status": "pending accepted"
}


Exercício 2: Consultando Dados



Clientes em São Paulo: Encontre todos os clientes que estão localizados na cidade de "São Paulo". 




Processos com Valor Superior a: Liste todos os processos na coleção client_processes cujo valor (value) seja maior que 2000.




Eventos com Proposta Pendente ou Aceita: Encontre todos os eventos onde o proposal_status seja "pending accepted" ou "accepted".




Clientes Corporativos: Liste todos os clientes onde o campo enterprise não seja null. Exiba apenas os campos full_name e cnpj_enterprise.




Processos de Cobrança: Encontre todos os processos cuja class seja "Cobrança" e ordene-os por valor em ordem decrescente.



Exercício 3: Atualizando Dados



Atualizar Status do Processo: Altere o status do processo com number "PROC-2023-001" para "concluído".




Adicionar Observação ao Evento: Adicione o campo note_doc com o valor "OBS-MS-001.txt" ao evento de Maria Silva.




Incrementar Quantidade de Limpezas: Aumente em 1 a amount_of_cleaning para o evento da Empresa Soluções Ltda.



Exercício 4: Excluindo Dados



Remover Processo: Remova o processo com number "PROC-2023-002".




Remover Clientes sem CNPJ: Remova todos os clientes onde o campo cnpj_enterprise seja null.



Exercício 5: Criando Índices



Índice no Nome do Cliente: Crie um índice no campo full_name da coleção client.




Visualizar Índices: Liste todos os índices da coleção client.



Lembre-se:


Substitua os placeholders de IDs ("id_do_cliente_...", "user_id_...") pelos IDs reais gerados pelo MongoDB ao inserir os documentos.

Preste atenção à sintaxe dos comandos e aos operadores utilizados.

Use o comando db.<colecao>.find() sem argumentos para verificar os dados após cada operação de inserção, atualização ou exclusão.
