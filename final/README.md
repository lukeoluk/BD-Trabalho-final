# Modelo para Apresentação da Etapa Final

Estrutura de pastas:

~~~
├── README.md  <- arquivo apresentando a proposta
│
├── data
│   ├── external       <- dados de terceiros em formato usado para entrada na transformação
│   ├── interim        <- dados intermediários, e.g., resultado de transformação
│   ├── processed      <- dados finais usados para a modelagem
│   └── raw            <- dados originais sem modificações
│
├── notebooks          <- Jupyter notebooks ou equivalentes
│
├── slides             <- arquivo de slides em formato PDF
│
├── src                <- fonte em linguagem de programação ou sistema (e.g., Cytoscape)
│   └── README.md      <- instruções básicas de instalação/execução
│
└── assets             <- mídias usadas no projeto
~~~

# Etapa Final

## Projeto `Covid-19 - Análise socioeconômica na pandemia`

## Equipe `Grupo Genérico de BD`
* `Lucas Fernandes André        RA: 182495`
* `Gabriel Massuyoshi Sato      RA: 172278`
* `Caio Lucas Silveira De Sousa RA: 165461`

## Slides da Apresentação da Etapa Final

> Apresentação: [Link](./slides/apresentação.pdf)

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

> Coloque aqui a imagem do modelo conceitual final em ER ou UML, como o exemplo a seguir:
> ![ER Taxi](images/er-taxi.png)

## Modelos Lógicos Finais

> Coloque aqui os modelos lógicos dos bancos de dados relacionados aos modelos conceituais. Todos os modelos lógicos da versão final devem estar presentes, mesmo que tenham sido apresentados em etapas anteriores. Para o modelo relacional, sugere-se o formato a seguir. Para outros modelos lógicos o formato é livre, pode ser adotado aqueles apresentados em sala.

> Exemplo de modelo lógico relacional
~~~
PESSOA(_Código_, Nome, Telefone)
ARMÁRIO(_Código_, Tamanho, Ocupante)
  Ocupante chave estrangeira -> PESSOA(Código)
~~~

## Programa de extração e conversão de dados atualizado

> Coloque um link para o arquivo do notebook que executa a extração e conversão de dados. Ele estará dentro da pasta `notebook`. Se por alguma razão o código não for executável no Jupyter, coloque na pasta `src`. Se a extração e conversão envolverem queries executadas através de uma interface de um SGBD não executável no Jupyter, como o Cypher, apresente na forma de markdown.

## Conjunto de queries para todos os modelos

> Acrescente um link para o(s) arquivo(s) do(s) notebook(s) que executa(m) as queries para cada um dos modelos lógicos. Eles estarão dentro da pasta `notebook`. Se por alguma razão o código não for executável no Jupyter, coloque na pasta `src`. Se as queries forem executadas através de uma interface de um SGBD não executável no Jupyter, como o Cypher, apresente na forma de markdown.
> Apresente todas as suas queries em versão final, mesmo que tenham aparecido em etapas anteriores.

## Bases de Dados

título da base | link | breve descrição
----- | ----- | -----
`Data on COVID-19 (coronavirus) by Our World in Data` | https://github.com/owid/covid-19-data/tree/master/public/data` |  `Dados globais que analisam diversas características da população de um determinado país, como renda, expectativa de vida, etc.`
`Country Borders` | https://github.com/geodatasource/country-borders | `Mostra as fronteiras dos países`
`Country and Continent Codes List` | https://datahub.io/JohnSnowLabs/country-and-continent-codes-list | `Mostra países e qual continente eles pertencem`
`againstcovid19 - Taiwan - Cases` | https://againstcovid19.com/taiwan/cases | `Relação de casos de Taiwan baseado em relações de pessoas, em que cada nó é uma pessoa e cada aresta é o tipo de relação entre as pessoas`
`Dados socioeconômicos de Taiwan` | https://eng.stat.gov.tw/mp.asp?mp=5 | `Database relacionado aos dados socioeconômicos de Taiwan.`


## Arquivos de Dados

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
