
# Machine Learning para previsão de preços de ativos imobiliários utilizando o BigQuery

`CURSO: Banco de dados`

`DISCIPLINA: Projeto - Arquitetura de dados em nuvem`

`SEMESTRE: 5º`



 Este trabalho faz parte do Eixo 5 da formação em Banco de dados da Pontifícia Universidade Católica,e tem como objetivo central demonstrar a execução de técnicas de Machine Learning em um ambiente de Cloud.Para a execução do projeto foi empregado como tema central a previsão de preços na área imobiliária,tema escolhido a partir dos conjuntos de datasets públicos disponibilizados na plataforma kaggle principalmente devido a atualidade do tema e a facilidade de acesso aos dados.
  Para execução do projeto foi escolhido como provedor de Cloud o Google Cloud devido a expertise anterior com a plataforma e ao conhecido desempenho da mesma.Neste sentido foi utilizado o Serviço BigQuery do GCP como ferramenta principal no projeto.O bigquery atuou em um primeiro momento como um Datawarehouse,onde os dados de preços de residencias retirados do kaggle foram inseridos e pre processados e em um segundo como ferramenta de Machine Learning para treinamento e teste do modelo de dados,visando a previsão dos preços de residencias a partir dos dados de teste.Após o treinamento foram realizadas ainda dentro da ferramenta a análise dos resultados e otimizações do treinamento.


## Integrantes <!-- em ordem alfabética -->


* [Angélica dos Santos](https://github.com/Angel-arruda)


## Orientador

* [Luigi Sanavia Neto]

# Planejamento

| Etapa         | Atividades |
|  :----:   | ----------- |
| ETAPA 1         |[Documentação de Contexto](https://github.com/Angel-arruda/puc-minas-projeto5-machinelearning/blob/main/README.md) <br> 
| ETAPA 2         |[Processo de Coleta de dados](https://github.com/Angel-arruda/puc-minas-projeto5-machinelearning/blob/main/README.md) <br>[Modelo de dados inicial](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data) <br> [Governança de dados](https://github.com/Angel-arruda/puc-minas-projeto5-machinelearning/blob/main/README.md) <br> [Arquivos utilizados](kaggle competitions download -c house-prices-advanced-regression-techniques) <br> [Fonte](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques) |
| ETAPA 3         |[Pré-processamento de dados]() |
| ETAPA 4        |[Aprendizagem de máquina]() |
| ETAPA 5         | [Análise dos resultados]() |
| ETAPA 6       | [Otimizações]() |


# Problema

  Em geral o processo de precificação de propriedades mobiliarias é altamente dependente de mão de obra humana e feito de maneira pouco automatizada.Normalmente ao decidir vender ativo é necessário entrar em contato com uma imobiliaria e solicitar uma avaliação,isto faz com que o processo seja demorado,inexato e muitas vezes enviesado por caracteristicas pessoais do avaliador.
  Essas caracteristicas tornam processo ineficiente para o do dono da propriedade interessado em vende-la,que em função do viés humano necessita muitas vezes ,aguardar alguns dias e até semanas para a disponibilidade da imobiliaria além de custear diversas avaliações para garantir que o valor estipulado não esteja abaixo do mercado,ou seja no processo hoje há uma demora na determinação do preço e altos custos,visto que normalmente a avaliação é paga.Do mesmo modo a ineficiencia do processo também afeta o cliente comprador,que acaba também necessitando consultar diversos avaliadores para confirmar que valor estipulado não está acima do mercado.
  No entanto ainda que o processo hoje seja feito com mão de obra humana,este processo pode ser automatizado pois são conhecidos os fatos que determinam o preço de uma propriedade e estes são em sua maioria,mensuráveis. 
  
  
  
 # Contexto
 
  Atualmente existe um conjunto de dados públicos dentro deste tema,contendo informações de preços de venda e caracteristicas de casas americanas nos últimos anos ,disponibilizado na plataforma Kaggle.
  Sabe-se que o preço se um ativo imobiliario é determinado por caractéristicas como área,quantidade de comodos,tipo de comodos,tipo de área em que ele está localizado entre outros fatores mensuráveis/classificavéis. O conjunto de dados disponibilizado pelo Kaggle apresenta grande parte das variáveis que sabe-se compõe o preço de venda de uma residencia.
  Essas caracteristicas fazem com que esse processo seja um excelente candidato a técnicas de machine learning e por isso será objetivo deste trabalho embora seja preciso destacar que pretende-se aqui apenas demonstrar um exemplo de utilização de machine learning para esse fim pois ainda que seja possível treinar modelos de machine learning capazes de precificar um ativo,na prática,isto é em situações reais,a automatização completa de um processo como esses não é uma tarefa simples e necessitaria de conjunto de dados geograficamente diversificado e constantemente atualizado.
  
  
# Objetivos 
  
  O objetivo geral do trabalho é utilizar a ferramenta BigQuery do Google cloud para treinar um modelo de regressão linear com dados de vendas  de imóveis disponíveis na plataforma Kaggle.Espera-se que o modelo seja capaz de determinar com precisão,qual será o preço de um imóvel que não faça parte do conjunto de treino a partir de suas características.
  Outro objetivo  do trabalho é o desenvolvimento do conhecimento da aplicação de técnicas de machine learning e da utilização de ferramentas de cloud para esse fim, assim como o desenvolvimento do conhecimento de otimização de soluções pertinentes à temática.


  
# Descrição do processo de Coleta de dados

Os dados foram coletados no dia 17/03/2022 do site Kaggle em formato de arquivo zip contendo 4 arquivos distintos:

train.csv - Dados de treino
test.csv - Dados de Teste
data_description.txt - Descrição dos dados.
sample_submission.csv - Exemplo de retorno que o modelo deve produzir.

Após a Coleta e desempacotamento dos arquivos,o total de Kb do arquivo foi 957.39 kB o mesmo sinalizado pelo site.

Em seguida foi feita a etapa de retenção dos arquivos,foram criadas as tabelas correspondentes aos arquivos e inseridos os dados do arquivo train.csv,que será utilizado na próxima etapa e do test.csv. Cada uma das tabelas contém a estrutura do arquivo e a descrição dos campos retirada do arquivo "data_description"

# Governança de dados


Requisitos do projeto:

Garantir a precisão dos dados,confiabilidade, integridade e segurança dos dados.

Classificação de confidencialidade de dados : Públicos quanto a visualização,não há dados sensíveis e impedimentos que impliquem confidencialidade dos dados.O papel de data view do Bigquery pode ser dado a qualquer pessoa com interesse em visualizar os dados,desde que ela esteja dentro da organização.


A)Coleta

Requisitos:A coleta de dados será feita manualmente no site Kaggle,registrando-se o horário e data.Deve-se observar o tamanho do arquivo garantindo que todos os dados tenham sido baixados.

Procedimentos: 
Os dados devem ser baixados do site Kaggle no computador do analista de dados em pasta correspondente.

Funções : Analista de dados - Responsabilidades:Baixar os dados no Site kaggle,garantindo a correta coleta de dados e completude dos arquivos.

B)Retenção

Requisitos:A retenção dos dados será feita no Bigquery,em uma tabela contendo os dados originais que deve ser mantida até o fim do projeto.

Procedimentos: 
Os dados devem ser inseridos no Bigquery a partir da criação de uma tabela baseada em arquivo CSV.Deve-se garantir que todas as colunas do arquivo sejam corretamente configuradas no Bigquery.A descrição de cada campo deve ser inserida como "Description" no Bigquery no momento de criação da tabela.

Funções : Analista de dados - Responsabilidades:Criar a tabela na ferramenta e inserir os arquivos CSV.


c)Processamento

Requisitos:O processamento deve ser feito no Bigquery,mantendo-se os dados manipulados em tabela separada dos dados originais porém no mesmo dataset.Deve ser mantido o histórico de processamento em uma query salva.Com o objetivo que o processo seja reproduzivel.

Procedimentos: Deve ser criada uma tabela com o mesmo nome da original contendo o final "Trusted",os dados devem ser copiados da tabela original para esta tabela e manipulados via SQL.Todas as querys feitas nestes dados devem ser salvas dentro do próprio Bigquery (A ferramenta faz isso automaticamente porém em conjunto o analista deve clicar em "Salvar query"e descrever o passo que foi executado.

Funções : Analista de dados - Responsabilidade: Fazer o tratamento e processamento dos dados,mantendo o histórico manual das querys conforme descrito acima.

D)compartilhamento 

De acordo com a classificação dos dados,os dados utilizados no projeto,bem como os resultados são públicos,não havendo restrições de compartilhamento.

Requisitos:O compartilhamento dos dados deve ser centralizado dentro do GCP,e feito via IAM(Identity acess managment do gcp,local aonde são centralizadas as permissões relativas as ferramentas) 

Procedimentos: Deverá ser dada a permissão de visualização de dados no Dataset contendo os dados do projeto para qualquer usuário dentro da organização(requisito geral para acesso ao ambiente GCP).
Quanto ao compartilhamento de edição dos dados: Buscando garantir a precisão e integridade dos dados,só será permitido o compartilhamento de visualização nos dados,apenas o analista de dados responsável pelo projeto tem autorização de editar os dados.

Funções : Engenheiro de Cloud - Responsabilidades:Garantir o permissionamento correto e compartilhamento dos dados com usuários interessados.

E)Eliminação

Classificação de retenção do ciclo de vida de dados: Período fixo - Os dados serão mantidos por um período de 90 dias no Bigquery.Este período é suficiente para realização do projeto,garantindo que a utilização do GCP não implique em custos desnecessários

Requisitos:O processo de eliminação dos dados do GCP deve ser automático.

Procedimentos: Para garantir a correta eliminação dos dados do GCP foi definido que o Dataset será configurado com um período de eliminação automático de 90 dias.

Funções : Analista de dados - Responsabilidades:Configurar o Dataset com a eliminação definita e verificar se os dados foram corretamente eliminados ao 
fim do projeto.




# Pré-processamento de dados
 
    Nesta etapa os dados foram pré processados na ferramenta Bigquery do Gcp,a ferramenta foi escolhida em função de conhecimento prévio na utilização flexibilidade e alta performace no processamento de grandes conjuntos de dados.Na ferramenta foram realizadas as seguintes etapas:
    
    
    
    Nesta etapa os dados foram pré processados na ferramenta Bigquery do Gcp,a ferramenta foi escolhida em função de conhecimento prévio na utilização flexibilidade,a ferramente é totalmente cloud based,não sendo necessário baixar programas ou configurar infraestrutura e além disso possui precisão e alta performace no processamento de grandes conjuntos de dados.Na ferramenta foram realizadas as seguintes etapas utilizando a linguagem Sql:
    
    
  
    Limpeza de dados: O BigQuery foi utilizado para alterar valores ausentes e valores duplicados.
    

    Transformação de dados: Os tipos de dados originais foram alterados com a função Cast
    

    Seleção de dados: Foram selecionadas as colunas necessárias para o modelo de Machine Learning,isto é com grande influencia nos preços e qualidade nos     dados e descartarta-das as colunas irrelevantes.
    

    Normalização de dados: Foi feita a normalização da coluna tipo de venda.
    

    Agregação de dados: Foi necessário fazer a agregação dos dados para encontrar outliers.

   


# Código

<li><a href=""> Código Fonte</a></li>

# Apresentação

<li><a href=""> Apresentação da solução</a></li>

