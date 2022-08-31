# Rede Social

Rede social é uma estrutura composta por _indivíduos_ (pessoas ou organizações)
que são conectadas por um ou mais tipos de _relações_

O conceito de redes sociais surgiu há séculos nas áreas de antropologia social e
sociologia, porém, apenas nas últimas décadas, os estudos em redes sociais se
intensificaram analisando tanto as características individuais de seus
componentes, como também as características estruturais da rede

# Análise de Redes Sociais Análise de Redes Sociais (ARS) vem sendo utilizada em
diferentes tipos de aplicação.

Até o início da década de 1980, a maioria das pesquisas era voltada para um
pequeno grupo de usuários, e os dados eram obtidos através de entrevistas e/ou
questionários

A partir dos anos 80, as análises passaram a ser feitas com milhares ou milhões
de indivíduos, devido ao surgimento dos computadores pessoais e as redes sociais
no formato digital. 

Redes sociais são tipicamente analisadas utilizando a teoria dos grafos ou
teoria de redes (**NÃO** são a mesma coisa). Há outros métodos utilizando
mineração de dados e mineração de textos/processamento de língua natural, que
tem se popularizado recentemente

# Representação de Redes Sociais

Redes sociais são tipicamente representadas como _grafos_.

## Grafos - Conceitos Básicos ### O que é um grafo?

Estruturas matemáticas que permitem codificar relacionamentos entre pares e
objetos. Os objetos são os _vértices_ do grafo

São representados como um conjunto de nós (vértices) conectados dois a dois por
linhas (arestas)

    ``` A - B - C - D ```

#### Grafos dirigidos Alguns grafos são dirigidos (ou direcionados) - digrafos.
As relações representadas pelas arestas têm sentido definido. As arestas só
podem ser seguidas em uma única direção.

Em grafos dirigidos, as arestas são _pares ordenados_ de vértices. Saindo de um
em direção ao outro Mesmo que ambos sejam o mesmo vértice (auto-laços -
*self-loop*)

#### Grafos não-dirigidos Podemos pensar num grafo não dirigido como um grafo
com arestas de sentido duplo

As arestas são _pares não ordenados_

Se (u, v) é uma aresta no grafo, então dizemos que _v_ é ... 

#### Comparando...

Em grafos não dirigidos, a relação de adjacência é simétrica ``` (u,v) <=> (v,u)
```

Já em grafos dirigidos, não necessariamente há essa simetria

Em grafos não dirigidos, o _grau de um vértice_ é o número de arestas que
incidem nele

Já em grafos dirigidos, o grau de um vértice é o número de arestas que _saem_ do
vértice mais o número de arestas que _chegam_ nele

Um _caminho_ de um vértice x a um vértice y é uma sequência de vértices que,
para cada vértice, do primeiro ao penúltimo, há uma aresta ligando esse vértice
ao próximo na sequência

Umm _ciclo_ acontece quando, a partir de um determinado vértice, pudermos
percorrer algum caminho que nos leve a esse mesmo vértice
    
    Em grafos dirigidos, o caminho deve conter pelo menos uma aresta

Em grafos não dirigidos, um ciclo deve conter pelo menos 3 arestas.

Grafos em que há ao menos um ciclo são chamados de _cíclicos_

Grafos em que não há ciclos são chamados de _acíclicos_

Um grafo não direcionado é _conexo_ (ou _conectado_) se cada par de vértices
nele estiver conectado por um caminho

Um grafo dirigido é _fortemente conexo_ se existir um caminho entre qualquer par
de vértices entre qualquer par de vértices no grafo

Um grafo dirigido é _conexo_ se possuir um caminho de u para v, _ou_ um caminho
de v para u, para cada par de vértices (u,v)

Um grafo dirigido é _fracamente conexo_ se a substituição de todas as suas
arestas por arestas _não-direcionadas_ produz um grafo conexo

Em grafos não dirigidos, um clique é um subconjunto de seus vértices tal que
cada par de vértices tal que cada par de vértices do subconjunto é conectado por
uma aresta

Grafos também podem ser _ponderados_ 

    Casos em que possuem pesos associados às suas arestas

Por fim, temos um tipo já conhecido de grafo...

A _árvore_

    * Grafo acíclico
    * Conexo
    * Não-dirigido

# Grafos -- Representação

## Como podemos representar um grafo?

Como um mapeamento de cada nó à lista de nós aos quais ele está conectado

### Representação computacional de grafos

Existem duas maneirais usuais de representar grafos:

#### Matrizes de adjacência Se o grafo for ponderado, podemos usar valores ao
invés de bits

``` 
Para diferenciar não aresta de um valor válido (como 0)? Deve-se definir um
valor padrão 
```
    
Se o grafo for dirigido

#### Lista de adjacências

Para cada vértice, temos uma lista ligada de seus vizinhos. Uma _lista de
adjacências_ de um grafo com `n` vértices consiste em ...

Se o grafo for ponderado, é necessário armazenar os pesos em cada elemento da
lista de vizinhos de cada vértice

## Quando usar uma ou outra representação?

Depende da aplicação, memória disponível, do problema que queremos resolver e
das operações que queremos executar

    Se denso (quando possui muitas arestas em relacão ao número de vértices) ou
    esparso (com poucas arestas)

### Grafo Bipartido

Os vértices podem ser divididos em dois conjuntos disjuntos. Não existem
vértices de um mesmo conjunto

### Multigrafo

Permite a existência de arestas múltiplas entre um mesmo par de vértices

### Grafo misto

Possui arestas direcionadas e não direcionadas

