# Etapa Final

## Projeto `Covid-19 - Análise socioeconômica na pandemia`

## Equipe `Grupo Genérico de BD`
* `Lucas Fernandes André        RA: 182495`
* `Gabriel Massuyoshi Sato      RA: 172278`
* `Caio Lucas Silveira De Sousa RA: 165461`

## Slides da Apresentação da Etapa Final

> Apresentação: [Link](slides/apresentacao.pdf)

## Resumo do Projeto
> Texto resumindo o projeto.

## Motivação e Contexto

> Descrição do tema do projeto, incluindo motivação e contexto gerador.

## Detalhamento do Projeto
> Apresente aqui detalhes da análise. Nesta seção ou na seção de Resultados podem aparecer destaques de código como indicado a seguir. Note que foi usada uma técnica de highlight de código, que envolve colocar o nome da linguagem na abertura de um trecho com `~~~`, tal como `~~~python`.
> Os destaques de código devem ser trechos pequenos de poucas linhas, que estejam diretamente ligados a alguma explicação. Não utilize trechos extensos de código. Se algum código funcionar online (tal como um Jupyter Notebook), aqui pode haver links. No caso do Jupyter, preferencialmente para o Binder abrindo diretamente o notebook em questão.

~~~python
df = pd.read_excel("/content/drive/My Drive/Colab Notebooks/dataset.xlsx");
sns.set(color_codes=True);
sns.distplot(df.Hemoglobin);
plt.show();
~~~

## Evolução do Projeto
> Relatório de evolução, descrevendo as evoluções na modelagem do projeto, dificuldades enfrentadas, mudanças de rumo, melhorias e lições aprendidas. Referências aos diagramas, modelos e recortes de mudanças são bem-vindos.
> Podem ser apresentados destaques na evolução dos modelos conceitual e lógico. O modelo inicial e intermediários (quando relevantes) e explicação de refinamentos, mudanças ou evolução do projeto que fundamentaram as decisões.
> Relatar o processo para se alcançar os resultados é tão importante quanto os resultados.

## Resultados e Discussão
> Apresente os resultados da forma mais rica possível, com gráficos e tabelas. Mesmo que o seu código rode online em um notebook, copie para esta parte a figura estática. A referência a código e links para execução online pode ser feita aqui ou na seção de detalhamento do projeto (o que for mais pertinente).
> A discussão dos resultados também pode ser feita aqui na medida em que os resultados são apresentados ou em seção independente. Aspectos importantes a serem discutidos: É possível tirar conclusões dos resultados? Quais? Há indicações de direções para estudo? São necessários trabalhos mais profundos?

## Conclusões
> Apresente aqui as conclusões finais do trabalho e as lições aprendidas.

## Modelo Conceitual Final
> ![ER Taxi](images/ER2.jpg)

## Modelos Lógicos Finais
> ![ER Taxi](images/modelo_logico_tabelas.png)

## Programa de extração e conversão de dados atualizado

> Coloque um link para o arquivo do notebook que executa a extração e conversão de dados. Ele estará dentro da pasta `notebook`. Se por alguma razão o código não for executável no Jupyter, coloque na pasta `src`. Se a extração e conversão envolverem queries executadas através de uma interface de um SGBD não executável no Jupyter, como o Cypher, apresente na forma de markdown.

## Conjunto de queries para todos os modelos
> Notebook com as queries utilizadas no projeto final: [Link](notebooks/queries.ipynb)

> Markdown com as queries em Cypher utilizadas no projeto: [Link](./src/queriesCypher.md)

> Notebook com as queries da Etapa 3: [Link](../stage03/notebook/queries.ipynb)

> Acrescente um link para o(s) arquivo(s) do(s) notebook(s) que executa(m) as queries para cada um dos modelos lógicos. Eles estarão dentro da pasta `notebook`. Se por alguma razão o código não for executável no Jupyter, coloque na pasta `src`. Se as queries forem executadas através de uma interface de um SGBD não executável no Jupyter, como o Cypher, apresente na forma de markdown.
> Apresente todas as suas queries em versão final, mesmo que tenham aparecido em etapas anteriores.

## Bases de Dados

título da base | link | breve descrição
----- | ----- | -----
`Data on COVID-19 (coronavirus) by Our World in Data` | https://github.com/owid/covid-19-data/tree/master/public/data |  `Dados globais que analisam diversas características da população de um determinado país, como renda, expectativa de vida, etc.`
`Country Borders` | https://github.com/geodatasource/country-borders | `Mostra as fronteiras dos países`
`Country and Continent Codes List` | https://datahub.io/JohnSnowLabs/country-and-continent-codes-list | `Mostra países e qual continente eles pertencem`
`List of continent codes` | https://datahub.io/core/continent-codes | `Continentes e seus respectivos códigos`
`againstcovid19 - Taiwan - Cases` | https://againstcovid19.com/taiwan/cases | `Relação de casos de Taiwan baseado em relações de pessoas, em que cada nó é uma pessoa e cada aresta é o tipo de relação entre as pessoas`
`Dados socioeconômicos de Taiwan` | https://eng.stat.gov.tw/mp.asp?mp=5 | `Database relacionado aos dados socioeconômicos de Taiwan.`


## Arquivos de Dados

nome do arquivo | link | breve descrição
----- | ----- | -----
`owid-covid-data.csv` | [link](data/externo/owid-covid-data.csv) | `Dados do covid-19 em diversos países`
`GEODATASOURCE-COUNTRY-BORDERS.csv` | [link](data/externo/GEODATASOURCE-COUNTRY-BORDERS.csv) | `Mostra países que fazem fronteira entre si`
`country-and-continent-codes-list-csv_csv.csv` | [link](data/externo/country-and-continent-codes-list-csv_csv.csv) | `Mostra os códigos de duas e três letras dos países e seus continentes.`
`continent-codes_csv` | [link](data/externo/continent-codes_csv.csv) | `Códigos e nomes dos continentes do mundo`
`owid-country-data.csv`| [link](data/processado/owid-country-data.csv) | `Processado:  Dados de países como população, idh, etc. retirado originalmente de owid-covid-data.csv`
`casos-mortes-Continentes.csv` | [link](data/processado/casos-mortes-Continentes.csv) | `Processado: Mostra mortes e casos dos continentes`
`idh-mortes_casos_total.csv` | [link](data/processado/idh-mortes_casos_total.csv) | `Processado: Mostra mortes e casos por faixa de IDH`
`iso_2c_cases.csv` | [link](data/processado/iso_2c_cases.csv) | `Processado: Utilizado para visualização no Cytoscape`
`page-rank-borders.csv` | [link](data/processado/page-rank-borders.csv) | `Processado: Page Rank da quantidade de fronteiras que cada país possui`
