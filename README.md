# Hospital-Fundamental-MySQL

Um pequeno hospital local busca desenvolver um novo sistema que atenda melhor às suas necessidades. Atualmente, parte da operação ainda se apoia em planilhas e arquivos antigos, mas espera-se que esses dados sejam transferidos para o novo sistema assim que ele estiver funcional. Neste momento, é necessário analisar com cuidado as necessidades desse cliente e sugerir uma estrutura de banco de dados adequada por meio de um Diagrama Entidade-Relacionamento.

<h2>Modelo Entidade Relacionamento</h2>


![](https://cdn.discordapp.com/attachments/1030653726173696010/1039299532560793611/Captura_de_Tela_370.png)
** **

# Parte 2





## Os Segredos do Hospital

E não era exatamente aquilo! 

Após a primeira versão do projeto de banco de dados para o sistema hospitalar, notou-se a necessidade de expansão das funcionalidades, incluindo alguns requisitos essenciais a essa versão do software. As funcionalidades em questão são para o controle na internação de pacientes. Será necessário expandir o Modelo ER desenvolvido e montar o banco de dados, criando as tabelas para o início dos testes.
Faça login no Google para salvar o que você já preencheu. Saiba mais



No hospital, as internações têm sido registradas por meio de formulários eletrônicos que gravam os dados em arquivos. 

Para cada internação, são anotadas a data de entrada, a data prevista de alta e a data efetiva de alta, além da descrição textual dos procedimentos a serem realizados. 

As internações precisam ser vinculadas a quartos, com a numeração e o tipo. 

Cada tipo de quarto tem sua descrição e o seu valor diário (a princípio, o hospital trabalha com apartamentos, quartos duplos e enfermaria).

Também é necessário controlar quais profissionais de enfermaria estarão responsáveis por acompanhar o paciente durante sua internação. Para cada enfermeiro(a), é necessário nome, CPF e registro no conselho de enfermagem (CRE).

A internação, obviamente, é vinculada a um paciente – que pode se internar mais de uma vez no hospital – e a um único médico responsável.
O seguinte pedaço de Diagrama ER modela esses novos requisitos:

### Mãos a obra?

Faça a ligação do diagrama acima ao diagrama desenvolvido na atividade anterior, construindo relacionamentos com entidades relacionadas. E eleve o seu diagrama para que já selecionando os tipos de dados que serão trabalhados e em quais situações. 

Por último, crie um script SQL para a geração do banco de dados e para instruções de montagem de cada uma das entidades/tabelas presentes no diagrama completo (considerando as entidades do diagrama da atividade anterior e as novas entidades propostas no diagrama acima). Também crie tabelas para relacionamentos quando necessário. Aplique colunas e chaves primárias e estrangeiras.
Use ferramentas, como ERPlus, Lucidchart, draw.io (via web) e MySQL Workbench, ou mesmo um editor de imagens para o diagrama.  Você pode utilizar o MySQL Workbench ou o DBdiagram.io para montar os scripts SQL.

![](https://user-images.githubusercontent.com/110677627/200137457-6f215ecb-8f0d-48db-82cb-3f00f7c5590b.png)
** **
# O-Prisioneiro-dos-Dados - PARTE 3 - Alimentando o banco de dados

<strong>De que serve o banco sem dados? </strong>
Então vamos alimentar o banco! 

Com o banco de dados para o sistema hospitalar completamente montado, é necessário incluir dados para realizar os devidos testes e validar sua viabilidade quanto ao sistema. Nesta etapa, também é importante realizar a separação de alguns scripts iniciais para o banco, com os dados que serão necessários a um povoamento inicial do sistema.
** **
<strong>Jogando nas regras que você criou: <br>
Crie scripts de povoamento das tabelas desenvolvidas na atividade anterior<br>
Observe as seguintes atividades: </strong>


* Inclua ao menos dez médicos de 

* Ao menos sete especialidades (considere a afirmação de que “entre as especialidades há pediatria, clínica geral, gastroenterologia e dermatologia”).

* Inclua ao menos 15 pacientes.

* Registre 20 consultas de diferentes pacientes e diferentes médicos (alguns pacientes realizam mais que uma consulta). As consultas devem ter ocorrido entre 01/01/2015 e 01/01/2022. Ao menos dez consultas devem ter receituário com dois ou mais medicamentos.

* Inclua ao menos quatro convênios médicos, associe ao menos cinco pacientes e cinco consultas.

* Criar entidade de relacionamento entre médico e especialidade. 

* Criar Entidade de Relacionamento entre internação e enfermeiro. 

* Arrumar a chave estrangeira do relacionamento entre convênio e médico.

* Criar entidade entre internação e enfermeiro.

* Colocar chaves estrangeira dentro da internação (Chaves Médico e Paciente).

* Registre ao menos sete internações. Pelo menos dois pacientes devem ter se internado mais de uma vez. Ao menos três quartos devem ser cadastrados. As internações devem ter ocorrido entre 01/01/2015 e 01/01/2022.

* Considerando que “a princípio o hospital trabalha com apartamentos, quartos duplos e enfermaria”, inclua ao menos esses três tipos com valores diferentes.

* Inclua dados de dez profissionais de enfermaria. Associe cada internação a ao menos dois enfermeiros.

* Os dados de tipo de quarto, convênio e especialidade são essenciais para a operação do sistema e, portanto, devem ser povoados assim que o sistema for instalado.
** **
# PARTE 4 - Alterando o banco de dados

Pensando no banco que já foi criado para o Projeto do Hospital, realize algumas alterações nas tabelas e nos dados usando comandos de atualização e exclusão:

Crie um script que adicione uma coluna “em_atividade” para os médicos, indicando se ele ainda está atuando no hospital ou não. 

Crie um script para atualizar ao menos dois médicos como inativos e os demais em atividade.

# PARTE 5 - As Relíquias dos Dados

<strong>Mãos a obra
Crie um script e nele inclua consultas que retornem:</strong>
<ol>
<li>Todos os dados e o valor médio das consultas do ano de 2020 e das que foram feitas sob convênio.</li>
<li> Todos os dados das internações que tiveram data de alta maior que a data prevista para a alta.</li>
<li>Receituário completo da primeira consulta registrada com receituário associado.</li>
<li>Todos os dados da consulta de maior valor e também da de menor valor (ambas as consultas não foram realizadas sob convênio).</li>
<li>Todos os dados das internações em seus respectivos quartos, calculando o total da internação a partir do valor de diária do quarto e o número de dias entre a entrada e a alta.</li>
<li>Data, procedimento e número de quarto de internações em quartos do tipo “apartamento”.</li>
<li>Nome do paciente, data da consulta e especialidade de todas as consultas em que os pacientes eram menores de 18 anos na data da consulta e cuja especialidade não seja “pediatria”, ordenando por data de realização da consulta.</li>
<li>Nome do paciente, nome do médico, data da internação e procedimentos das internações realizadas por médicos da especialidade “gastroenterologia”, que tenham acontecido em “enfermaria”.</li>
<li>Os nomes dos médicos, seus CRMs e a quantidade de consultas que cada um realizou.</li>
<li>Todos os médicos que tenham "Gabriel" no nome. </li>
<li>Os nomes, CREs e número de internações de enfermeiros que participaram de mais de uma internação.</li>
</ol>

<strong>Observação 1: se necessário, inclua novos registros no banco de dados para testar adequadamente.  </strong>

<strong>Observação 2: podem ser úteis as funções de data do MySQL, como DATEDIFF(data1, data2) para número de dias entre duas datas, CURDATE() ou NOW() para data atual, DATE(dataehora) para extrair a data de um “datetime”, YEAR(data) para o ano de uma data, TIMESTAMPDIFF(YEAR, data1, data2) para número de anos entre duas datas, entre outras. 
Consulte a documentação do MySQL (“Date and Time Functions”) para mais informações.</strong>


