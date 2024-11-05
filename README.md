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

The Domestic Violence Dashboard (2020-2024) reveals the tragic reality faced by thousands of women, based on data from the **Disque 180** hotline. During this period, the total number of reports showed a significant increase of **56%**, highlighting the growing severity of violence cases. The COVID-19 pandemic not only physically isolated victims but also left them vulnerable to their abusers within their homes.

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
