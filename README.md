 

# Análise de Evasão de Clientes (Churn) - TelecomX_BR

Este projeto realiza uma análise completa de evasão de clientes (churn) em um dataset de telecomunicações (`TelecomX_Data.json`). O objetivo é limpar os dados, criar uma coluna de contas diárias, realizar análises exploratórias, investigar a distribuição de churn, explorar correlações, e fornecer insights para reduzir a evasão. O projeto está estruturado em Jupyter Notebooks, que podem ser executados no **Google Colab** ou localmente.

## Estrutura do Projeto

O projeto é composto pelos seguintes notebooks, cada um correspondendo a uma etapa da análise:

1. **data_quality_analysis.ipynb**: Verifica a qualidade dos dados (valores ausentes, duplicatas, erros de formatação, inconsistências).
2. **data_cleaning.ipynb**: Aplica correções aos dados (imputação, remoção de duplicatas, padronização).
3. **add_contas_diarias.ipynb**: Adiciona a coluna `Contas_Diarias` (faturamento mensal ÷ 30).
4. **descriptive_analysis.ipynb**: Realiza análise descritiva (média, mediana, desvio padrão, visualizações).
5. **churn_distribution_analysis.ipynb**: Analisa a distribuição de churn (gráficos de barras e pizza).
6. **numeric_vars_churn_analysis.ipynb**: Explora a distribuição de variáveis numéricas por churn.
7. **correlation_churn_analysis.ipynb**: Investiga correlações entre variáveis e churn.
8. **churn_analysis_report.ipynb**: Relatório final com introdução, análises, conclusões, e recomendações.


## Tecnologias

As seguintes tecnologias e bibliotecas Python são utilizadas neste projeto:

- **Pandas**: Manipulação e análise de dados em estruturas como DataFrames.
  ![Pandas Logo]  src="<img alt="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ8te-Q1kTVsUz-I5Is4XWC0HPgiZpkd23xoA&s"
- **Requests**: Requisições HTTP para carregar dados de URLs.
  ![Requests Logo](images/requests_logo.png)
- **Matplotlib**: Criação de visualizações gráficas, como gráficos de barras e dispersão.
  ![Matplotlib Logo](images/matplotlib_logo.png)
- **Seaborn**: Visualizações estatísticas avançadas, como mapas de calor e gráficos de distribuição.
  ![Seaborn Logo](images/seaborn_logo.png)
- **SciPy**: Cálculos estatísticos, como medidas de assimetria (skewness).
  ![SciPy Logo](images/scipy_logo.png)
- **Openpyxl**: Exportação de dados para arquivos Excel.
  ![Openpyxl Logo](images/openpyxl_logo.png)

## Pré-requisitos

### Dependências
As seguintes bibliotecas Python são necessárias para executar os notebooks:

- `pandas`: Manipulação de dados.
- `requests`: Carregamento de dados via URL.
- `matplotlib`: Visualizações gráficas.
- `seaborn`: Visualizações estatísticas avançadas.
- `scipy`: Cálculos estatísticos (ex.: skewness).
- `openpyxl`: Exportação para Excel (opcional, usado em `export_to_csv_excel.ipynb`).

### Instalação

#### No Google Colab
Nenhuma instalação prévia é necessária, pois o Colab já inclui a maioria das bibliotecas. Para instalar dependências específicas, execute no início de cada notebook:

```bash
!pip install pandas requests matplotlib seaborn scipy openpyxl
```

#### Localmente
1. Certifique-se de ter o Python 3.7+ instalado.
2. Crie um ambiente virtual (opcional, mas recomendado):
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   ```
3. Instale as dependências:
   ```bash
   pip install pandas requests matplotlib seaborn scipy openpyxl
   ```
4. Instale o Jupyter Notebook:
   ```bash
   pip install jupyter
   ```

## Como Executar o Projeto

### No Google Colab
1. **Acesse o Google Colab**:
   - Abra `https://colab.research.google.com/`.
   - Crie um novo notebook ou faça upload dos arquivos `.ipynb`.

2. **Carregar os Notebooks**:
   - Faça upload de cada notebook (ex.: `data_quality_analysis.ipynb`, `data_cleaning.ipynb`, etc.) via `File > Upload Notebook`.

3. **Carregar os Dados**:
   - O dataset é carregado automaticamente da URL `https://raw.githubusercontent.com/ingridcristh/challenge2-data-science/refs/heads/main/TelecomX_Data.json` em cada notebook.
   - Se preferir usar um arquivo local (ex.: após limpeza), faça upload no Colab (`Files > Upload`) e ajuste o código para:
     ```python
     df = pd.read_json('/content/TelecomX_Data_With_Contas_Diarias.json')
     ```

4. **Executar os Notebooks**:
   - Execute as células sequencialmente em cada notebook (Shift+Enter).
   - Comece com `data_quality_analysis.ipynb` e siga até `churn_analysis_report.ipynb` para a análise completa.
   - Certifique-se de instalar as dependências (veja acima) na primeira célula, se necessário.

5. **Baixar Resultados**:
   - Os notebooks geram arquivos de saída (ex.: `TelecomX_Data_Analyzed.csv`, gráficos PNG como `correlation_heatmap.png`).
   - No Colab, esses arquivos são baixados automaticamente via `files.download()`.

### Localmente
1. **Clonar ou Baixar os Notebooks**:
   - Coloque todos os arquivos `.ipynb` em um diretório local.
   - (Opcional) Clone o repositório, se disponível: `git clone <URL do repositório>`.

2. **Iniciar o Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```
   - Isso abrirá uma interface no navegador.

3. **Abrir e Executar**:
   - Navegue até o diretório do projeto e abra cada notebook.
   - Execute as células sequencialmente (Ctrl+Enter ou Shift+Enter).
   - Ajuste o caminho do dataset, se necessário (ex.: `df = pd.read_json('path/to/TelecomX_Data.json')`).

4. **Acessar Resultados**:
   - Arquivos de saída (CSV, Excel, PNG) serão salvos no mesmo diretório dos notebooks.
   - Abra os arquivos CSV/Excel no Excel ou Google Sheets e os gráficos PNG em qualquer visualizador de imagens.

## Possíveis Problemas e Soluções

### 1. **Erro ao Carregar o Dataset**
   - **Problema**: A URL `https://raw.githubusercontent.com/ingridcristh/challenge2-data-science/refs/heads/main/TelecomX_Data.json` não está acessível.
   - **Solução**:
     - Verifique a conexão com a internet.
     - Baixe o arquivo manualmente e faça upload no Colab (`Files > Upload`) ou ajuste o caminho local:
       ```python
       df = pd.read_json('/content/TelecomX_Data.json')
       ```
     - Certifique-se de que a URL está correta ou use uma cópia local do dataset.

### 2. **Coluna de Churn ou Serviços Não Encontrada**
   - **Problema**: O código não encontra a coluna `churn`, `valor_mensal`, ou `num_servicos`.
   - **Solução**:
     - Verifique os nomes das colunas com `print(df.columns)`.
     - Ajuste o código manualmente, por exemplo:
       ```python
       churn_column = 'CustomerChurn'  # Substitua pelo nome correto
       monthly_column = 'MonthlyCharge'
       services_column = 'ServicesCount'
       ```
     - Consulte o dicionário de dados (`TelecomX_diccionario.md`, se disponível) para nomes corretos.

### 3. **Dependências Não Instaladas**
   - **Problema**: Erros como `ModuleNotFoundError: No module named 'seaborn'`.
   - **Solução**:
     - No Colab, execute:
       ```bash
       !pip install seaborn
       ```
     - Localmente, instale a biblioteca ausente:
       ```bash
       pip install seaborn
       ```

### 4. **Gráficos Não Aparecem no Colab**
   - **Problema**: Os gráficos não são exibidos ou não são baixados.
   - **Solução**:
     - Certifique-se de que `%matplotlib inline` está incluído no início do notebook.
     - Verifique se a célula de download está correta:
       ```python
       from google.colab import files
       files.download('correlation_heatmap.png')
       ```
     - Se executando localmente, os gráficos são salvos no diretório do notebook.

### 5. **Dados Não Limpos**
   - **Problema**: Erros devido a valores ausentes, duplicatas, ou formatos incorretos.
   - **Solução**:
     - Execute primeiro o notebook `data_quality_analysis.ipynb` e `data_cleaning.ipynb` para garantir que os dados estejam limpos.
     - Use o arquivo gerado (`TelecomX_Data_With_Contas_Diarias.json`) nos notebooks subsequentes.

### 6. **Valores de Churn Inconsistentes**
   - **Problema**: A coluna `churn` tem valores inesperados (ex.: `True`/`False` em vez de `Sim`/`Não`).
   - **Solução**:
     - Ajuste o mapeamento na célula de padronização:
       ```python
       df[churn_column] = df[churn_column].map({True: 'Sim', False: 'Não'})
       ```
     - Verifique os valores únicos com `print(df[churn_column].unique())`.

## Resultados do Projeto

- **Arquivos Gerados**:
  - `TelecomX_Data_Cleaned.json`: Dados limpos após tratamento.
  - `TelecomX_Data_With_Contas_Diarias.json`: Dados com a coluna `Contas_Diarias`.
  - `TelecomX_Data_Analyzed.csv`: Dataset final com análises.
  - Gráficos PNG: `churn_distribution_bar.png`, `churn_distribution_pie.png`, `correlation_heatmap.png`, `<coluna>_by_churn.png`, `services_by_churn_bar.png`.

- **Principais Achados**:
  - Identificados problemas de qualidade (valores ausentes, duplicatas) e corrigidos.
  - Criada a coluna `Contas_Diarias` para análise diária do faturamento.
  - Analisada a distribuição de churn, com proporções de clientes que saíram e permaneceram.
  - Exploradas variáveis numéricas (ex.: `Contas_Diarias`, `tempo_contrato`) e sua relação com churn.
  - Calculadas correlações, destacando fatores como custos elevados ou poucos serviços associados à evasão.

- **Recomendações**:
  - Oferecer descontos para clientes com altos valores em `Contas_Diarias`.
  - Criar programas de fidelidade para clientes com contratos curtos.
  - Promover serviços adicionais para aumentar a retenção.

## Como Contribuir

1. Faça um fork do repositório (se disponível).
2. Adicione novos notebooks ou análises (ex.: modelos preditivos de churn).
3. Envie um pull request com as alterações.

## Licença

Este projeto é de código aberto e está sob a licença MIT (ou ajuste conforme necessário).

## Contato

Para dúvidas ou sugestões, entre em contato com o responsável pelo projeto ou abra uma issue no repositório.
