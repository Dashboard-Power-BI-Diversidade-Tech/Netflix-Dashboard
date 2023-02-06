# Análise de filmes e séries da Netflix

Projeto final desenvolvido durante o módulo de Microsoft Power BI do programa \<Div\>ersidade Tech, promovido pela Suzano em parceria com a Ada. O projeto foi desenvolvido por:

- [Bruno Rammon](https://www.linkedin.com/in/bruno-r-s-souza/)
- [Dimitri Marinho](https://www.linkedin.com/in/dimitrimarinho/)
- [Jorge Luiz Figueira](https://www.linkedin.com/in/jorgeluizfigueira/)
- [Marcus Almeida](https://www.linkedin.com/in/marcus-vinicius-de-souza-almeida/)

No projeto, foi utilizada a base de dados [“Netflix Movies and TV Shows”](https://www.kaggle.com/datasets/shivamb/netflix-shows), que reune informações utilizadas as base de dados do IMDB e TMDB para analisar séries e filmes da Netflix, no período dos anos de 1954 até 2022.

- **Dicionário dos dados:**
    
    O conjunto de dados possui dois arquivos, um contendo informações dos títulos (**titles.csv**) e outro arquivo com o elenco (**credits.csv**) para cada título. 
    
    O primeiro conjunto possui mais de 5mil registros de títulos da ***Netflix***, com 15 colunas contendo informações que incluem:
    
    - `id`: Identificação do título no site JustWatch.
    - `title`: O nome do título.
    - `show_type`: Classifica em série (TV show) ou filme (movie).
    - `description`: Descrição breve.
    - `release_year`: Ano de lançamento.
    - `age_certification`: Classificação etária.
    - `runtime`: Tempo de duração do episódio, no caso de uma série, ou tempo do filme.
    - `genres`: Lista de gêneros.
    - `production_countries`: Uma lista de países que produziu os títulos.
    - `seasons`: Número de temporadas, se for uma série.
    - `imdb_id`: Identificação (id) do título no *Internet Movie Database* (IMDB).
    - `imdb_score`: Pontuação no IMDB.
    - `imdb_votes`: Votos no IMDB.
    - `tmdb_popularity`: Popularidade no *The Movie Database* (TMDB).
    - `tmdb_score`: Pontuação no TMDB.
    
    E o segundo conjunto de dados, possui mais de **77mil** créditos para **atores, atrizes, diretores e diretoras** em títulos da Netflix, com 5 colunas contendo informações que incluem:
    
    - `person_ID`: Identificação da pessoa no site JustWatch.
    - `id`: Identificação do título no site JustWatch.
    - `name`: Nome da pessoa.
    - `character_name`: Nome do(a) personagem interpretado(a).
    - `role`: Define o cargo, entre pessoa que atua (ACTOR) ou pessoa que dirige o título (DIRECTOR).
    

- **Modelagem dimensional:**
    
    ![](https://i.imgur.com/og1q3uq.png)
    

- **Overview**:
    
    ![](https://i.imgur.com/Ci8ssAp.png)
    

---

## Discussões:

- A duração dos filmes tem diminuído ao longo do tempo?
- Qual a relação tempo de duração e os gêneros?
- Existe alguma relação entre os atores e as notas no IMBD?
- Qual o rank de filmes mais bem avaliados por gênero?
- Qual a relação do gênero dos títulos com o tempo de duração?
- Como é a distribuição dos filmes e séries por país?

---

## **A duração dos filmes tem diminuído ao longo do tempo?**

![Captura de tela colorida do ambiente do Microsoft Power BI com um gráfico de linha mostra uma queda no número que diz respeito a duração média do tempo de filmes e séries ao longo dos anos.](https://i.imgur.com/7o81H2U.png)

Para responder a essa pergunta, foi feito um filtro que avaliava os filmes a partir do ano 2000, e até o ano de 2022, onde já considerávamos os anos onde tivemos pelo menos 200 registros entre séries e filmes para avaliar. E conseguimos observar alguns pontos interessantes:

- O instante onde o valor da duração média foi **máxima** nesse período ocorre no ano de **2001**, com a marca de 124.71 minutos de duração.
- O instante onde o valor da duração média foi **mínima** ocorre no ano de **2020**, com a marca de **91.74 minutos.**
- O tempo de duração **média** no período de 2000 a 2020 é de **125 minutos.**
- A equação para a reta de tendência encontrada utilizando o Python é $y(x) = -1.35x + 2830.61$.

- **Outros gráficos interessantes:**
    
    
    **Tempo de duração dos filmes entre 2000-2022**
    
    ![](https://i.imgur.com/KfnoDZg.png)
    
    **Tempo médio de duração dos filmes em cada ano**
    
    ![](https://i.imgur.com/ZWCgxxl.png)
    

---

## **Qual a relação tempo de duração e os gêneros?**

![](https://i.imgur.com/J9xokUr.png)

Considerando ambos filmes e séries, temos as seguintes características:

- Filmes de *romance, filmes ocidentais (western / faroeste), europeus, ação* e *drama*, compõem o top 5 de maior duração, onde foi avaliada a mediana de metade dos filmes de cada gênero.
- O tempo médio de duração é 76.89 minutos
- E a obra com maior duração tem 240 minutos, o equivalente a 4 horas de duração.

---

## **Existe alguma relação entre os atores e as notas no IMBD?**

![](https://i.imgur.com/FHJNe5Q.png)

---

## **Qual o rank de filmes mais bem avaliados por gênero?**

![](https://i.imgur.com/jbVgCfT.png)

E no IMDB especificamente, também podemos usar o seguinte visual para conferir cada título divido por gênero e também o tipo:

![](https://i.imgur.com/Olq1Tbj.png)

---

## **Distribuição de filmes por localização**

![](https://i.imgur.com/qRk6A9M.png)
