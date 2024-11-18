**EN**

# Domestic Violence Data Analysis in Brazil

## Overview

This project addresses the critical issue of domestic violence in Brazil, utilizing data from the **Disque 180** hotline. It consists of three main components:

1. **Data Collection**: A notebook that performs web scraping to download CSV files containing data on domestic violence.
2. **Data Cleaning**: A notebook dedicated to cleaning and preprocessing the downloaded data for analysis.
3. **Dashboard**: A Power BI dashboard that visualizes the data and provides insightful narratives about the state of domestic violence in Brazil.

## Dataset

The dataset used for this analysis was extracted from the Brazilian government's Open Data repository [Open Data repository](https://dados.gov.br/dados/conjuntos-dados/central-de-atendimento-a-mulher--ligue-180). The Women's Assistance Center, known as Ligue 180, is a crucial service in combating violence against women, offering three types of support: reporting incidents, providing guidance for victims, and disseminating information about laws and campaigns.

This dataset covers the period from the **second half of 2020 to the first half of 2024**. Due to its complexity, which includes numerous records and non-standardized categorical variables, most of the processing was conducted using Python, leveraging libraries such as pandas, numpy, and geobr (to retrieve geographic coordinates of Brazilian municipalities).

## Downloading the Data

The data download process is automated using a Python script. This script retrieves CSV files from specified URLs related to the **Disque 180** hotline. You can run the `download_data.ipynb` notebook to directly download the latest datasets.

### Steps to Download:

1. Open `download_data.ipynb`.
2. Execute the cells to download the CSV files.
3. The files will be saved in the specified directory.

## Data Cleaning

The downloaded CSV files often contain inconsistencies and missing values. The data cleaning process involves the following steps:

- **Removing duplicates**: Identifying and eliminating duplicate records to ensure data integrity.
- **Handling missing data**: Addressing missing values through appropriate methods such as imputation or exclusion.
- **Normalizing column names**: Standardizing column names for consistency and ease of analysis.
- **Filtering relevant columns**: Selecting only the columns necessary for the analysis to simplify the dataset.

Run the cleaning notebook to preprocess the data and prepare it for visualization.

Additionally, in Power Query and Power BI, final adjustments were made, and all necessary measures were created. A calendar table was constructed to utilize time intelligence functions, such as `SAMEPERIODLASTYEAR`. A table containing the start and end dates of Carnival was incorporated to calculate incidents during this period, alongside a table with the population by federative unit and year. The calculated column `TaxaDenunciasPor100k` was added to determine the rate of reports per 100,000 inhabitants. The column `PeriodoDoDia` was also created, extracted from the date of the report.

Key measures created include:

- **Total Count of Reports**: `incidentCount`
- **Reports During the Pandemic**: `Incidents During COVID`
- **Reports During Carnival**: `Incidents During Carnival`
- **Reports on New Year**: `Incidents on New Year`
- **Growth Rate of Reports**: `TaxaCrescimento` (calculated based on the number of incidents from the previous year)
- **Mode Measures** for columns: `local`, `violação`, and `relação vítima suspeito`, labeled as `[Tipo Local]`, `[Tipo Violação]`, and `[Tipo VitimaSusp]`, respectively.

## Dashboard: Analysis of Domestic Violence in Brazil

The Domestic Violence Dashboard (2020-2024) reveals the tragic reality faced by thousands of women, based on data from the **Disque 180** hotline. During this period, the total number of reports showed a significant increase of **56%**, highlighting the growing severity of violence cases. The COVID-19 pandemic not only physically isolated victims but also left them vulnerable to their abusers within their homes

The dashboard was developed in Power BI to provide visual and narrative insights into domestic violence in Brazil, facilitating the analysis and interpretation of the data. The file `dashboard_powerbi_disque180.pdf` allows you to view the structure and layout of the dashboard, which includes dynamic charts, interactive maps, and key metrics. These features enable a deep understanding of the domestic violence phenomenon in the country, offering a comprehensive analysis of the patterns, trends, and impact of such violence.

### Key Insights:

- **Reporting Methods**: The majority of cases (1.53 million) were reported via phone, underscoring the importance of this channel. Victims themselves were responsible for over **1 million** reports, indicating their direct involvement in the reporting process.

- **Emergency vs. Non-emergency Reports**: While most reports were non-emergency, approximately **100,000** involved life-threatening situations, pointing to the critical nature of some incidents.

- **Geographical Disparities**: A pronounced regional disparity is evident, with states like Roraima, Amapá, and Acre exhibiting the highest rates of reports per 100,000 inhabitants, indicating a concerning prevalence of cases in the North and Central-West regions.

- **Victim Profile**: The primary victims are young adult women aged **18 to 30**, with a notable representation of mixed-race and white women. In contrast, the majority of suspects are men, predominantly adults, with many reports lacking information on the race of the aggressors.

- **Motivations for Violence**: Family and interpersonal factors emerge as the leading motivations for violence, followed by economic reasons and power disputes, illustrating the complex dynamics of abusive relationships. Physical and psychological abuse continue to be the most reported types of violations, frequently occurring in domestic settings.

- **Temporal Patterns**: The dashboard highlights spikes in reports on weekdays and during afternoon hours, suggesting a correlation with victims' availability to report incidents. Specific events, such as the pandemic and holidays, have also impacted reporting patterns, with peaks observed during Christmas, New Year, and Carnival.

This narrative dashboard not only quantifies the problem but also illustrates the persistence of a harsh reality where many women still struggle for their safety within their own homes.

## Getting Started

To replicate this project, clone the repository and ensure you have the necessary libraries installed. Run the notebooks in the specified order: first, download the data; then, clean it; and finally, analyze it using your own Power BI dashboard or another data visualization tool.

---

**PT**

# Análise de Violência Doméstica no Brasil

## Visão Geral

Este projeto aborda a crítica questão da violência doméstica no Brasil, utilizando dados da central **Disque 180**. O projeto é composto por três componentes principais:

1. **Coleta de Dados**: Um notebook Python que realiza web scraping para baixar arquivos CSV com dados sobre violência doméstica.
2. **Limpeza de Dados**: Um notebook dedicado à limpeza e pré-processamento dos dados para análise.
3. **Dashboard**: Um dashboard no Power BI para visualização dos dados e fornecimento de insights sobre a situação da violência doméstica no Brasil.

## Conjunto de Dados

O conjunto de dados utilizado para esta análise foi extraído do repositório de Dados Abertos do governo brasileiro [Repositório de Dados Abertos](https://dados.gov.br/dados/conjuntos-dados/central-de-atendimento-a-mulher--ligue-180). A Central de Atendimento à Mulher, conhecida como Ligue 180, oferece três tipos de apoio: registro de incidentes, orientação às vítimas e disseminação de informações sobre leis e campanhas.

Este conjunto de dados cobre o período de **2020 até o primeiro semestre de 2024**. Devido à complexidade e às inconsistências presentes nos dados, a maior parte do processamento foi feita utilizando Python com as bibliotecas **pandas**, **numpy** e **geobr** (para obter as coordenadas geográficas dos municípios).

## Baixando os Dados

O processo de download dos dados é automatizado com o script Python. Esse script recupera os arquivos CSV de URLs específicas relacionadas à central **Disque 180**.

### Passos para Baixar:

1. Abra o notebook `download_data.ipynb`.
2. Execute as células para baixar os arquivos CSV.
3. Os arquivos serão salvos no diretório especificado.


## Limpeza dos Dados

Os arquivos CSV baixados geralmente contêm inconsistências e valores ausentes. O notebook `dataClean.ipynb` realiza a limpeza dos dados. O processo de limpeza inclui os seguintes passos:

* **Remoção de duplicatas:** Eliminar registros duplicados para garantir a integridade dos dados.
* **Tratamento de dados ausentes:** Lidar com valores ausentes por meio de exclusãp com um ponto de corte específico para percentual de dados ausentes.
* **Normalização dos nomes das colunas:** Padronização dos nomes das colunas para maior consistência.
* **Filtragem de colunas relevantes:** Seleção apenas das colunas necessárias para análise.

## Dashboard: Análise da Violência Doméstica no Brasil

O dashboard foi desenvolvido no Power BI com o objetivo de fornecer insights visuais e narrativos sobre a violência doméstica no Brasil, facilitando a análise e a interpretação dos dados. No arquivo `dashboard_powerbi_disque180.pdf`, é possível visualizar a estrutura e o layout do dashboard, que inclui gráficos dinâmicos, mapas interativos e medidas-chave, permitindo uma compreensão aprofundada do fenômeno da violência doméstica no país.

**Alguns dos principais insights:**
* **Métodos de Denúncia:** A maioria dos casos (1,53 milhão) foi registrada por telefone, destacando a importância deste canal.
* **Denúncias Emergenciais vs. Não Emergenciais:** A maioria das denúncias não foi emergencial, mas cerca de 100.000 envolviam risco de vida.
* **Disparidades Geográficas:** Estados como Roraima e Amapá apresentaram as maiores taxas de denúncias por 100.000 habitantes.
* **Perfil das Vítimas:** A maioria das vítimas são mulheres jovens adultas, com idades entre 18 e 30 anos.
* **Motivações para a Violência:** Fatores familiares e interpessoais são as principais causas da violência, seguidos por questões econômicas e disputas de poder.

## Por onde começar
- Clone este repositório.
- Execute os notebooks na ordem:
    - Primeiro, baixe os dados.
    - Depois, faça a limpeza e o pré-processamento dos dados.
    - Por fim, use o Power BI ou outra ferramenta de visualização para analisar os dados.

## Conclusão
Este projeto fornece uma visão abrangente sobre a violência doméstica no Brasil, utilizando dados públicos e ferramentas de análise poderosas para entender os padrões e apoiar a tomada de decisão em políticas públicas.
