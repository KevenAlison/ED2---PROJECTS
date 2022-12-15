# Trabalho 03 - Unidade 02
## Directed Graph: Building a network with wikipedia

# Integrantes
- Gabriela Cruz Targino 
- Keven Alison dos Santos Bezerra

O vídeo com a explicação do trabalho encontra-se no seguinte link:
[Explicação T3U2](https://drive.google.com/file/d/1nxj1UIcBBA7tGQI-972MHAl2XkLSM0ds/view?usp=sharing)
Obs: Os algoritmos utilizados nesta análise tiveram como base o repositório do desenvolvedor [Alvaro].(https://github.com/alvarofpp/)

Este trabalho tem como objetivo fazer uma análise de uma rede digirida gerada a partir de uma página do WIKIPEDIA, mais especificamente a página do álbum de indie Rock "Know my Heart". Para a execução foi utilizada a linguagem python com o auxílio de bibliotecas de manipulação de grafos além da API da própria wikipédia para a coleta de dados.

## Coletando os dados

Inicialmente foi feita a coleta dos dados e sua devida inserção em formato de grafo. Para isso é definida uma SEED, que neste caso é o nome da página que desejamos ter como ponto de partida, e os STOPS, que são os pontos de parada da busca por links.

(código e imagem do grafo)

Como vamos realizar análises métricas para os dados coletados, é necessário realizar uma filtragem para melhorar os resultados que serão obtidos. Para isso, utilizamos duas etapas de filtragem de dados, na primeira eliminamos dados duplicados, e na segunda, dados que possuem apenas x vizinhos.

## Análise dos dados

### Análise Métrica

Na disciplina de Algoritmo e Estrutura de Dados II, para qual o presente trabalho foi feito, vimos algumas métricas utilizadas na análise de grafos com base nas interações entre os nós.

A primeira métrica é o **Degree Centrality**, esta métrica representa a quantidade de vizinhos que um determinado nó possui. 


<p align="center">
  <img width="70%" src="./Figuras/degree_centrality.jpg">
</p>

A proxima métrica analisada foi o **Closeness Centrality**, que nos mostra a distancia média de um nó em relação aos demais.

<p align="center">
  <img width="70%" src="./Figuras/closeness_centrality.jpg">
</p>

Em seguida foi a vez de analisar o **Betweenness Centrality** dos nós da nossa rede, essa métrica diz respeito à frequencia que um nó serve de "passagem" para a conexão de seus nós vizinhos.

<p align="center">
  <img width="70%" src="./Figuras/betweenness_centrality.jpg">
</p>

Por fim, temos o **Eigenvector Centrality**, que é uma métrica que mede a importância de um nó baseado na sua vizinhança.

<p align="center">
  <img width="70%" src="./Figuras/eigenvector_centrality.jpg">
</p>


### Distribuição de centralidade
Para esta análise vão ser levadas em consideração duas métricas mencionadas anteriormente, a Degree Centrality e a Closeness Centrality. A partir delas seram geradas duas funções: a PDF (Probability Density Function) e a CDF (Cumulative Density Function).

Inicialmente plotamos o histograma referente ao grau dos nós para analisarmos a rede de uma forma mais ampla. A partir dele é possível observar que grande maioria dos nós está na faixa do grau xx.

(Imagem histograma)

Seguindo a análise, fizemos o plot do PDF, que se trata da Função Densidade de Probabilidade. Essa função basicamente estima o valor de uma variável aleatória X com base em um dado valor Y. Para nosso contexto basicamente ela vai estimar quantos nós possuem certo valor de grau de centralidade.

<p align="center">
  <img width="70%" src="./Figuras/probability_density_function.jpg">
</p>

Em seguida foi plotado o gráfico referente ao CDFM, que se trata da Função de Distribuição Acumulada. Essa função basicamente estima a probabilidade de uma variável aleatória X ser menor ou igual a dado valor Y. Para nosso contexto basicamente ela vai estimar a probabilidade de uma certa quantidade de nós possuirem valor menor ou igual a um determinado grau de centralidade.

<p align="center">
  <img width="70%" src="./Figuras/cumulative_density_function.jpg">
</p>

### Análise de Distribuições
Para uma análise mais comparativa plotamos os gráficos correspondentes às métricas para observar como se comportam em comparação às demais.
<p align="center">
  <img width="70%" src="./Figuras/all.jpg">
</p>

### Decomposição do Core
<p align="center">
  <img width="70%" src="./Figuras/k-core_sociopatterns.jpg">
</p>

### Análise dos dados através do Software GELPHI
Enquanto realizavamos nosso trabalhao percebemos certas dificuldades em analisar a nossa rede quando ela estava muito extensa, fazedno com que reduzissemos bastante o numero de nós e links para que fosse possível uma visualização mais legível. Visando uma análise mais detalhada sobre a rede, utilizamos o software Gelphi para visualizarmos a nossa rede e suas características.
Agora que possuimos uma ferramente mais avançada, reduzimos algumas limitações na geração da nossa rede, permitindo que um grafo com mais nós e conexões fosse gerado. A partir dele utilizaremos plugins para gerar uma rede que seja capaz de transmitir suas informações visualmente através de sua divisão em comunidades, os quais representarão uma determinada métrica desejada.
