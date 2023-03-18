
# Prevendo preços de casa utilizando o ml no Bigquery

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
| ETAPA 1         |[Documentação de Contexto](https://github.com/Angel-arruda/puc-minas-projeto5-machinelearning/blob/main/README.md) <br> |
| ETAPA 2         |[Processo de Coleta de dados](https://github.com/Angel-arruda/puc-minas-projeto5-machinelearning/main/README.md)<br> [Modelo de dados inicial]([docs/template.md](https://github.com/Angel-arruda/puc-minas-projeto5-machinelearning/edit/main/README.md))  <br> [Governança de dados]([docs/template.md](https://github.com/Angel-arruda/puc-minas-projeto5-machinelearning/edit/main/README.md)) <br> [Arquivos utilizados]([docs/template.md](https://github.com/Angel-arruda/puc-minas-projeto5-machinelearning/edit/main/README.md)) <br> [Fonte](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques) |
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
  Sabe-se que o preço se um ativo mobiliario é determinado por caractéristicas como área,quantidade de comodos,tipo de comodos,tipo de área em que ele está localizado entre outros fatores mensuráveis/classificavéis. O conjunto de dados disponibilizado pelo Kaggle apresenta grande parte das variáveis que sabe-se compõe o preço de venda de uma residencia.
  Essas caracteristicas fazem com que esse processo seja um excelente candidato a técnicas de machine learning e por isso será objetivo deste trabalho embora seja preciso destacar que pretende-se aqui apenas demonstrar um exemplo de utilização de machine learning para esse fim pois ainda que seja possível treinar modelos de machine learning capazes de precificar um ativo,na prática,isto é em situações reais,a automatização completa de um processo como esses não é uma tarefa simples e necessitaria de conjunto de dados geograficamente diversificado e constantemente atualizado.
  
  
# Objetivos 
  
  O objetivo geral do trabalho é utilizar a ferramenta BigQuery do Google cloud para treinar um modelo de regressão linear com dados de vendas  de imóveis disponíveis na plataforma Kaggle.Espera-se que o modelo seja capaz de determinar com precisão,qual será o preço de um imóvel que não faça parte do conjunto de treino a partir de suas características.
  Outro objetivo  do trabalho é o desenvolvimento do conhecimento da aplicação de técnicas de machine learning e da utilização de ferramentas de cloud para esse fim, assim como o desenvolvimento do conhecimento de otimização de soluções pertinentes à temática.


  
# Descrição do processo de Coleta de dados


# Governança de dados

# Código

<li><a href=""> Código Fonte</a></li>

# Apresentação

<li><a href=""> Apresentação da solução</a></li>

