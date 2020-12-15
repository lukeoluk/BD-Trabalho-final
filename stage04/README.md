# Etapa 04 - Análises com o Segundo Modelo Lógico

## Slides da Apresentação da Etapa

> Apresentação: [Link](./slides/apresentacao.pdf)

## Modelo Conceitual Atualizado

> Coloque aqui a imagem do modelo conceitual atualizado em ER ou UML, como o exemplo a seguir:
> ![ER](ER2.jpg)

## Modelos Lógicos Atualizados

> Coloque aqui os dois modelos lógicos dos bancos de dados relacionados aos modelos conceituais. O modelo lógico da etapa anterior pode ser copiado ou apresentado revisado. Para o modelo relacional, sugere-se o formato a seguir. Para outros modelos lógicos o formato é livre, pode ser adotado aqueles apresentados em sala.

> Exemplo de modelo lógico relacional
~~~
PESSOA(_Código_, Nome, Telefone)
ARMÁRIO(_Código_, Tamanho, Ocupante)
  Ocupante chave estrangeira -> PESSOA(Código)
~~~

## Conjunto de queries de dois modelos

> Queries em SQL: [Link](./notebook/queries.ipynb)

> Queries em Cypher: [Link](./src/queriesCypher.md)

> Queries em SQL da Etapa 3: [Link](../stage3/notebook/queries.ipynb)


## Bases de Dados

título da base | link | breve descrição
----- | ----- | -----
`Data on COVID-19 (coronavirus) by Our World in Data` | https://github.com/owid/covid-19-data/tree/master/public/data` |  `Dados globais que analisam diversas características da população de um determinado país, como renda, expectativa de vida, etc.`
`Country Borders` | https://github.com/geodatasource/country-borders | `Mostra as fronteiras dos países`
`Country and Continent Codes List` | https://datahub.io/JohnSnowLabs/country-and-continent-codes-list | `Mostra países e qual continente eles pertencem`


## Arquivos de Dados
> Elencar os arquivos usados no projeto que estão disponíveis no Github do projeto (manter os da Etapa 3 e acrescentar os da Etapa 4).

nome do arquivo | link | breve descrição
----- | ----- | -----
`owid-covid-data.csv` | [Link](./data/owid-covid-data.csv) | `Dados do covid-19 em diversos países`
`owid-country-data.csv`| [Link](./data/owid-country-data.csv) | `Dados de países como população, idh, etc.`
`GEODATASOURCE-COUNTRY-BORDERS.csv` | [Link](./data/GEODATASOURCE-COUNTRY-BORDERS.csv) | `Mostra países que fazem fronteira`
`country-and-continent-codes-list-csv_csv.csv` | [Link](./data/country-and-continent-codes-list-csv_csv.csv) | `Mostra os códigos de duas e três letras dos países e seus continentes.`
`casos-mortes-Continentes.csv` | [Link](./data/processado/casos-mortes-Continentes.csv) | `Processado: Mostra mortes e casos dos continentes`
`idh-mortes_casos_total.csv` | [Link](./data/processado/idh-mortes_casos_total.csv) | `Processado: Mostra mortes e casos por faixa de IDH`


> Os arquivos devem ser colocados na pasta `data`, em subpasta conforme seu papel (externo, interim, processado, raw). A diferença entre externo e raw é que o raw é em formato não adaptado para uso. A pasta `raw` é opcional, pois pode ser substituída pelo link para a base original da seção anterior.
> Coloque arquivos relacionais (usualmente CSV), XML ou JSON que não estejam disponíveis online e sejam acessados pelo notebook.
