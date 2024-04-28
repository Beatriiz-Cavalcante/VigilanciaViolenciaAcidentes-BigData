# Sistema de Vigilância de Violências e Acidentes (Viva)

<p>O Sistema de Vigilância de Violências e Acidentes (Viva) foi estabelecido pelo Ministério da Saúde em 2006, através da Portaria MS/GM nº 1.356, e é composto por dois componentes principais:

<li><b>Vigilância de Violência Interpessoal e Autoprovocada (Viva/Sinan):</b> Este componente monitora casos de violência interpessoal e autoprovocada por meio do Sistema de Informação de Agravos de Notificação (Sinan).</li>
<li><b>Vigilância de Violências e Acidentes em Unidades Sentinela de Urgência e Emergência (Viva Inquérito):</b> Este componente coleta dados em unidades de urgência e emergência para descrever o perfil das vítimas de violência e acidentes, identificar fatores de risco e propor medidas de prevenção.</li>
<br>
Segundo a Portaria de Consolidação nº 4 de 2017, são objetos de notificação compulsória casos suspeitos ou confirmados de violência doméstica e outras violências, e casos de violência sexual e tentativa de suicídio devem ser notificados imediatamente. O instrutivo de notificação de violência interpessoal e autoprovocada, publicado em 2016, define os objetos de notificação como casos suspeitos ou confirmados de diversos tipos de violência, incluindo violência doméstica, sexual, autoprovocada, tráfico de pessoas, entre outros.</p> 

<h2>Escolha do DataSet</h2>

<ul>
  <li><b>Relevância para a Saúde Pública:</b> O Viva é uma ferramenta crucial para monitorar a magnitude e gravidade das violências e acidentes. Ele fornece informações essenciais para entender e abordar problemas de saúde pública relacionados à violência interpessoal e autoprovocada, bem como acidentes.</li>
  <li><b>Subsídios para Políticas Públicas e Intervenções:</b> Os dados do Viva são utilizados para definir políticas públicas, estratégias e ações de intervenção, prevenção, atenção e proteção às pessoas em situação de violência. Portanto, a análise desses dados pode fornecer insights valiosos para a formulação e implementação de políticas e programas de saúde.</li>
  <li><b>Avaliação de Impacto de Intervenções:</b> Ao analisar os dados do Viva ao longo do tempo, é possível avaliar o impacto de diferentes intervenções e programas destinados a prevenir e reduzir a incidência de violências e acidentes.</li>
  <li><b>Identificação de Tendências e Padrões:</b> Através da análise exploratória dos dados do Viva, é possível identificar tendências temporais e geográficas, bem como padrões de violência e acidentes. Isso pode ajudar na alocação eficiente de recursos e na implementação de medidas preventivas direcionadas.</li>
  <li><b>Contribuição para a Pesquisa Acadêmica:</b> Os dados do Viva também podem ser utilizados como fonte para estudos acadêmicos e pesquisas científicas sobre violência e saúde pública. A análise desses dados pode levar a descobertas importantes e contribuir para o avanço do conhecimento na área.</li>
</ul>









<h2>Dicionário de Dados</h2>
<ul>
'TP_NOT' - Varchar2(1) Categoria: 1 – Negativa, 2 – Individual, 3 – Surto e 4 – Agregado. Descrição:Identifica o tipo da notificaçação. Campo obrigatório.

'ID_AGRAVO' - Varchar2(4). Categoria:Tabela de agravos do sistema 
com códigos (classificação internacional de doenças –CID 10) e nomes dos agravos classificados como notificação compulsória ( nacional, estadual ou municipal) e as síndromes ( febrehemorragia aguda;respiratória aguda; diarréia aguda; sanguinolenta;neurológica aguda; insuficiência renal aguda; outras síndromes. Descrição:Nome e código do agravo notificado segundo CID-10 (Centro Colaborador da OMS para a Classificação de Doenças em Português). Campo Chave: Preenchendo o código, a descrição é preenchida automaticamente, e viceversa; Ao exportar, é retirado o ponto.

'DT_NOTIFIC'- Date. Categoria: dd/mm/aaaa. Descrição:  Data de preenchimento da ficha de notificação. Campo Chave.

'SEM_NOT' - Varchar2(6). Categoria: Semanas no calendário epidemiológico padronizado. Descrição:Semana epidemiológica que o caso foi notificado. Características: Preenchida automaticamente a partir da data de notificação. 

'NU_ANO' - Varchar(4). Descrição: Ano da notificação. Características: Variável interna preenchida pelo sistema a partir da data de notificação.

'SG_UF_NOT' - Varchar2(2). Categoria: Tabela com códigos e siglas padronizadas pelo IBGE. Descrição: Sigla da Unidade Federativa onde está localizada a unidade de saúde (ou outra fonte notificadora) que realizou a notificação. A sigla é uma variável que está associada ao código na tabela. Campo obrigatório.

'ID_MUNICIP' - Varchar2(6). Categoria: Taebla com código e nome dos municípios do cadastro do IBGE (tabela municipi.dbf). Descrição: Código do município onde está localizada a unidade de saúde que realizou a notificação. O nome está associado ao código na tabela de municípios. Campo Chave: Preenhcendo o código, a descrição é preenchida automaticamente e vice-versa.

'ID_UNIDADE' - Number(7,0). Categoria: Código e nome da tabela do cadastro Nacional de Estabelecimento de Saúde (CNES). Descrição: Nome completo e código da unidade de saúde da área de abrangência da unidade notificadora. Campo obrigatório: Ao preencher o código, a descrição é preenchida automaticamente e vice-versa.

'DT_OCOR' - Date. Categoria: dd/mm/aaaa. Descrição: Data de ocorrência da violência. Campo obrigatório: Data menor ou igual (<=) a Data de Notificação.

'SEM_PRI' - Varchar2(6). Categoria: Semanas no calendário epidemiológico pradonizado. Descrição: Semana epidemiológica dos números sintomas. Características: Preenchida automaticamente a partir da data de primeiros sintomas no diagnostico. 

'ANO_NASC'

'NU_IDADE_N' - number(4). Categoria: A composição da variável obedece o seguinte critério: 1º dígito: 1. Hora, 2. Dia, 3. Mês, 4. Ano. 
Ex: 3009 – nove meses, 4018 – dezoito anos. Descrição: quando não há data de nascimento a idade deve ser digitada segundo informação fornecida pelo paciente como aquela referida por ocasião da data da ocorrência ou na falta desse dado é registrada a idade aparente. Características: Campo Obrigatório: Caso a data de nascimento não esteja preenchida. Preenchido automaticamente se Data de nascimento for preenchida. Calculada entre Data de nascimento e Data de
Ocorrência;Campo composto pela unidade de medida de tempo e numero da idade.- Se campo < 4007 (7 anos), campo escolaridade é preenchido com 10- Não se aplica.

'CS_SEXO' - Varchar2(1). Categoria: M - Maculino, F - Feminino, I - Ignorado. Descrição: Sexo do paciente. Campo obrigatório. Se sexo = masculino, desabilitar o campo Gestante.

'CS_GESTANT' - Varchar2(1). Categoria: 1. 1º Trimestre, 2. 2º Trimestre, 3. 3º Trimestre, 4. Idade gestacional ignorada, 5. Não, 6. Não se aplica, 9. Ignorado. Descrição: Idade gestacional da paciente. Campo obrigatório se sexo = F. Se sexo = Masculino ou idade menor ou igual a 10 anos, o campo é automaticamente preenchido com 6. Não se aplica. 

'CS_RACA' - Varchar2(1). Categoria: 1. Branca, 2. Preta, 3. Amarela, 4. Parda, 5. Indígena, 9. Ignorado. Descrição: Considera-se cor ou raã declarada pela pessoa. Campo essencial.

'CS_ESCOL_N' - Varchar2(2). Categoria: 43. Analfabeto, 1. 1ª a 4ª série incompleta do EF, 2. 4ª série completa do EF ( antigo 1° grau), 3. 5ª à 8ª série incompleta do EF (antigo ginásio ou 1° grau), 4. Ensino fundamental completo (antigo ginásio ou 1° grau), 5. Ensino médio incompleto (antigo colegial ou 2° grau), 6. Ensino médio completo (antigo colegial ou 2° grau), 7. Educação superior incompleta, 
8. Educação superior completa, 9. Ignorado, 10. Não se aplica. Descrição: Série e grau que a pessoa está frequentando ou frequentou consierando a última série concluída com aprovação ou grau de instrução do paciente por ocasião da notificação. Campo essencial: Preenchido automaticamente com a Categoria 10-não se aplica quando idade menor a 7 anos de idade. Quando caso notificado > 7 anos, campo não pode ser preenchido com categoria 10-não se aplica. 

'SG_UF' - Varchar2(2). Categoria: Tabela com códigos e siglas padronizados pelo IBGE. Descrição: Sigla da Unidade Federada de residência do paciente por ocasião de notificação. A sigla é uma variável que está associada ao código na tabela.
Campo obrigatório se residente no Brasil. Ao digitar a sigla da UF, o campo País é preenchido automaticamente com 'Brasil'. Se nenhuma UF for selecionada, os sitema pula automaticamente para seleção de outro país que não for o Brasil. 

ID_MN_RESI' - Varchar2(6). Categoria: Tabela com códigos e nomes padronizados pelo IBGE. Descrição: Código do município de residência do caso notificado. O nome está associado ao código na tabela de municípios. Campo obrigatório quando UF é digitada. São exibidos somente os municípios pertencentes à UF selecionada no capmo anterior. Permite digitação do nome do município ou do código IBGE. Quando digitado o nome, o código é preenhcido automaticamente e vice-versa.

'ID_PAIS' - Varchar(4). Categoria: Tabela com código e descrição de países. Descrição: País onde residia o paciente por ocasião da notificação. Campo obrigatório se UF for digitada este campo é preenchido automaticamente com 'Brasil'.

'NDUPLIC' - Varchar2(1). Categoria: 0 ou branco - Não identificado. 1. Não é duplicidado (não listar), 2. Duplicidade, Descrição: Identifica duplicidade. Descrição: Categorias de 1 e 2 atribuídas pelo usuário do sistema na rotina de duplicidade para identificar duplicidade que não devem ser listadas no relatório de duplicidade ou não devem ser computadas na incidência do agravo. Quando o registro estava marcado para 'não listar' e retornou para a rotina de duplicidade, é atribuída a categoria 0.

'DT_INVEST', 'ID_OCUPA_N', 'SIT_CONJUG', 

'DEF_TRANS' - Varchar2(1). Categoria: 1. Sim, 2. Não e 9. Ignorado. Descrição: Se o paciente possui algum tipo de deficiência/transtorno. Campo essencial. Se o 2 ou 9, pular para o campo 40. UF de ocorrência.

'DEF_FISICA' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Se o paciente possui algum tipo de deficiência física. Campo essencial. Se campo 38 for = 2 ou 9 preencher automaticamente com 
categoria = 8 (não se aplica).Se campo 38 = 1, não aceitar categoria = 8 (não se aplica).

'DEF_MENTAL' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Se o paciente possui algum tipo de deficiência mental. Campo essencial. Se campo 38 for =2 ou 9, preencher automaticamente com categoria 8 (não se aplica.). Se campo 38 = 1, não aceitar categoria 8 (não se aplica).

'DEF_VISUAL' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Se o paciente possui algum tipo de deficiência visual. Campo essencial. Se campo 38 for =2 ou 9, preencher automaticamente com categoria 8 (não se aplica.). Se campo 38 = 1, não aceitar categoria 8 (não se aplica).

'DEF_AUDITI' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Se o paciente possui algum tipo de deficiência auditiva. Campo essencial. Se campo 38 for =2 ou 9, preencher automaticamente com categoria 8 (não se aplica.). Se campo 38 = 1, não aceitar categoria 8 (não se aplica).

'TRAN_MENT' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Se o paciente possui algum tipo de transtorno mental. Campo essencial. Se campo 38 for =2 ou 9, preencher automaticamente com categoria 8 (não se aplica.). Se campo 38 = 1, não aceitar categoria 8 (não se aplica).

'TRAN_COMP' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Se o paciente possui algum tipo de transtorno de comportamento. Campo essencial. Se campo 38 for =2 ou 9, preencher automaticamente com categoria 8 (não se aplica.). Se campo 38 = 1, não aceitar categoria 8 (não se aplica).


'DEF_OUT' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Se o paciente possui algum tipo de outras deficiências/síndromes. Campo essencial. Se campo 38 for =2 ou 9, preencher automaticamente com categoria 8 (não se aplica.). Se campo 38 = 1, não aceitar categoria 8 (não se aplica).

'DEF_ESPEC' - Varchar2(30). Descrição: Especificar qual o tipo de outras deficiências/síndromes. Campo obrigatório se campo 39. Outras deficiências/síndromes = 1. 

'SG_UF_OCOR' - Varchar2(2). Categoria: Tabela com código dos estados padronizados pelo IBGE. Descrição: Sigla da Unidade Federada de ocorrência do evento por ocasião da notificação. Campo obrigatório.

'ID_MN_OCOR' - Varchar2(6). Categoria:  Tabela com código dos estados padronizados pelo IBGE. Descrição: Código e nome do município de ocorrência do evento notificado. Campo obrigatório: São exibidos somente os 
municípios pertencentes à UF selecionada no campo anterior.Digitação do nome do município ou do código: quando digitado o nome, o código é preenchido automaticamente e viceversa.

'HORA_OCOR' - Hora(hh:mm). Descrição: Informar a hora em que a violência ocorreu considerando o intervalo de 00:00 a 23:49s. Campo essencial.

'LOCAL_OCOR' - Varchar2(2). Categoria:01. Residência, 02. Habitação coletiva, 03. Escola, 04. Local de prática esportiva, 05. Bar ou similar, 06. Via publica, 07. Comércio/Serviços, 08. Industrias/ construção, 09. Outro, 99. Ignorado. Descrição: Informar o local de ocorrência do evento notificado. Campo obrigatório. Se a categoria selecionada for diferente de 09, pular para questão 53. 

'LOCAL_ESPE' - Varchar2(30). Descrição: Especificar outro local de ocorrência. Campo obrigatório se campo 52. Local de Ocorrência for igual a 9 - Outro.

'OUT_VEZES' - Varchar2(1). Categoria: 1. Sim, 2. Não e 9. Ignorado. Descrição: Informar se a violência é de repetição. Campo essencial. 
'LES_AUTOP' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Informar se a lesão foi autoprovocada. Campo essencial. 

'VIOL_FISIC' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu violência física. Campo obrigatório.

'VIOL_PSICO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu violência psicológica/moral. Campo obrigatório.

'VIOL_TORT' -  Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu tortura. Campo obrigatório.

'VIOL_SEXU'-  Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu violência sexual. Campo obrigatório.

'VIOL_TRAF' -  Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu tráfico de seres humanos. Campo obrigatório.

'VIOL_FINAN' -  Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu violência financeira/econômica. Campo obrigatório.

'VIOL_NEGLI' -  Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu negligencia/abandono. Campo obrigatório.

'VIOL_INFAN' -  Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu trabalho infantil. Campo obrigatório.

'VIOL_LEGAL' -  Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu intervenção legal. Campo obrigatório.

'VIOL_OUTR' -  Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu outro tipo de violência. . Campo obrigatório: Se categoria=2 ou 9, pular para o campo 57. Meio de agressão Força Corporal/Espancamento.

'VIOL_ESPEC' - Varchar2(30). Descrição: Especificar que outro tipo de violência ocorreu. Campo obrigatório: se campo 56-Outros for =1.

'AG_FORCA' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o meio da agressão foi através de força corporal. Campo essencial.

'AG_ENFOR' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição:Informar se o meio da agressão foi através de enforcamente. Campo essencial.

'AG_OBJETO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o meio da agressão foi através de objeto contundente. Campo essencial.

'AG_CORTE' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o meio da agressão doi através de objeto perfuro cortante. Campo essencial. 

'AG_QUENTE' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o meio de agressão foi atravpes de subst/objt quente. Campo essencial.

'AG_ENVEN' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o meio de agressão foi através de envenenamento. Campo essencial. 

'AG_FOGO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o meio da agressão foi através de arma de fogo. Campo essencial.

'AG_AMEACA' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o meio de agressão foi através de ameaça. Campo essencial.

'AG_OUTROS' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se ocorreu o meio de agressão foi através de outro. Características: Se categoria selecionada por =2 ou 9, pular para o campo 58. Se ocorreu violência sexual, qual tipo? - Assédio sexual.

'AG_ESPEC' - Varchar2(30). Descrição: Espeficiar qual outro meio de agressão sofreu. Campo obrigatório se o campo 57- Outro for =1. 

'SEX_ASSEDI'- Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Informar se ocorreu assédio sexual. Características: Campo essencial: Habilitado se campo 56-violência sexual for=1. Categoria 8 (não se aplica) se campo 56 – tipo de 
violência sexual for = 2 ou 9.

'SEX_ESTUPR' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Informar se ocorreu estupro. Campo essencial: Habilitado se o campo 56 - violência sexual for =1. Categoria 8 (não se aplica) se o campo 56 - tipo de violência sexual for =2 ou 9.

'SEX_PUDOR' - not found

'SEX_PORNO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição:Informar se ocorreu pornografia infantil. Campo essencial: Habilitado se o campo 56 - violência sexual for = 1. Categoria 8 (não se aplica) se campo 56 - tipo de violência sexual for = 2 ou 9.

'SEX_EXPLO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Informar se ocorreu exploração sexual. Campo essencial: Habilitado se campo 56 - violência sexual for =1. Categoria 8 (não se aplica) se campo 56 - tipo de violência sexual for =2 ou 9.

'SEX_OUTRO' - Varchar 2. Categoria: 1. Sim, 2. Não, 8. Não se aplica, 9. Ignorado. Descrição: Informar se ocorreu outro tipo de violência sexual. Campo essencial: Habilitado se campo 56 - violência sexual for =1. Categoria 8 (não se aplica) se campo 56 - tipo de violência sexual for 2 = ou 9. Se categoria selecionada for = 2, 8 ou 9, pular para campo 59. Procedimento realizado.

'SEX_ESPEC' - Varchar2(30). Descrição: Especificar qual outro tipo de violência sexual. Campo obrigatório se o campo 58. Se ocorreu violência sexual, qual tipo? - Outro =1. 

'PEN_ORAL', 'PEN_ANAL', 'PEN_VAGINA', 'PROC_DST', 'PROC_HIV', 'PROC_HEPB', 'PROC_SANG', 'PROC_SEMEN', 'PROC_VAGIN', 'PROC_CONTR', 'PROC_ABORT', 'CONS_ABORT', 'CONS_GRAV', 'CONS_DST', 'CONS_SUIC', 'CONS_MENT', 'CONS_COMP', 'CONS_ESTRE', 'CONS_OUTR', 'CONS_ESPEC', 'LESAO_NAT', 'LESAO_ESPE', 'LESAO_CORP', 'NUM_ENVOLV' - not found 

'REL_SEXUAL' - not found.

'REL_PAI' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era o pai. Campo obrigatório.

'REL_MAE' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era a mãe. Campo obrigatório.

'REL_PAD' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era o padrasto. Campo obrigatório.
 
'REL_CONJ' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era o cônjuge. Campo obrigatório. 

'REL_EXCON' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era o ex-cônjuge. Campo obrigatório. 

'REL_NAMO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era o namorado(a). Campo obrigatório.

'REL_EXNAM' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era o ex-namorado(a). Campo obrigatório. 

'REL_FILHO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o(a) provável autor(a) da agressão eram filho ou filha. Campo obrigatório.

'REL_DESCO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era desconhecido. Campo obrigatório.

'REL_IRMAO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era irmão ou irmã. Campo obrigatório. 

'REL_CONHEC' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão eram amigo(s)/conhecido(s). Campo obrigatório.

'REL_CUIDA'  - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era o cuidador. Campo obrigatório.

'REL_PATRAO'  - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era o patrão/chefe. Campo obrigatório.

'REL_INST'  - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era pessoa com relação institucional. Campo obrigatório.

'REL_POL'  - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era policial/agente da lei. Campo obrigatório.

'REL_PROPRI' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era a prórpia pessoa. Campo obrigatório. 

'REL_OUTROS'  - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão tinha algum outro tipo de relação. Campo obrigatório: Se categoria =2 ou 9, pular para campo 62. Sexo do provável autor da agressão. 

'REL_ESPEC'  - Varchar2(20). Descrição: Especificar outro tipo de relação com a pessoa atendida. Campo obrigatório se capmo 61. Relação com a pessoa atendida - Outros = 1 .

'AUTOR_SEXO' - Varchar2(1). Categoria: 1. Masculino, 2. Feminino, 3. Ambos os sexos, 9. Ignorado. Descrição: Informar o sexo do provável autor da agressão. Campo obrigatório.

'AUTOR_ALCO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição. Informar se o provável autor da agressão tinha suspeita de uso de álcool. 

'ENC_SAUDE' - - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento no setor da rede da saúde. Campo obrigatório.

'ENC_SENTIN', 'ENC_DEAM', 'ENC_DPCA', 'ENC_DELEG', 'ENC_MPU', 'ENC_MULHER', 'ENC_CREAS', 'ENC_IML', 'ENC_OUTR', 'ENC_ESPEC', 'ENC_TUTELA', 'ENC_ABRIGO', 
'ENC_VARA' - not found 

'REL_TRAB' - Varchar2(1). Categoria: 1. Sim, 2. Não e 9. Ignorado. Descrição: Informar se occoreu violência relacionada ao trabalho. Campo essencial se categoria =2 ou 9,  pular para o campo 68. Circunstância da lesão.

'REL_CAT' - Varchar2(1). Categoria: 1. Sim, 2. Não, 8. Não se aplica e 9. Ignorado. Descrição: Informar se foi emitida a CAT, caso a violência seja relacionada ao trabalho. Categoria = 8 se campo 66. Violência relacionada ao trabalho for =2 ou 9. Se campo 66. Violência relacionada ao trabalho for = 1, não permitir a categoria 8. não se aplica. 

'CIRC_LESAO' - Varchar2(5). Categoria: Tabela de agravos do sistema com códigos (classificação internacional de doenças - CID 10) e nomes dos agravos. Descrição: Nome e código do agravo. Campo essencial. 

'CLASSI_FIN' - not found
'EVOLUCAO' - not found
'DT_OBITO' - not found
'DT_DIGITA' - not found
'DT_TRANSUS' - not found
'DT_TRANSDM' - not found
'DT_TRANSSM', 'DT_TRANSRM', 'DT_TRANSRS', 'DT_TRANSSE' -  all not found

'REL_MAD' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se o provável autor da agressão era a madrasta. Campo obrigatório.

'TPUNINOT'- not found


'ORIENT_SEX' - Varchar2(1). Categoria: 1. Heterossexual, 2. Homossexual(gay/lésbica), 3. Bissexual, 8. Não se aplica, 9. Ignorado. Descrição: Orientação sexual do paciente. Campo Obrigatório se >=10 anos. Categoria (8) Não se Aplica se idade do paciente for <=9 anos.

'IDENT_GEN' - Varchar2(1). Categoria: 1. Travesti, 2. Transexual Mulher, 2. Transexual Homem, 8. Não se aplica, 9. Ignorado. Descrição: Identidade de gênero do paciente. Campo obrigatório se Campo Obrigatório se >=10 anos. Categoria (8) Não se Aplica se idade do paciente for <=9 anos. Se o campo 13 Sexo for igual (=) a Feminino (F) não permitir a categoria (4) Travesti.

'VIOL_MOTIV' - Varchar2(1). Categoria:01.Sexismo, 02.Homofobia/Lesbofobia/Bifobia/Transfobia, 03. Racismo, 04. Intolerância religiosa, 05. Xenofobia, 06. Conflito geracional, 07. Situação de rua, 08. Deficiência, 09. Outros, 88. Não se aplica, 99. Ignorado. Descrição: Informar se violência tem relação com características da vítima. Campo obrigatório.

'CICL_VID' - Varchar2(1). Categoria: 1. Criança, 2. Adolescente, 3. Jovem, 4. Pessoa adulta, 5. Pessoa idosa, 9. Ignorado. Descrição: Informar o ciclo de vida do provável autor da agressão. Campo obrigatório.

'REDE_SAU' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento no setor da rede saúde. Campo obrigatório.

'ASSIST_SOC' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento no setor da rede Assitencia Social. Campo obrigatório.
 
'REDE_EDUCA' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento no setor da rede Educação. Campo obrigatório.

'ATEND_MULH' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento no setor da rede atendimento à mulher. Campo obrigatório.
 
'CONS_TUTEL' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento para o Conselho Tutelar. Campo obrigatório.

'CONS_IDO' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento para o Conselho do Idoso. Campo obrigatório.
 
'DELEG_IDOS' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento para delegacia de atendimento ao idoso. Campo obrigatório.

'DIR_HUMAN' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento para centro de refência dos Direitos Humanos. Campo obrigatório.

'MPU' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento para Ministério Público. Campo obrigatório.

'DELEG_CRIA' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento para Delegacia Especializada de Proteção à Criança e Adolescente. Campo obrigatório.

'DELEG_MULH' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento para delegacia de atendimento à mulher. Campo obrigatório.

'DELEG' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento para outras delegacias. Campo obrigatório.

'INFAN_JUV' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento para justiça da infnância e da . Campo obrigatório.

<li>'DEFEN_PUBL' - Varchar2(1). Categoria: 1. Sim, 2. Não, 9. Ignorado. Descrição: Informar se houve encaminhamento para defensoria pública. Campo obrigatório.</li>

<li>'DT_ENCERRA' - Date. Categoria: dd/mm/aaaa. Descrição: Data de encerramento do caso. Características: Campo ≥ data da notificação.</li>
</ul>
<h2>Integrantes do grupo</h2>
<ul>
  <li>Ana Andrade</li>
  <li>Beatriz Cavalcante</li>
  <li>Mariah Cecilia</li>
  <li>Melksedec Silva</li>
  <li>Samuel Muniz</li>
  <li>Vinicius Fernando</li>
</ul>
