# Obtenção, organização e análise de dados

Considerando que uma rede social é um conjunto de indivíduos e suas relações,
existe uma gama muito grande de possibilidades de redes a serem construídas e
analisadas.

Historicamente, muitas das primeiras redes analisadas eram compostas por
pequenos grupos de indivíduos (com laços familiares, geográficos, profissionais,
etc...)

Porém, com a popularização da internet e, em especial das redes sociais online,
se tornou possível analisar milhares ou milhões de indivíduos e suas relações.

## Obtenção dos dados

Redes sociais podem ser compostas de diferentes formas, por exemplo, a partir de
dados de publicações científicas. A Plataforma Lattes conta com o currículo de
7,3 milhões de pessoas. Contém relações de coautoria, orientação, participação
em bancas, participação em projetos, relações profissionais, etc...

A base de dados do [DBLP](https://dblp.org) (Digital Bibliography & Library
Project) conta com informações de mais de 3 milhões de pesquisadores que
publicaram artigos relacionados à ciência da computação.

### Formas de obter dados

* APIs
    * Gratuitas;
    * Licenças Acadêmicas;
    * Pagas;
* Web Crawlers
    * Muitas vezes bloqueado pelas próprias redes sociais;
* Conjuntos de dados disponíveis
    * Disponibilizados pelos mantenedores dos dados (p.e.: dados do DBLP);
    * Organizados em diferentes sites: Kaggle, UCI, Azure;
    * Disponibilizados de forma esparsa

## Cuidados com o uso dos dados

### Lei Geral de Proteção de Dados Pessoais (LGPD) 

* A lei cita "dados pessoais cujo acesso é público". Como essa categoria de
  dados deve ser tratada?

* "Deve ser tratada considerando a finalidade, a boa-fé e o interesse público
  que justificaram a sua disponibilização. A LGPD define, por exemplo, que uma
  organização pode, sem precisar pedir novo consentimento, tratar dados tornados
  anterior e manifestamente públicos pelo titular *(ela não pode, no entanto,
  repassar e/ou comercializar esses dados)*" 

### Comitê de Ética em Pesquisas (CEP)

Um CEP é um colegiado interdisciplinar e independente, de relevância pública, de
caráter consultivo, deliberativo e educativo, criado para defender os interesses
dos participantes da pesquisa em sua integridade e dignidade e para contribuir
no desenvolvimento da pesquisa dentro de padrões éticos.

### Plataforma Brasil

A Plataforma Brasil é o sistema oficial de lançamento de pesquisas para análise
e monitoramento do Sistema CEP/CONEP. O pesquisador deve realizar cadastro na
Plataforma Brasil para efetuar a submissão do projeto ao CEP.

### [Termo de Consentimento Livre e Esclarecido (TCLE)](www5.each.usp.br/tcle)

"O Termo de Consentimento Livre e Esclarecido (TCLE) é um documento no qual é
explicitado o consentimento livre e esclarecido do participante e/ou de seu
responsável legal, de forma escrita, devendo conter todas as informações
necessárias em linguagem clara e objetiva, de fácil entendimento, para o mais
completo esclarecimento sobre a pesquisa a qual se propõe participar (...) ."

## Limpeza de dados

Limpeza de dados é o processo de corrigir ou remover dados corrompidos,
incorretos, inválidos ou fora do contexto das análises que serão realizadas.

Muitas vezes descartamos dados que estão fora do padrão (outliers), ou colunas
que não iremos avaliar para termos dados mais concisos

### Enriquecimento do Conjunto de Dados

Busca por informações complementares (potencialmente de outras fontes), que
poderão ser utilizadas na análise de dados.

### Resolução de Entidades (*Entity Resolution*)

Tarefa de desambiguação do conjunto de dados de forma a identificar corretamente
as entidades tratadas, citadas ou analisadas.

#### Múltiplas aplicações, dependendo da análise que se pretende realizar.

* Identificar os diversos registros a respeito de uma netidade
* Identificar informações duplicadas
* Padronização na forma na qual uma entidade é referenciada

#### Entidades podem ser: 

* Pessoas
* Locais
* Instituições
* Produtos
* Datas ...

## Inteligência Artificial e ARS

Muitos problemas de análise de redes sociais são (ou podem ser) tratados
utilizando IA:

* Classificação
* Regressão
* Agrupamento
* Detecção de Anomalias (outliers) - e.g., identificação de bots

## KDD - Etapas/Tarefas

### Seleção

Seleção dos subconjuntos dos dados de interesse (registros e atributos)

Tarefa intimamente ligada ao problema que se deseja investigar

### Pré-processamento

O pré-processamento, juntamente com a limpeza de dados, pode envolver: remoção
de ruído e estratégias para lidar com NULLs

Descartar dados muitas vezes pode ser considerado em ARS, pois estamos lidando
com muitos dados (os dados são "baratos", altamente disponíveis). No entanto, em
alguma situações é desejável fazer o seu tratamento.

#### Valores Faltantes

Há 3 abordagens principais para lidar com valores faltantes: 

1. Descartar os registros com valores faltantes;
2. Descartar as colunas, atributos ou características com valores faltantes;
3. Preencher os valores faltantes (*missing value imputation*).

##### Preenchimento de valores faltantes

Além da tentativa de obter o valor faltante (por exemplo, por enriquecimento de
dados), há três abordagens principais para o preenchimento automático:

1. Preencher com o valor zero/nulo;
2. Preencher com média, moda ou mediana;
3. Preenchimento usando IA (por exemplo, com auxílio de um regressor ou
classificador).

### Transformação

Transformação dos dados para o formato que será apresentado ao algoritmo de
mineração de dados. Pode envolver agregação, normalização, criação de novos
atributos, redução de dimensionalidade (seleção de atributos ou projeção), etc.

Para dados textuais, envolve a transformação do texto em dados tabulares.

#### Mineração de Dados (propriamente dita)

* Identificação de regras de associação
* Criação do modelo de classificação
* Criação do modelo de regressão
* Agrupamento/Clusterização
* Identificação de Anomalias (Outliers)

### Análise/Interpretação dos Resultados

Análise crítica dos resultados obtidos, considerando não só as métricas de
avaliação, mas também o impacto de sua aplicação.

### Validação cruzada

O conjunto de treinamento e validação é subdividido em k subconjuntos (por exemplo, de forma aleatória)

O seguinte processo é executado k vezes...

#### Métricas de Desempenho/Avaliação

Existem diversas métricas para avaliar o desempenho de algoritmos de
classificação. Muitas delas podem ser obtidas a partir da *matriz de confusão*.

Matriz de confusão é uma tabela que apresenta o número de elementos que foram
classificados em cada classe em contraste com sua classe real.

##### Exemplos de métricas

Fórmulas no slide original

:warning: Não confundir **acurácia** com **precisão** :warning:

* Acurácia (accuracy/ACC): Taxa global de acertos
* Precisão (precision): Proporção de positivos avaliados corretamente
* Revocação (recall, sensibilidade) 
* Especificidade (specificity)
* Medida F1 (F1 score)

##### Métricas de Desempenho (Regressão)

Fórmulas no slide original

* Erro Absoluto Médio (*Mean Absolute Error (MAE)*)
* Erro Quadrático Médio (*Mean Square Error (MSE)*)
    * Penaliza mais os erros maiores em relação ao MAE
* Raiz Quadrada do Erro Quadrático Médio (*Root Mean Square Error (RMSE)*)

##### Métricas de Desempenho (Ranqueamento)

Fórmulas no slide original

* Coeficiente(s) de Correlação de Pearson
* Coeficiente de determinação (R^2)
* Média da Classificação recíproca (*Mean reciprocal rank (MRR)*)
* Ganho Cumulativo Descontado (DCG) e Normalizado (NDCG)
    * https://towardsdatascience.com/normalized-discounted-cumulative-gain-37e6f75090e9
* Precisão em k (*Precision at rank k*): número de itens relevantes entre os k
  primeiros ranqueados dividido por k

## Balanceamento dos Dados

Em diversas aplicações reais, a distribuição das classes no conjunto de dados
não é uniforme.

Por exemplo, dado um conjunto de usuários arbitrários de uma rede social,
provavelmente a *maioria não será de bots.*

E muitos algoritmos de aprendizagem de máquina podem 'aprender' a dar *preferência*
para a classe majoritária

Para evitar isso, podemos balancear o *conjunto de treinamento* de diversas
formas:

### Undersampling

Remoção dos elementos da classe majoritária até atingir a mesma quantidade de
elementos da classe minoritária

* Remoção aleatória de elementos
* Remoção de elementos redundantes
* Substituição de conjuntos de elementos 'próximos' por um novo elemento
  representativo do conjunto.

### Oversampling

Adicionamos elementos à classe minoritária até atingir a mesma quantidade de
elementos da classe majoritária.

* Repetição aleatória de elementos
* Criação de novos elementos de forma sintética
* Repetição/criação com base nos elementos 'mais difíceis' de classificar
