# CTEDS: D5 - Grupo 7

### Repositório criado para a disciplina D5 - Metodologias Ágeis do curso CTEDS

Nas issues está definido o Escopo do projeto (Proposta Projeto #1) como também os assuntos dos cards apresentados no board (Projects -> CTEDS - D5)

# 1. Visão Geral

<p align="center">
  <img src="https://github.com/gabrielsrd/d5-grupo7/blob/main/assets/logo.jpg?raw=true" alt="Sublime's custom image"/>
</p>

<p align="center">
  **Strategy Crawler**
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

# 3.1 Tecnologias

Para desenvolvimento das propostas citadas acima foi escolhida as seguintes tecnologias:
  1. Python: Desenvolvimento do Crawler utilizando Selenium como também para a análise de dados
  2. Node/Vue: Desenvolvimento da tela web
  3. Postgresql: Base de dados
  4. Lambda + SageMaker: IA/ML
  5. AWS: Disponibilização do serviço na nuvem

# 3.2 Visão Lógica da arquitetura da aplicação
<p align="center">
  <img src="https://user-images.githubusercontent.com/41268748/183515157-9aa94897-9caf-4a79-805e-a58c25d9b43d.png" alt="Sublime's custom image"/>
</p>

# 3.3 Visão Lógica da arquitetura de como os dados serão utilizados
<p align="center">
  <img src="https://github.com/gabrielsrd/d5-grupo7/blob/main/assets/data.jpg?raw=true" alt="Sublime's custom image"/>
</p>



