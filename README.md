# diagramasSQL
Criei alguns diagramas usando o Workbench MySQL, a fim de praticar e entender os conceitos de relacionamentos entre entidades no SQL, como chave primária, chave estrangeira, herança e etc.
<br>
<hr>
DIAGRAMA ORDEM DE SERVIÇO
<hr>
Explicação: 
1- Do que se trata?

É um diagrama que criei, do que seria um "Fluxo de Serviço", ou um "fluxo de abertura de chamados" de uma empresa, usando o criador de modelagem de dados do próprio Workbench do MySQL.

2- Qual a finalidade?

Criei para poder ter uma melhor explicação visual de como funciona as chaves primárias e chaves estrangeiras dentro das tabelas de SQL, como uma tabela é diretamente ou indiretamente ligada na outra através de uma chave ou valor em comum.

3- Como funciona o fluxo?

Primeiramente, o cliente abre um chamado para o "Helpdesk" da empresa.
Note que o cliente possui algumas informações de identificação única, que cada cliente tem o seu, como ID, CPF e contato.

Nisso, é gerado um pedido, que por sua vez, também tem informações únicas como ID do pedido, descrição do que deve ser feito, data da solicitação, o ID do cliente que abriu essa ordem (chave estrangeira, usada para ligar o pedido ao cliente) e por fim, o status do pedido, se ele está liberado ou não para ser feito.

O pedido aberto, então será analisado, e um responsável será encarregado de atender o pedido com a ordem de serviço aberta. Repare que a análise contém chaves estrangeiras do ID do responsável, que conecta a análise, à quem irá atender a demanda através desse ID.

O pedido quando é aberto pelo cliente, gera automaticamente, uma ordem de serviço, contendo seu próprio ID, status, e uma chave estrangeira de "IdPedido", que liga o pedido com a ordem, pois um único pedido, pode gerar N novas ordens dependendo do que deve ser feito.

![Fluxo de Ordem de Serviço](https://github.com/user-attachments/assets/a8b67c0d-e320-4b13-a8d6-1af75aab3e45)

<br>
<hr>

DIAGRAMA UNIVERSIDADE
<hr>

Criei um pequeno projeto de diagrama no Workbench do MySQL que representa uma entidade-relacionamento (ER) para uma base de dados de uma universidade:

- Aluno
Cada aluno tem um ID único.
Alunos se matriculam em várias disciplinas.

- Matriculado
Armazena quais alunos estão matriculados em quais disciplinas.

- Disciplina
Cada disciplina tem um ID único.
Pode ter pré-requisitos.
É ministrada por um professor.

- Pré-Requisito das Disciplinas
Liga as disciplinas aos seus pré-requisitos.

- Pré-Requisitos
Representa os pré-requisitos que as disciplinas podem ter.

- Professor
Cada professor tem um ID único.
Pertence a um departamento.

- Departamento
Cada departamento tem um ID único, um nome e está em um campus.
Oferece vários cursos.

- Curso
Cada curso tem um ID único.
Está associado a um departamento.

- Disciplina do Curso
Liga as disciplinas aos cursos nos quais elas estão incluídas.

Relacionamentos:
Aluno: Um aluno pode se matricular em várias disciplinas.

Matriculado: Mostra quais disciplinas os alunos estão cursando.

Disciplina: Pode ter vários pré-requisitos e é ministrada por um professor.

Pré-Requisito das Disciplinas: Liga disciplinas aos seus pré-requisitos.

Professor: Um professor pode ministrar várias disciplinas e pertence a um departamento.

Departamento: Um departamento pode ter vários cursos e professores.

Curso: Um curso inclui várias disciplinas e pertence a um departamento.

Essas entidades e relacionamentos formam a estrutura básica de como a universidade gerencia alunos, disciplinas, professores, cursos e departamentos.

![Diagrama - Universidade](https://github.com/user-attachments/assets/649edd4d-d1de-487c-84c2-67f857595fbf)

<br>
<hr>
DIAGRAMA DA OFICINA AUTOMOTIVA
<hr>
<br>

Cliente:

Atributos:
idCliente: Identificador único do cliente (chave primária).
Nome do Cliente: Nome do cliente.
Veículo: Modelo do veículo do cliente.
CPF: Cadastro de Pessoa Física do cliente.
Contato: Informações de contato do cliente.
Relacionamento:
Um cliente pode ter uma ou mais ordens de serviço.
Ordem de Serviço:

Atributos:
idOrdem de Serviço: Identificador único da ordem de serviço (chave primária).
Data de Emissão: Data de emissão da ordem de serviço.
Cliente_idCliente: Referência ao cliente (chave estrangeira).
Mecânico_idMecânico: Referência ao mecânico responsável (chave estrangeira).
Relacionamentos:
Uma ordem de serviço pertence a um cliente.
Uma ordem de serviço pode ter um ou mais orçamentos.
Uma ordem de serviço é atribuída a um mecânico.
Mecânico:

Atributos:
idMecânico: Identificador único do mecânico (chave primária).
Nome: Nome do mecânico.
Especialidade: Especialidade do mecânico.
Relacionamentos:
Um mecânico pode ser responsável por uma ou mais ordens de serviço.
Um mecânico pode fazer parte de um ou mais orçamentos.
Orçamento:

Atributos:
idOrçamento: Identificador único do orçamento (chave primária).
Valor do Orçamento: Valor estimado do orçamento.
Mecânico Responsável: Nome do mecânico responsável pelo orçamento.
Ordem de Serviço_idOrdem de Serviço: Referência à ordem de serviço (chave estrangeira).
Ordem de Serviço_Cliente_idCliente: Referência ao cliente da ordem de serviço (chave estrangeira).
Mecânico_idMecânico: Referência ao mecânico responsável (chave estrangeira).
Relacionamentos:
Um orçamento pertence a uma ordem de serviço.
Um orçamento é feito por um mecânico.
Aprovação do Cliente:

Atributos:
idAprovação: Identificador único da aprovação (chave primária).
Orçamento aprovado: Indicação se o orçamento foi aprovado pelo cliente.
Orçamento_idOrçamento: Referência ao orçamento (chave estrangeira).
Orçamento_Ordem de Serviço_idOrdem de Serviço: Referência à ordem de serviço do orçamento (chave estrangeira).
Orçamento_Ordem de Serviço_Cliente_idCliente: Referência ao cliente da ordem de serviço do orçamento (chave estrangeira).
Cliente_idCliente: Referência ao cliente (chave estrangeira).
Mecânico_idMecânico: Referência ao mecânico responsável (chave estrangeira).
Relacionamentos:
A aprovação do cliente está ligada a um orçamento específico.
A aprovação do cliente referencia o cliente e o mecânico envolvidos.
Relacionamentos:

Cada cliente pode ter várias ordens de serviço (1:N).
Cada ordem de serviço pode ter vários orçamentos (1:N).
Cada mecânico pode ser responsável por várias ordens de serviço e orçamentos (1:N).
Cada orçamento pode ser aprovado ou não pelo cliente (1:1).
Esse diagrama mostra claramente como os dados estão organizados e como as diferentes entidades se relacionam dentro do contexto de uma oficina automotiva.

![Diagrama Oficina](https://github.com/user-attachments/assets/3a15f472-1386-4e96-bac4-31df94cd3fc4)




