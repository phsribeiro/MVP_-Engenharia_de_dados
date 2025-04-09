 

MVP 

 

ANÁLISE DE PERFORMANCE E EFICIÊNCIA DE CHILLER 

 

 

ENGENHARIA DE DADOS  

 

 

PONTÍFICA UNIVERSIDADE CATÓLICA DO RIO DE JANEIRO – PUC RIO  

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

ALUNOS:                                     

FELIPE CASTRO FERNANDES 

PAULO HENRIQUE DE SOUZA RIBEIRO      

 

INTRODUÇÃO 

O Brasil está entre os países com a energia elétrica mais cara do mundo, ocupando a sexta posição no ranking global. Segundo um levantamento da Federação das Indústrias do Rio de Janeiro (FIRJAN), realizado em 2018, o custo da energia no país é 46% superior à média internacional. Esse cenário representa um grande desafio para a competitividade da indústria nacional e impõe impactos significativos também ao setor de real estate, especialmente em empreendimentos comerciais de grande porte. 

Em edifícios comerciais, os sistemas de climatização são responsáveis por uma parcela expressiva do consumo energético. De acordo com a Empresa de Pesquisa Energética (EPE), vinculada ao Ministério de Minas e Energia (MME), o ar-condicionado pode representar até 60% da demanda total de eletricidade nesses empreendimentos. Isso torna os sistemas de refrigeração não apenas um item essencial para o conforto térmico dos usuários, mas também um dos principais vilões do ponto de vista financeiro e ambiental. 

O consumo energético associado aos chillers — equipamentos responsáveis pela refrigeração de grandes volumes de água para sistemas de ar-condicionado — representa um dos maiores custos operacionais em centros comerciais, como shopping centers. Dessa forma, a análise da performance e eficiência desses equipamentos é fundamental para garantir uma operação mais sustentável e economicamente viável. Identificar desvios em relação às especificações técnicas do fabricante e entender seus impactos no consumo são passos essenciais para propor melhorias que otimizem o desempenho energético e reduzam despesas recorrentes. 

Neste estudo, focamos a análise de operação de chillers instalados em um shopping center localizado no bairro de Botafogo, no Rio de Janeiro, durante um período de 90 dias. Dentro do contexto deste empreendimento, o consumo de utilidades corresponde a 35% dos gastos condominiais, sendo que 85% desse montante se refere exclusivamente ao consumo de energia elétrica, enquanto os 15% restantes estão ligados ao consumo de água. Esses dados evidenciam a relevância estratégica da gestão energética eficiente para a sustentabilidade financeira da operação — conforme ilustrado no gráfico a seguir. 

 

 

 

 

 

 

OBJETIVO 

 

Este projeto tem como foco a análise da operação de chillers instalados em um shopping center no Rio de Janeiro ao longo de um período de 90 dias. O objetivo principal é avaliar o desempenho desses equipamentos e compará-los com os parâmetros estabelecidos na folha de seleção do fabricante. A partir dessa comparação, será possível identificar eventuais desvios na operação, compreender seus impactos no consumo energético e propor medidas corretivas para aumentar a eficiência e reduzir custos operacionais.  

 

Para alcançar esse objetivo, este estudo busca responder às seguintes perguntas: 

 

Os chillers estão operando dentro dos limites de performance projetados pelo fabricante? 

Quais são os principais fatores que impactam a eficiência energética desses equipamentos? 

Há desvios significativos no consumo energético em comparação com os valores de referência? 

Qual é a eficiência energética dos chillers durante o período de análise? 

Como os desvios na operação afetam o consumo energético e os custos operacionais? 

Quais estratégias podem ser implementadas para otimizar a performance dos chillers e reduzir desperdícios? 

 

METODOLOGIA 

 

Com as perguntas-chave definidas, o próximo passo foi a obtenção dos dados necessários para a análise. Para isso, foram consultados catálogos e manuais técnicos dos fabricantes, além da realização de pesquisas bibliográficas sobre eficiência energética e consumo de equipamentos de refrigeração em empreendimentos comerciais. 

A coleta de dados foi realizada em tempo real por meio de um sistema de automação, garantindo maior precisão na análise. A abordagem adotada é predominantemente quantitativa, uma vez que os principais parâmetros analisados — como consumo energético, potência e eficiência operacional — são expressos em valores numéricos. O processo envolveu a coleta, modelagem e tratamento desses dados para compará-los com as especificações do fabricante. Além disso, foram consideradas variáveis externas que influenciam o desempenho dos chillers, como condições ambientais, e padrões de operação. 

Para o desenvolvimento das etapas do estudo, utilizaremos a plataforma Databricks Community Edition, uma versão gratuita do Databricks que permitirá a manipulação, análise e visualização dos dados coletados. 

O estudo foi realizado ao longo de 90 dias no shopping center localizado no Rio de Janeiro, permitindo uma análise contínua da operação dos chillers e a avaliação de seu desempenho em diferentes condições operacionais. 

Ao final do estudo, será feita uma discussão sobre o atingimento dos objetivos inicialmente traçados, destacando quais perguntas puderam ser respondidas com os dados obtidos e quais pontos exigem aprofundamento em estudos futuros. 

 

DETALHAMENTO 

 

Busca pelos Dados 

 

Os dados utilizados neste estudo foram coletados diretamente do sistema de automação predial de um shopping center localizado na cidade do Rio de Janeiro, ao longo de um período contínuo de 90 dias. A base contempla registros diários de consumo de energia elétrica (em kW) e carga térmica (em TR) de três chillers operando em um sistema real de HVAC (Heating, Ventilation and Air Conditioning). Para viabilizar o desenvolvimento do projeto e facilitar o acesso às informações, os dados foram organizados e publicados na plataforma Kaggle, permitindo sua posterior utilização em análises exploratórias, modelagens e validação dos objetivos propostos. 

 

Origem: Dataset criado e publicado no Kaggle 

Link do dataset: https://www.kaggle.com/datasets/felipecfernandes/eficincia-hvac-bps 

 

Coleta e Armazenamento em núvem 

 

Os dados são baixados diretamente do Kaggle para o ambiente Databricks utilizando o pacote kaggle.  Interface gráfica do usuário, Texto, Aplicativo

O conteúdo gerado por IA pode estar incorreto. 

 

Modelagem de Dados 

Foi adotado o modelo flat (Data Lake) com uma única tabela de catálogo de dados contendo os registros diários de operação dos chillers. 

 

Coluna 

Tipo 

Descrição 

Valores Esperados 

DATA 

Date 

Data da medição 

01/01/2024 a 31/03/2024 

kW_CHILLER1 

Float 

Consumo de energia do Chiller 1 

0 a 270 

TR_CHILLER1 

Float 

Carga térmica do Chiller 1 

0 a 240 

kW_CHILLER2 

Float 

Consumo de energia do Chiller 2 

0 a 270 

TR_CHILLER2 

Float 

Carga térmica do Chiller 2 

0 a 240 

kW_CHILLER3 

Float 

Consumo de energia do Chiller 3 

0 a 270 

TR_CHILLER3 

Float 

Carga térmica do Chiller 3 

0 a 240 

TEMP_EXTERNA 

Float 

Temperatura ambiente externa 

10 a 38 

 

NOTA: Nota: Os valores apresentados na tabela correspondem as indicações da folha de seleção do fabricante do equipamento. O arquivo pode ser consultado no notebook do GITHUB.  

  

Carga de Dados 

 

Todo o processo foi desenvolvido e executado no ambiente de notebooks da Databricks, que oferece uma interface interativa e integrada ao cluster Spark. A principal linguagem utilizada ao longo dessa etapa foi o Python, com apoio da biblioteca PySpark, que permite o processamento distribuído dos dados e a manipulação eficiente de grandes datasets em ambientes escaláveis. 

 

A carga inicial consistiu na importação dos arquivos no formato CSV, contendo registros diários dos chillers. Esses arquivos foram lidos e convertidos em DataFrames PySpark, tratados e posteriormente salvos como tabelas gerenciadas Delta no metastore do Databricks. 

 

É importante destacar que não houve necessidade de junção ou conciliação de diferentes fontes de dados. Todo o conteúdo relevante já se encontrava consolidado em um único conjunto de dados, o que simplificou significativamente o processo de transformação. 

 

As transformações realizadas foram voltadas principalmente para o enriquecimento das variáveis originais, como o cálculo da eficiência energética individual de cada chiller (relação entre carga térmica e consumo de energia), padronização dos tipos de dados, formatação de colunas temporais e validação de consistência entre os registros. 

 

Essa abordagem direta e bem estruturada favoreceu a fluidez do pipeline de dados, permitindo que os dados estivessem prontos para análise de forma ágil e com integridade assegurada.	 

 

 

 

 

 

 

 

 

Leitura e Transformação  

 

Texto

O conteúdo gerado por IA pode estar incorreto. 

 

Carga de Dados 

 

Interface gráfica do usuário, Texto, Aplicativo

O conteúdo gerado por IA pode estar incorreto. 

 

 

 

 

 

 

 

Análise de Dados 

 

Qualidade de Dados e Solução do Problema 

 

Vamos dividir a etapa de análise em duas: qualidade de dados e solução do problema.  

   

a. Qualidade de dados  

Deve ser feita uma análise da qualidade para cada atributo do conjunto de dados. Existem problemas no conjunto de dados? Caso haja, como esses problemas podem ser resolvidos para que não afetem as respostas das perguntas que quer solucionar?  

É possível que não se encontre problemas nos conjuntos de dados, em alguns casos há conjuntos de dados curados e já bem tratados antes de serem disponibilizados. Entretanto, mesmo nestes casos, espera-se que seja feita uma análise de valores por atributo e que se demonstre que não se encontrou problemas.  

   

          b. Solução do problema  

Chegou o momento de se solucionar o problema em questão, definido preliminarmente nos objetivos. Deve-se buscar respostas para as perguntas elencadas. Para cada resposta obtida tecnicamente através da análise dos dados deve haver uma discussão do seu resultado, conectando os números obtidos às respostas ao problema a ser solucionado.  

Ao final, deve haver uma discussão de uma forma geral sobre a solução do problema a partir das discussões de cada resposta.  

Aqui, podem ser utilizadas bibliotecas Python vistas na disciplina Análise Exploratória e Pré-Processamento de Dados, ou as ferramentas vistas na disciplina Visualização de Informação. Entretanto, caso não tenha ainda cursado estas disciplinas, é possível responder as perguntas do objetivo somente através da linguagem SQL, objeto da disciplina de Banco de Dados ou através da linguagem de consulta do banco NoSQL escolhido, objeto da disciplina de Data Warehouse.  

Entrega  

Deverá ser disponibilizado todo código construído em um repositório público do GitHub. Se tiver dúvidas sobre como criar um repositório público no GitHub, consulte https://docs.github.com/pt/repositories/creating-and-managing-repositories/creating-a-new-repository  

Algumas tarefas das etapas do trabalho podem ser feitas a partir de componentes visuais da plataforma de nuvem. Desta forma, deve se gerar evidência da execução destes passos através de screenshots ou vídeos.  

Deve se gerar evidência dos resultados das respostas às perguntas que definem o problema do MVP através de screenshots ou vídeos.  

 

AUTOAVALIAÇÃO 

 

Ao finalizar o trabalho, é esperado que o aluno faça uma autoavaliação contendo uma discussão sobre se conseguiu atingir os objetivos delineados antes do início das outras etapas, suas dificuldades encontradas na execução do trabalho, bem como trabalhos futuros para enriquecer o problema e sua solução em seu portifólio.  

 

REFERÊNCIAS BIBLIOGRÁFICAS 

ABRAVA. Eficiência energética ganha cada vez mais importância no setor de  refrigeração – FEBRAVA. Disponível em < https://abrava.com.br/eficiencia-energetica-ganha-cada-vez-mais-importancia-no-setor-de-refrigeracao-febrava/ > . 

 

 

 

 

 
