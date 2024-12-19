# diagramasSQL
Criei alguns diagramas usando o Workbench MySQL, a fim de praticar e entender os conceitos de relacionamentos entre entidades no SQL, como chave primária, chave estrangeira, herança e etc.

----------------------------------------------------------------------------------------DIAGRAMA ORDEM DE SERVIÇO----------------------------------------------------------------------------------------
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

------------------------------------------------------------------------------------------DIAGRAMA UNIVERSIDADE-------------------------------------------------------------------------------------------

Aluno

Cada aluno tem um ID único.
Alunos se matriculam em várias disciplinas.
Matriculado

Armazena quais alunos estão matriculados em quais disciplinas.
Disciplina

Cada disciplina tem um ID único.
Pode ter pré-requisitos.
É ministrada por um professor.
Pré-Requisito das Disciplinas

Liga as disciplinas aos seus pré-requisitos.
Pré-Requisitos

Representa os pré-requisitos que as disciplinas podem ter.
Professor

Cada professor tem um ID único.
Pertence a um departamento.
Departamento

Cada departamento tem um ID único, um nome e está em um campus.
Oferece vários cursos.
Curso

Cada curso tem um ID único.
Está associado a um departamento.
Disciplina do Curso

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



