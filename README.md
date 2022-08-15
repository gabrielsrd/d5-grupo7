# CTEDS: D5 - Grupo 7

### Repositório criado para a disciplina D5 - Metodologias Ágeis do curso CTEDS

Nas issues está definido o Escopo do projeto (Proposta Projeto #1) como também os assuntos dos cards apresentados no board (Projects -> CTEDS - D5)

# 1. Visão Geral

<p align="center">
  <img src="https://github.com/gabrielsrd/d5-grupo7/blob/main/assets/logo.jpg?raw=true" alt="Sublime's custom image"/>
</p>

<p align="center">
  <strong>Strategy Crawler</strong>
</p>

Demandas estratégicas são difíceis de tomar, cada vez mais o acúmulo de dados permite ter uma abrangente visão, mas dificulta o olhar o crítico em pequenos cenários e compará-los com o mercado, gerando dúvidas para o tomador de decisão do negócio sobre as melhores decisões a se tomar, envolvendo questões de tendência de mercado, alocação de recursos, estoques, preços etc.

Neste cenário, propomos o Strategy Crawler, uma ferramenta de automação que permite o usuário buscar, através de palavras-chaves sobre produtos, de forma totalmente automatizada e veloz, os principais detalhes disponibilizados nos maiores e-commerces do mercado. De forma resumida, iterativa e analítica, o software busca informações sobre as principais tendências sobre um produto, buscando informações sobre “rankeamento” dos usuários, range de preços, projeção de vendas, disponibilidade/falta no mercado, gerando esses dados com base em buscas nos principais sites de vendas. Essas informações são disponibilizadas para o usuário através de gráficos e resumos informativos, com o objetivo do consumidor final possuir em suas mãos uma ferramenta de análise rápida e prática.

# 2. Escopo do projeto

A plataforma que será desenvolvida como proposta para a disciplina Metodologias Ágeis do curso CETDS será o Strategy Crawler, uma aplicação PWA, ou seja, um sistema web que se adapta de acordo com o aperelho que está se conectando a plataforma, facilitando assim o acesso pelo usuário final, donos/tomadores de decisões de negócios online, aos menus de filtros de pesquisa por tópicos e e-commerces, e aos resultados gerados através da inspeção do robô em gráficos iterativos e resumos detalhados. Essa adaptapitatividade auxilia o usuário a visualizar seu histórico de pesquisas e resultados, permitindo melhores insights com base numa linha histórica de tendência de mercado observável. Ainda deve permitir acesso a ferramentas de previsibilidade, colhendo informações de pesquisas realizadas e gerandos dados inferidos sobre tendência de mercado para um setor, percentual aproximado de vendas, projeções de lucros etc.  

# 3. Arquitetura do projeto

O projeto está dividido em 4 áreas principais para facilitar o desenvolvimento e distribuição das equipes
  1. FrontEnd: Tela Web disponivel para os clientes com as análises obtidas a partir dos dados coletados, permitindo uma interação visual
  2. BackEnd: Banco de dados relacional para o armazenamento dos dados coletados e APIs de conexão
  3. Bot: Crawler para cada site de vendas online, responsável por obter os dados
  4. Análise de dados: Análise dos dados obtidos, utilizando técnicas estatísticas clássicas e alguns algoritmos de Machine Learning

## 3.1 Tecnologias

Para desenvolvimento das propostas citadas acima foi escolhida as seguintes tecnologias:

### 3.1.1 Crawler

Crawlers são robôs automatizados escritos em código de programação que possuem a responsabilidade de raspar a *web*, ou seja, realizam pesquisas em sites pré-definidos e extraem informações úteis segundo a lógica desenvolvidada pelo programador, tudo isso em tempo de execução do programa. Essa estratégia é muito utilizada em *data analytics* pelas empresas. No projeto, nossos crawlers serão desenvolvidos utilizando a linguagem Python, principalmente usando a biblioteca Selenium, por ter a possibilidade de interagir com a página simulando interações reais, é possível realizar testes de interface web de forma automatizada em toda a aplicação desenvolvida, além de ser muito empregado pela industria.

### 3.1.2 Frontend

O Frontend será uma aplicação PWA, caracterizada por ser um sistema *adaptativo*, onde os dados são apresentados para o usuário em modelos que variam de acordo com o tamanho do *screen* utilizado pelo usuário que realiza a requisição da página. Esse tipo de funcionalidade é muito empregada hoje, permitindo que o usuário tenha mais conforto e interação com as páginas, onde os dados são dispostos da melhor forma possível de acordo com o aparelho. A tecnologia utilizada na construção será o Vue.JS, um framework Javascript *open-source*, focado no desenvolvimento de interfaces de usuário e aplicativos de páginas únicas. Tecnologia muito utilizada atualmente, foi escolhida devido a curva de aprendizado ser relativamente pequena e apresentar um sistema de desenvolvimento de componentes reutilizaveis.

### 3.1.3 Middleware

Característica principalmente de aplicações orientadas a microserviços, a presença de um middleware facilita o redirecionamento de requisições, redirecionando para os serviços que podem processar corretamente o chamado. Na nossa aplicação, temos uma estrutura de backend dividida em 3 módulos, a primeira API será responsável por fazer todo o processamento de requisições referentes a dados de usuários, a segunda processa requisições relacionadas as informações dos Crawlers, e a última tem responsabilidade de processar/trabalhar os dados e realizar os trabalhos de IA.

### 3.1.4 API: NodeJS

As API's possuem a responsabilidade de processar as informações requisitadas pelo frontend e devolver as devolvê-las para análise e interação do usuário. A tecnologia utilizada para o desenvolvimento será o NodeJS, sendo muito empregada no mercado, possuindo uma estrutura de código aberto, multiplataforma, permitindo a execução de códigos fontes em Javascript, um fácil e prático gerenciamento embutido de pacotes/bibliotecas conhecido como npm (node package manager), ser notoriamente leve (não exige muitos recursos computacionais para sua execução) e produtivo (muitas bibliotecas e pacotes já implementados pela comunidade). A primeira, conectada ao banco Postgres, possui a responsabilidade de realizar todo o processamento de requisições voltado para dados de usuários, realizando autenticação/autorização, salvar/alterar/deletar/buscar dados de usuário e gerenciamento de histórico de usuário. A segunda API possui a responsabilidade de gerenciar os dados retornados pelos crawlers de pesquisa, realizando o tratamento dos dados e salvando/buscando informações em banco NoSQL.

### 3.1.5 Banco de dados: Postgres

Os bancos relacionais é uma tecnologia já á muitas décadas utilizada pelo profissionais da tecnologia, possuindo uma vantagem muito forte na sua utilização para dados tabulares, onde já sabemos previamente o formato e a sua estrutura. Como dados de usuário e informações sobre o histórico de pesquisas realizadas por esses vão possuir uma estrutura constante já definidas na lógica do negócio, é uma vantagem utilizar um banco relacional. No projeto vamos utilizar o Postgres, desenvolvido como projeto de código aberto, possui várias vantagens como permitir: consultas complexas, integridade transacional, chaves estrangeiras e a possibilidade de vários módulos adicionais. 

### 3.1.5 Banco de dados: MongoDB

Para a manutenção dos dados de valor do negócio, ou seja, as informações pesquisadas e colhidas pelos nossos crawlers de processamento de e-commerces, será utilizado um banco NoSQL orientado a documentos, o MongoDB. A tecnologia NoSQL fornece um mecanismo para armazenamento e recuperação de dados que são modelados de formas diferentes das relações tabulares usadas nos bancos de dados relacionais, permitindo, no caso de bancos orientados a documentos, uma estrutura mais livre no armazemento das informações, onde cada documento pode conter atributos diferentes. Para a lógica de negócio desenvolvida nesse projeto, existe uma vantagem na utilização desse tipo de banco, pois os dados colhidos pelos crawlers podem ser diferentes para cada pesquisa já que a estrutura e informações disponibilizadas nos sites utiilizados para raspagem são diversas. A utilização do MongoDB é devido ao fato de ser o banco de dados orientados a documentos mais utilizado hoje no mercado, código aberto e multiplataforma, além de permitir com que as aplicações modelem informações de modo muito mais natural, pois os dados podem ser aninhados em hierarquias complexas e continuar a ser indexáveis e fáceis de buscar. 

### 3.1.6 Cache: Redis

No sistema, o usuário pode realizar pesquisas diversas para colher muitas informações sobre produtos através dos nossos crawlers de processamento. Existe um certo delay de inicialização, raspagem, coleta, tratamento e disponibilidade dos dados para o usuário, consequentemente, existe a possibilidade de gerar um certo tipo de "estresse" para pesquisas consecutivas feitas pelo cliente. Portanto, para auxiliar e mitigar o tempo total de respostas, propomos a implementação de caches, que podem armazenar informações já pesquisadas e disponibilizá-las mais rapidamente. A tecnologia utilizada será o Redis, possuindo armazenamento de estrutura de dados em memória, usado como um banco de dados em memória distribuído de chave-valor.      

### 3.1.7 Lambda + SageMaker: IA/ML

No sistema, utilizamos dois serviços da AWS para executar alguns trabalhos de processamento de dados e machine learning. Com o lambda, um serviço gerenciado pela AWS que permite rodar pequenos trechos de códigos como se fosse aplicações independentes, realizamos o processamento e tratamento dos dados retornados dos crawlers e retornamos para API para salvar no banco de dados e retornar para o usuário. No Sagemaker podemos criar cenários de Machine Learning, testando modelos com base nos históricos e dados colhidos das pesquisas realizadas pelos ususários do sistema.

## 3.2 Visão Lógica da arquitetura da aplicação

<p align="center">
  <img src="https://user-images.githubusercontent.com/41268748/183515157-9aa94897-9caf-4a79-805e-a58c25d9b43d.png" alt="Sublime's custom image"/>
</p>

## 3.3 Visão Lógica da arquitetura de como os dados serão utilizados

<p align="center">
  <img src="https://github.com/gabrielsrd/d5-grupo7/blob/main/assets/data.jpg?raw=true" alt="Sublime's custom image"/>
</p>

# 4. Protótipo 

https://www.figma.com/proto/dFQbK5AIRk7qOn1GfuRv7u/Crawler-Strategy---CTEDS?node-id=24%3A67&scaling=min-zoom&page-id=0%3A1
