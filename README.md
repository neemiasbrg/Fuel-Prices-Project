<img src="fuel_prices.png">

# Fuel Prices Machine learning Project

## Objetivo

Este projeto visa aplicar algoritmos de machine learning para o agrupamento de preços de combustíveis por região do Brasil, utilizando dados abertos fornecidos pelo Ministério de Minas e Energia, disponível no site oficial do Governo Federal.

## Especificação Técnica

### Dataset

O dataset utilizado neste projeto é composto por dados semanais agrupados por semestre do ano de 2021. Os dados estão disponíveis em: [Dados Abertos ANP](https://www.gov.br/anp/pt-br/centrais-de-conteudo/dados-abertos/arquivos/shpc/dsas/ca/).

**Formato:**
O dataset está em formato CSV, contendo 16 colunas (features):
- `Regiao - Sigla` (object)
- `Estado - Sigla` (object)
- `Municipio` (object)
- `Revenda` (object)
- `CNPJ da Revenda` (object)
- `Nome da Rua` (object)
- `Numero Rua` (object)
- `Complemento` (object)
- `Bairro` (object)
- `Cep` (object)
- `Produto` (object)
- `Data da Coleta` (object)
- `Valor de Venda` (object)
- `Valor de Compra` (float64)
- `Unidade de Medida` (object)
- `Bandeira` (object)

### Métodos de Pré-processamento

O dataset requer tratamento inicial, incluindo:
- Limpeza da base (renomeação de colunas, remoção de colunas não utilizadas)
- Conversão de dados para formato adequado (datas e valores monetários)

### Tarefa de Aprendizado

A tarefa de aprendizado aplicada é o agrupamento (clustering).

### Modos de Aprendizado

- **Não Supervisionado**

### Algoritmo Avaliado

- **K-médias (K-Means)**

### Métricas Utilizadas

- **Score**
- **Média do Erro Absoluto**
- **Média do Erro Quadrático**

## Pré-Processamento

1. **Importação das Bibliotecas**

  Foram importadas bibliotecas essenciais para manipulação e análise de dados (pandas, numpy), visualização (matplotlib, seaborn), e aprendizado de máquina (sklearn). Além disso, foram incluídas bibliotecas para requisições HTTP (requests) e tratamento de dados (io).  

2. **Carregamento e Limpeza dos Dados**

Os dados foram carregados a partir de arquivos CSV disponibilizados pelo site do governo, utilizando requests. Em seguida, as bases de dados foram concatenadas e limpas, removendo colunas desnecessárias e corrigindo valores incorretos.

3. **Tratamento dos Dados**

Os dados foram ajustados para garantir a consistência. Isso incluiu a conversão de tipos de dados (como datas e valores monetários), e a padronização de formatos (como substituição de vírgulas por pontos em valores numéricos).

## Análise dos Dados

1. **Visão Geral**

Foi feita uma visão geral dos dados para entender suas características, como a distribuição das vendas ao longo do tempo e por região. Foi calculado o dia da semana e o mês das coletas para uma análise temporal.

2. **Visualizações**

Foram criados gráficos para visualizar a distribuição dos preços de combustíveis por região e tipo de produto, ajudando a identificar padrões e tendências nos dados.

## Modelagem dos Dados

1. **Preparação dos Dados**

Os dados foram preparados para o modelo de clustering. Incluiu-se a codificação das variáveis categóricas e a divisão dos dados em conjuntos de treino e teste. Foi realizada a remoção de colunas não necessárias.

2. **Aplicação do Algoritmo K-Médias**

O algoritmo K-Médias (K-Means) foi aplicado para agrupar os dados em clusters. Foi utilizado o método do cotovelo para determinar o número ideal de clusters e, em seguida, o modelo foi treinado com os dados.

3. **Avaliação dos Modelos**

Os modelos de regressão (Linear, Random Forest e Gradient Boosting) foram avaliados usando métricas como erro quadrático médio (MSE) e o coeficiente de determinação (R²) para determinar a precisão das previsões.

4. **Validação Cruzada**

Foi realizada a validação cruzada para verificar a robustez dos modelos. Isso envolveu dividir os dados em múltiplos subconjuntos para avaliar a performance dos modelos em diferentes partes dos dados, garantindo que os resultados fossem confiáveis e consistentes.

## Conclusão

A análise dos dados de vendas de combustíveis de 2021 revelou padrões de consumo e distribuição, identificou outliers e aplicou o algoritmo KMeans para agrupamento. Modelos de regressão foram treinados e avaliados, com o Random Forest apresentando o melhor desempenho. A validação cruzada foi realizada para garantir a robustez dos modelos.

## Requisitos

- Python 3.8+
- Bibliotecas: pandas, numpy, matplotlib, seaborn, scikit-learn, requests

## Como Executar o Projeto

1. Clone o repositório:
    ```bash
    git clone https://github.com/seu-usuario/fuel-prices-project.git
    cd fuel-prices-project
    ```

2. Instale as dependências:
    ```bash
    pip install -r requirements.txt
    ```

3. Execute o script principal:
    ```bash
    python fuel_prices.ipynb
    ```

## Contribuições

Sinta-se à vontade para contribuir com o projeto, abrindo issues ou enviando pull requests.

## Licença

Este projeto é licenciado sob a [MIT License](LICENSE).
