# 📊🐍 Resumo de Bibliotecas e Comandos Python para Dados usados durante a Imersão

O **Python** é uma das linguagens de programação mais utilizadas na análise de dados. Isso se deve ao fato de ser relativamente fácil de aprender, 
se integrar facilmente a outras ferramentas, como **Excel** e **SQL**, além de ser versátil e contar com bibliotecas específicas para análise e visualização de dados.

Durante a imersão, o Python foi utilizado em conjunto com o **Google Colab**, uma plataforma online baseada em **Jupyter Notebook**, para a execução dos exercícios. 
Este documento apresenta um resumo das bibliotecas utilizadas e dos principais comandos estudados.

## 🐼 Biblioteca Pandas 
O Pandas é a biblioteca principal para manipulação de dados em Python. É essencial para análise de dados estruturados e preparação de datasets para gráficos ou modelos.  
Ela permite:
- Criar e trabalhar com DataFrames (tabelas de dados, como planilhas).
- Ler arquivos em formatos como CSV, Excel e outros.
- Explorar, filtrar, agrupar e resumir dados de forma rápida.
- Tratar dados faltantes ou duplicados, renomear colunas e calcular estatísticas.

🔗 [Clique aqui para acessar a documentação oficial da biblioteca](https://pandas.pydata.org/docs/)

### 📌 Alguns comandos mais utilizados:
| Comando | Descrição |
|---------|-----------|
| `import pandas as pd` | Importa a biblioteca. Por convenção, a biblioteca **pandas** é apelidada de `pd`. |
| `df = pd.read_csv('link_do_arquivo')` | Lê um arquivo em formato **CSV**, onde os dados estão armazenados. Por convenção, esse arquivo é armazenado em uma variável chamada `df` (*dataframe*). |
| `df.head()` | Mostra as **cinco primeiras linhas** do dataframe. Caso deseje visualizar mais linhas, acrescentar a quantidade de linhas desejadas dentro dos parênteses. |
| `df.info()` | Informa as **colunas** e os **tipos de dados** que podem ser armazenados nelas. |
| `df.describe()` | Cria uma tabela com **estatísticas descritivas** das colunas de tipo numérico. |
| `df.describe(include='object')` | Cria uma tabela com as frequências das colunas de tipos **categóricos**. Onde:<br> - **count**: contagem dos valores existentes para aquela coluna;<br> - **unique**: quantos são os valores únicos;<br> - **top**: qual a informação mais frequente;<br> - **freq**: quantas vezes o valor informado em *top* está se repetindo. |
| `df.shape` | Mostra as **dimensões do dataframe**, onde o primeiro valor se refere à quantidade de **linhas**, e o segundo valor à quantidade de **colunas**. |
| `df.columns` | Informa o **nome das colunas**. |
| `df.rename(columns=variável_dicionário_de_novos_nomes, inplace=True)` | Altera os **nomes das colunas** com os valores que foram atribuídos às **chaves de um dicionário** e armazenados na variável passada como parâmetro. <br>🔎 O parâmetro `inplace=True` aplica essas alterações no arquivo, e deve ser utilizado com cuidado. |
| `df['coluna_categórica'].value_counts()` | Cria uma **tabela de frequência** para os dados categóricos armazenados em `coluna_categórica`. |
| `df.isnull()` | Verifica **campos nulos** no dataframe. Retorna `True` para campos que estão nulos. |
| `df.isnull().sum()` | Informa **quantos campos nulos** existem em cada coluna. |
| `df['coluna_com_nulos'].unique()` | Mostra quais são os **valores únicos** da `coluna_com_nulos`, onde `NaN` (*Not a Number*) se refere aos dados nulos. |
| `df[df.isnull().any(axis=1)]` | Informa **onde estão os dados nulos** do dataframe. |
| `df['coluna_desejada'].value_counts().plot(kind='bar', title='Distribuição da coluna desejada')` | Cria um **gráfico de barras** com os dados da `coluna_desejada` e atribui o título *“Distribuição da coluna desejada”*. |

---

## 🌊 Biblioteca Seaborn
O Seaborn é uma biblioteca de visualização baseada no Matplotlib, mas com gráficos mais bonitos e fáceis de criar. É indicada para explorar padrões e distribuições nos dados, e para apresentações visuais de estatísticas.  
Ela permite:
- Criar gráficos estatísticos, como barras, histogramas e boxplots.
- Trabalhar facilmente com dados categóricos e numéricos.
- Personalizar cores e estilos de forma intuitiva.

🔗 [Clique aqui para acessar a documentação oficial da biblioteca](https://seaborn.pydata.org/)

### 📌 Alguns comandos mais utilizados:
| Comando | Descrição |
|---------|-----------|
| `import seaborn as sns` | Importa a biblioteca. Por convenção, a biblioteca **seaborn** é apelidada de `sns`. |
| `sns.barplot(data=df, x='coluna_eixo_x', y='coluna_eixo_y')` | Cria um gráfico de barras utilizando a base de dados informada em `data`, com eixos `x` e `y` especificados pelas colunas informadas. |
| `sns.histplot(df['coluna_desejada'], bins=50, kde=True)` | Cria um histograma da coluna desejada. <br> **Onde:** <br> • `bins`: define a quantidade de divisões (intervalos) em que os dados serão agrupados. Cada barra do histograma representa quantos valores caíram dentro de um intervalo. <br> • `kde` (*Kernel Density Estimation*): quando definido como `True`, adiciona uma linha suave ao gráfico, que representa a estimativa da distribuição dos dados. Essa linha ajuda a visualizar a tendência geral dos valores, sem depender apenas da altura das barras. |
| `sns.boxplot(x=df['coluna_desejada'])` | Cria o gráfico de **boxplot** para a coluna desejada, permitindo visualizar mediana, quartis e possíveis outliers. |

---

## 📊 Biblioteca Matplotlib (módulo Pyplot)
O Matplotlib é a biblioteca mais flexível e clássica de gráficos em Python. É ótima para visualizações personalizadas, quando você precisa de controle total sobre cada detalhe do gráfico.  
Com o módulo Pyplot, é possível:
- Criar gráficos de linhas, barras, dispersão, pizza, entre outros.
- Definir tamanho, títulos, rótulos e legendas dos gráficos.
- Combinar vários elementos gráficos em uma mesma figura.

🔗 [Clique aqui para acessar a documentação oficial da biblioteca](https://matplotlib.org/stable/index.html)


### 📌 Alguns comandos mais utilizados:
| Comando | Descrição |
|---------|-----------|
| `import matplotlib.pyplot as plt` | Importa o módulo **pyplot** da biblioteca **Matplotlib**. Por convenção, é apelidado de `plt`. |
| `plt.figure(figsize=(8,5))` | Define o tamanho da figura que contém o gráfico. Neste caso, largura = 8 e altura = 5. |
| `plt.title('Título de exemplo')` | Insere um **título** para o gráfico de acordo com o informado. |
| `plt.xlabel('eixo x')` | Insere um **título para o eixo X** de acordo com o informado. |
| `plt.ylabel('eixo y')` | Insere um **título para o eixo Y** de acordo com o informado. |

---

## 📈 Biblioteca Plotly (Plotly Express)
O Plotly Express permite criar gráficos interativos e dinâmicos de forma simples. É ideal para apresentações e dashboards, quando você quer que o público explore os dados de forma visual e interativa.  
Ele permite:
- Criar gráficos de pizza, rosca, barras, linhas, mapas, entre outros.
- Tornar os gráficos interativos, permitindo passar o mouse sobre os dados e explorar informações.
- Customizar cores, títulos e rótulos.

🔗 [Clique aqui para acessar a documentação oficial da biblioteca](https://plotly.com/python/)

### 📌 Alguns comandos mais utilizados:
| Comando | Descrição |
|---------|-----------|
| `import plotly.express as px` | Importa a biblioteca **Plotly Express**. Por convenção, é apelidada de `px`. |
| `fig = px.pie(variável_frequência_categórica, names='coluna_desejada', values='valor_desejado', title='Título de exemplo')` | Cria um **gráfico de pizza interativo** e armazena na variável `fig`. É passado como parâmetro uma variável que armazena as frequências de um dado categórico, além da coluna e dos valores desejados. O gráfico receberá o título informado. |
| `fig = px.pie(variável_frequência_categórica, names='coluna_desejada', values='valor_desejado', hole=0.5, title='Título de exemplo')` | Transforma o gráfico anterior em um **gráfico de rosca**. |
| `fig.show()` | Exibe o **gráfico interativo** na tela. |
| `fig.update_traces(textinfo='percent+label')` | Atualiza o gráfico para mostrar o **nome do rótulo** e seu **percentual** junto ao gráfico. |
