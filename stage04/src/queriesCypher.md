## Queries em Cypher

## 1 - Juntar os países por continentes

~~~cypher

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lukeoluk/BD-Trabalho-final/main/stage04/data/country-and-continent-codes-list-csv_csv.csv' AS line
CREATE(:CountryAndContinent {country_name: line.Country_Name, continent_name: line.Continent_Name, continent_code: line.Continent_Code, country_name: line.Country_Name, country_code_2_letters: line.Two_Letter_Country_Code, country_code_3_letters: line.Three_Letter_Country_Codeline, country_number: line.Country_Number})

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lukeoluk/BD-Trabalho-final/main/stage03/notebook/owid-country-data.csv' AS line CREATE(:Country {iso_code: line.iso_code, continente: line.continent, name: line.location, idh: line.human_development_index, pib_per_capita: line.gdp_per_capita})

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lukeoluk/BD-Trabalho-final/main/stage03/notebook/owid-covid-data.csv' AS line CREATE(:CasosCovid{iso_code: line.iso_code, data: line.date, casos_total: line.total_cases, novos_casos: line.new_cases, mortes_total: line.total_deaths, novas_mortes: line.new_tests, total_testes: line.total_tests})

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lukeoluk/BD-Trabalho-final/main/stage04/data/GEODATASOURCE-COUNTRY-BORDERS.csv' AS line
CREATE(:CountryBorder {country_code: line.country_code,country_name: line.country_name, country_border_code: line.country_border_code,country_border_name: line.country_border_name})

CREATE INDEX ON :Country(iso_code)

CREATE INDEX ON :CasosCovid(iso_code)

-------------------------------------------------------------------------------- Carregamento dos Dados ---------------------------------------------------------

MATCH (c1: CountryAndContinent )
MATCH (c2: CountryAndContinent )
WHERE c1.continent_code = c2.continent_code AND c1.country_name <> c2.country_name
MERGE (c1)-[:MesmoContinente]->(c2)

MATCH (c1)-[:MesmoContinente]->(c2)
RETURN c1, c2
LIMIT 20


~~~


## 2 - Junta países por IDH

~~~cypher

// Juntar os países por IDH baixo

MATCH(c1: Country)
MATCH(c2: Country)
WHERE c1.name <> c2.name AND toFloat(c1.idh) < 0.5 AND toFloat(c2.idh) < 0.5
MERGE (c1)-[:IdhBaixo]->(c2) 

MATCH (c1:Country)-[:IdhBaixo]->(c2:Country) 
RETURN c1, c2
LIMIT 10



// Juntar os países por IDH medio

MATCH(c1: Country)
MATCH(c2: Country)
WHERE c1.name <> c2.name AND toFloat(c1.idh) > 0.5 AND toFloat(c1.idh) < 0.799 AND toFloat(c2.idh) > 0.5 AND toFloat(c2.idh) < 0.799
MERGE (c1)-[:IdhMedio]->(c2) 

MATCH (c1:Country)-[:IdhMedio]->(c2:Country) 
RETURN c1, c2
LIMIT 10


// Juntar os países por IDH alto

MATCH(c1: Country)
MATCH(c2: Country)
WHERE c1.name <> c2.name AND toFloat(c1.idh) > 0.799 AND toFloat(c2.idh) > 0.799
MERGE (c1)-[:IdhAlto]->(c2) 

MATCH (c1:Country)-[:IdhAlto]->(c2:Country) 
RETURN c1, c2
LIMIT 10

~~~

## 3 - Retorna casos e mortes de covid-19 em países de acordo com o IDH

~~~cypher

// Mostra os casos de covid-19 de acordo com o IDH do país


// retornar casos covid e mortes - IDH baixo 

MATCH (c:Country)-[:casosCovid]->(d:CasosCovid)  // Mostra arestas entre paises e seus casos de Covid
WHERE toFloat(c.idh) < 0.5
RETURN c, d
LIMIT 30

// retornar casos covid e mortes - IDH medio

MATCH (c:Country)-[:casosCovid]->(d:CasosCovid)  // Mostra arestas entre paises e seus casos de Covid
WHERE toFloat(c.idh) > 0.5 AND toFloat(c.idh) < 0.799
RETURN c, d
LIMIT 30

// retornar casos covid e mortes - IDH alto

MATCH (c:Country)-[:casosCovid]->(d:CasosCovid)  // Mostra arestas entre paises e seus casos de Covid
WHERE toFloat(c.idh) >  0.799
RETURN c, d
LIMIT 30

~~~


## 4 - Liga dados de covid-19 dos países ao seus continentes

~~~cypher
  
MATCH(c1: CountryAndContinent)  // Cria nós de continentes
MERGE (:Continents {continent_name: c1.continent_name, continent_code: c1.continent_code})

MATCH (c:Country)-[:casosCovid]->(d: CasosCovid)  // Liga os dados da covid-19 de cada país ao seu continente
MATCH(con: Continents)
WHERE c.continente = con.continent_name
MERGE (d)-[:Covid19]->(con)


MATCH (d:CasosCovid)-[:Covid19]->(con:Continents)
RETURN d,con
LIMIT 20

~~~

## 5 - Mostra o número de mortes e casos de um continente específico

~~~cypher

MATCH (d:CasosCovid)-[:Covid19]->(con:Continents)         // Retorna número de mortes de um continente especificado.
WHERE con.continent_name = 'South America'                
RETURN SUM(toFloat(d.mortes_total))


MATCH (d:CasosCovid)-[:Covid19]->(con:Continents)         // Retorna número de casos de um continente especificado.
WHERE con.continent_name = 'South America'                
RETURN SUM(toFloat(d.casos_total))


~~~

## 6 - Cria vértices para os continentes, e para cada continente é criado duas arestas com o total de mortes e de casos.

~~~cypher
LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lukeoluk/BD-Trabalho-final/main/stage04/data/casos-mortes-Continentes.csv' AS line 
CREATE(:CasosMortes {Continente: line.Continente, Codigo: line.Codigo, Casos: line.Casos, Mortes: line.Mortes})

MATCH(c:CasosMortes)
CREATE (:Morte{qtdMortes: c.Mortes})-[:Mortes]->(c)

MATCH(c:CasosMortes)
CREATE (:QntCasos {qtdCasos: c.Casos})-[:Casos]->(c)

MATCH (q:QntCasos)-[:Casos]->(c)<-[:Mortes]-(m:Morte)
RETURN q,c,m

~~~




