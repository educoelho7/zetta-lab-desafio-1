# zetta-lab-desafio-1
Desafio 1 da trilha de Ciência e Governança de Dados do Zetta Lab 2025

# Análise dos Fatores que Impactam o IDHM Municipal no Brasil
## Objetivo

O objetivo deste projeto é identificar e visualizar os fatores socioeconômicos que mais impactam o Índice de Desenvolvimento Humano Municipal (IDHM) no Brasil.
Para isso, foram utilizadas bases de dados públicas de saúde, educação, meio ambiente, segurança e economia, integradas em uma análise exploratória e preditiva.

## Estrutura da Análise
### 1. Preparação e Tratamento dos Dados

Unificação de diferentes bases de dados (saúde, educação, economia, meio ambiente, segurança) em um único DataFrame principal (main_df).
Normalização e padronização dos nomes das colunas).
Conversão e limpeza de dados numéricos e categóricos.
Remoção de valores nulos e inconsistentes.
Criação de variáveis derivadas, como taxas per capita (ex: taxa de homicídios por 100 mil habitantes).

### 2. Visualização Geográfica (Mapas)

- Foi criada uma visualização geográfica com dados municipais, usando GeoPandas e Matplotlib.
- O mapa exibe o IDHM de 2010 para cada município.
- Cores seguem a escala da ONU (UNDP).
- Municípios sem dados aparecem em cinza (#cccccc);

### 3. Identificação dos Fatores Mais Relevantes (Feature Importance)

Para compreender quais variáveis mais influenciam o IDHM, foi treinado um modelo de Random Forest Regressor:

Variável alvo: idhm 2010
Variáveis explicativas: educação, saúde, meio ambiente, economia, segurança, etc.
O modelo foi ajustado e gerou um ranking de importância das variáveis (feature_importances_).
O resultado foi organizado em um DataFrame com as colunas metrica e importancia.
Esse ranking permite identificar quais indicadores têm maior peso no desenvolvimento humano municipal.

### 4. Agrupamento de Municípios (K-Means Clustering)

Foi aplicado o algoritmo K-Means (k=5) para agrupar os municípios com perfis socioeconômicos semelhantes.
As variáveis numéricas foram padronizadas antes da clusterização;
Cada município recebeu um rótulo de cluster (cluster ∈ {0, 1, 2, 3, 4});
Os clusters foram visualizados em um mapa com uma escala de tons de roxo.

### 5. Estatísticas Descritivas por Cluster

Após a clusterização, foi feita uma análise de médias e desvios-padrão das variáveis numéricas em cada grupo.
Isso permite entender:
- Quais características diferenciam os clusters;
- Quais indicadores são mais altos ou baixos em cada grupo;
- Como se distribuem as desigualdades regionais no país.

## Principais Tecnologias Utilizadas

Pandas / GeoPandas
Matplotlib
Scikit-learn

## Resultados
Identificação dos fatores que mais influenciam o IDHM.
Classificação dos municípios brasileiros em grupos de similaridade socioeconômica.
Visualização geográfica interativa e estática dos resultados.
Base sólida para subsidiar políticas públicas regionais baseadas em dados.
