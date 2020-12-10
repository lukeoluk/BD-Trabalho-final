# Etapa 03 - Análises com o Primeiro Modelo Lógico

## Primeiro Modelo Conceitual

> Coloque aqui a imagem do primeiro modelo conceitual em ER ou UML, como o exemplo a seguir:
> ![ER](./Diagrams/er.png)

## Primeiros Modelos Lógicos

> Coloque aqui os primeiros modelos lógicos dos bancos de dados relacionados aos modelos conceituais. Para o modelo relacional, sugere-se o formato a seguir. Para outros modelos lógicos o formato é livre, pode ser adotado aqueles apresentados em sala.

> Exemplo de modelo lógico relacional
~~~
PESSOA(_Código_, Nome, Telefone)
ARMÁRIO(_Código_, Tamanho, Ocupante)
  Ocupante chave estrangeira -> PESSOA(Código)
~~~


## Primeiro conjunto de queries

> Queries em SQL: [Link](./notebook/queries.ipynb)

## Bases de Dados

título da base | link | breve descrição
----- | ----- | -----
`Data on COVID-19 (coronavirus) by Our World in Data` | https://github.com/owid/covid-19-data/tree/master/public/data` | Dados globais que analisam diversas características da população de um determinado país, como renda, expectativa de vida, etc.


## Arquivos de Dados
> Elencar os arquivos usados no projeto que estão disponíveis no Github do projeto.

nome do arquivo | link | breve descrição
----- | ----- | -----
`owid-covid-data.csv` | [Link](data/owid-covid-data.csv) | Dados de covid-19 em diversos países
`owid-country-data.csv` | [Link](data/processado/owid-country-data.csv) | Arquivo processado obtido a partir do owid-covid-data.csv

> Os arquivos devem ser colocados na pasta `data`, em subpasta conforme seu papel (externo, interim, processado, raw). A diferença entre externo e raw é que o raw é em formato não adaptado para uso. A pasta `raw` é opcional, pois pode ser substituída pelo link para a base original da seção anterior.
> Coloque arquivos relacionais (usualmente CSV), XML ou JSON que não estejam disponíveis online e sejam acessados pelo notebook.
