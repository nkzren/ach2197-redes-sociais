# Processamento de Linguagem Natural (PLN)

Nessa disciplina, será utilizada para auxiliar os processos de mineração de
texto (*Text mining*)

## Descoberta de conhecimento

A maioria dos algoritmos de mineração de dados recebe como entrada dados
estruturados, no formato de uma tabela em que cada linha representa uma
instância e cada coluna representa um atributo (características ou variável).

Para a utilização de textos por estes algoritmos é necessário que os textos
sejam convertidos/transformados para um formato estruturado.

## Atividades/Tarefas Básicas

As técnicas descritas nessa seção possuem resolver uma ou mais das seguintes
perguntas:

* Como dividir meu texto?
* O que significa cada unidade de divisão do texto?
* Como classificar cada unidade de texto?

### Técnicas

* *POS tagging (Part-of-speech tagging)*: Substituição das palavras por suas
  classes gramaticais (substantivos, verbos, adjetivos, advérbios, etc...)

* Remoção de *stop-words* (ou "palavras vazias"): Remoção de palavras que são
  insignificantes no contexto da análise que será realizada (por exemplo,
  artigos e preposições)

* Conversão de todas as letras para caixa baixa, remoção de acentos e caracteres
  especiais

* Lematização (*lemmatization*): ato de retirar flexões/conjugações de palavras
  de forma a retorná-las a um formato padronizado (de dicionário)

* Radicalização (*stemming*): ato de reduzir palavras à sua raiz/radical

* Tokenização (*tokenization*): separação do texto em unidades básicas
  (palavras, fonemas, caracteres, etc...)

* n-gramas (ou unigramas): sequência contínua de itens (por exemplo, n tokens)

* *BOW (bag-of-words)* - saco de palavras: equivalente ao unigrama de palavras

### Representação

Os textos podem ser representados, de forma estruturada, como conjuntos de
n-gramas de *tokens* (caracteres, fonemas, palavras, classes gramaticais,
etc...)

Cada linha corresponde a um texto (por exemplo, uma postagem) e cada coluna
representa um n-grama (por exemplo, uma palavra)

Cada célula indica que o texto contém ou não respectivo token (ou conjunto de
tokens):

* De forma binária;
* Contagem (valor absoluto ou relativo);
* TF-IDF (*term frequency - inverse document frequency*)

## PLN - Algumas aplicações

* Reconhecimento de Entidade Nomeada (*Named Entity Recognition (NER)*):
  Identificação de quais itens do texto se referem a entidades nomeadas (nomes
  de pessoas, lugares, organizações, etc...) e quais são os tipos dessas
  entidades

* Análise de Sentimentos (*Sentiment Analysis*): pode envolver a identificação
  dos sentimentos presentes numa sentença e/ou de sua polaridade (positiva,
  negativa ou neutra)

* Detecção de posicionamento (*Stance detection*): identificação do
  posicionamento do texto em relação a algo (a favor, contra, neutro/sem
  posicionamento)

* Extração de termos/tópicos (*Terminology/Topic extraction/Topic modeling*):
  identificação dos principais termos de uma sentença ou do tópico/assunto que
  está sendo discutido


