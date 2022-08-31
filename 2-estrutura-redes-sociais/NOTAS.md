# Análise Estrutural de Redes Sociais

Investigar a estrutura da rede, tipicamente usando métricas da teoria dos
grafos.

É necessário entender as métricas, não apenas como elas são calculadas.

As referências estão ao final dos slides no site.

## Medidas de Centralidade (influência)

tldr; Medida de importância de um indivíduo na rede.

Têm por objetivo quantificar o quão central é a posição que um indivíduo ocupa
na rede. Há diversas medidas de centralidade diferentes, veremos apenas quatro a
seguir.

    Em análise de redes sociais a centralidade costuma estar ligada à
    importância, influência ou prestígio de um indivíduo.

### Centralidade de Grau (*centrality degree*)

tldr; Grau do vértice no grafo

É igual ao grau de cada individuo na rede. No caso de grafos direcionados,
existem duas medidas de centralidade de grau (de entrada e de saída).

  * Indica a quantos indivíduos o atual indivíduo está conectado (número de
    amigos, seguidos, seguidores, coautores, etc...)

  * Em grafos direcionados, tipicamente, a centralidade de grau de entrada é
    relacionada ao prestígio do indivíduo

### Centralidade de Proximidade (*Closeness Centrality (CP)*)

Medida para verificar o quão próximo um nó está em relação a todos os demais da
rede.
    * d: distância

    CP(x) = 1 / SUM(y)(d(x, y)) 

**OU**

    CP(x) = (n - 1) / SUM(y)(d(x, y))

Identifica nós que estão mais próximos dos demais, possuindo maior capacidade de
espalhar informações pela rede. Tipicamente utilizada em situações epidêmicas
também, para medir o grau de infecção

*olhar slide correspondente com o exemplo de centralidade em grafo
não-direcionado*

Em grafos disconexos ou digrafos que não são fortemente conexos, pode ser
calculada como:

    CP(x) = 1 / SUM(y)(d(x, y)) 

Onde *d(x, y) = n*, quando não houver caminho de *x* a *y*

*olhar slide correspondente com o exemplo de centralidade em grafo direcionado*

### Centralidade de Intermediação (Betweenness Centrality)

tldr; Medida de nós com maior tendência de obter uma informação mais rapidamente

Medida para verificar o quão presente um nó está nos caminhos mais curtos da
rede

    CI(x) = SUM ( delta(st)(x) / delta(st) )

Identifica nós que estão nos caminhos mais curtos (que fazem as ligações mais
rápidas) com os demais nós da rede. Nós com maior centralidade de intermediação
estão mais presentes nos fluxos de informação mais rápidos/eficientes da rede.

*meio confuso sem o exemplo, olhar no slide para grafos direcionados e
não-direcionados*

### Centralidade Page Rank

tldr; Medida da quantidade de páginas importantes que apontam para uma página.
Mais conhecido como "centralidade que fez o Google ficar popular"

Medida para verificar a importância de um nó com base na importância dos nós que
apontam para ele. Pode ser calculada iterativamente ou algebricamente.

*não consegui replicar a fórmula só com markdown, help*

*olhar exemplo... you get it by now*

### Coeficiente (Local) de Agrupamento (*Clustering coefficient*)

Mede a transitividade das relações do nó atual. Redes coesas/maduras tendem a
ter maiores coeficientes de agrupamento (maior transitividade das relações).

*fórmula longa... já sabe né?*


### Número de Nós e de Arestas

### Grau médio

Média dos graus dos vértices. Indica, na média, a quantos indivíduos cada
indivíduo está conectado. Fornece uma visão geral da conectividade da rede.
Muitas vezes usado em conjunto com o grau individual dos nós, para a realização
de análises comparativas.

### Densidade

Relação entre a quantidade de arestas existentes no grafo e quantidade máxima
para o respectivo número de nós.
    * E: quantidade de arestas

    Densidade = (2 * E) / (N * (N - 1))

Fornece uma visão geral da conectividade da rede. Costuma ser uma medida mais
estável do que o grau médio, possibilitando uma melhor comparação entre redes de
diferentes tamanhos. Redes Sociais mais densas costumam ser consideradas mais
maduras e/ou com melhor fluxo de informação

### Número de Componentes Conexos

Quantidade de componentes da rede. Ilustra em quantas partes a rede está
fragmentada. Componentes podem indicar, por exemplo, bolhas ideológicas ou
outros tipos de agrupamentos de indivíduos.

### Tamanho do Componente Gigante

Componente gigante é o maior componente conexo da rede (em relação ao número de
nós). O tamanho do componente gigante é a sua quantidade de nós.

Ter a maioria dos indivíduos no componente gigante, tipicamente é considerado
positivo para o fluxo ... (não deu tempo de digitar tudo)

### Tamanho do clique máximo

Clique máximo corresponde ao maior grupo de indivíduos totalmente conectados
entre si. Pode significar a presença de um grupo...

### Média dos Caminhos mínimos (MCM)

Caminho mínimo ou caminho geodésico corresponde ao menor caminho entre um par de
vértices. A média dos caminhos mínimos (*average shortest length*)...

Possuir uma MCM baixa, em Redes Sociais, tipicamente é visto de forma positiva,
indicando que, na média, os indivíduos estão próximos uns aos outros.

Teoria dos seis graus de separação\*.

### Diâmetro

Tamanho do maior caminho geodésico da rede. Caminho geodésico, entre dois nós,
corresponde ao caminho de menor tamanho entre esses nós.

Indica o caminho mais longo que uma informação precisará passar para atravessar
a rede.

Uma Rede Social com um diâmetro baixo costuma...

### Assortatividade

Correlação de Pearson dos valores dos graus entre pares de nós conectados. 

## Assortatividade em Redes Sociais

Analisa a homofilia da Rede Social. Tipicamente são analisadas características
diferentes do grau dos nós, por exemplo, cidade, gênero, profissão, idade e área
de atuação.

### Coeficiente (Global) de Agrupamento (*Clustering coefficient*)

    CA = ( 3 * ciclos(3) ) / triplas

sendo, *ciclos(3)* o número de ciclos de tamanho 3 e *triplas* o número de
triplas entre nós conectados em si, formando ou não um ciclo.

### Centralização (Freeman Centralization)

Mede o quão central é o nó mais central da rede em relação à centralidade dos
demais nós.

Há um valor de centralização para cada tipo de centralidade, e ela é calculada
pela divisão da soma da diferença das centralidades entre o *nó mais central e
os demais pela soma...*

*Adivinha?*

### :warning: Modularidade (Modularity) :warning:

Medida utilizada para verificar a **força** ou **'qualidade'** da divisão da
rede em grupos, comunidades, agrupamentos ou módulos.

Corresponde à fração entre a quantidade de arestas dentro de cada grupo menos a
fração esperada de arestas se estas forem distribuídas aleatoriamente.

Os algoritmos de agrupamento visam maximizar a modularidade.
