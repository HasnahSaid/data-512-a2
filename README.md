# data-512-a2

## Goal
The goal of this assignment is to examine bias in English Wikipedia articles on politician, this is done through exploring the quality of the articles as well as the coverage proportion for each country.

## Data Sources
1. **[Politicians by Country from the English-language Wikipedia:](https://figshare.com/articles/dataset/Untitled_Item/5513449)** This dataset contains English Language Wikipedia articles within the category "Category:Politicians by nationality" and subcategories. This data was obtained via Wikimedia API and formatted in a CSV file named 'page_data.csv' which can be found in the raw_data directory

| Column  | Description |
| ------------- | ------------- |
| country  | sanitised country names extracted from the category name  |
| page  | unsanitised page title |
| rev_id  | containing revision ID for each article  |

2. **[World Population mid-2020 (millions):](https://www.prb.org/international/indicator/population/table/)** This dataset was obtained from the Population Reference Bureau (PBR) and contains populations in countries, sub-regions and the world as of mid-2020. The data is stored in a CSV file 'WPDS_2020_data.csv' in the raw_data directory

| Column  | Description |
| ------------- | ------------- |
| FIPS  | abbreviation of countries and sub-regions names  |
| Name  | names of countries and sub-regions  |
| Type  | type of the value in the Name column (world, sub-region, country)  |
| TimeFrame  | year when population collected  |
| Data (M)  | population in millions  |
| Population  | population  |

4.  **[ORES API:](https://www.mediawiki.org/wiki/ORES)** ORES (Objective Revision Evaluation Service) is a web service PI that provides quality rating for Wikipedia articles, these ratings are retrieved using the revision ID of the article

| Rating  | Description|
| ------------- | ------------- |
| FA  | Featured Article  |
| GA  | Good Article  |
| B  | B-class Article  |
| C  | C-class Article  |
| Start  | Start-class Article  |
| Stub  | Stub-class Article  |

## Data Processing
To answer the quesitons in section 6, the following data cleaning and transformation was done to prepare the data for analysis:
1. Removed articles that had "Template:" in the page name in the Wikipedia article page
2. Removed sub-region rows from the dataset, these were identified by being in uppercase
3. Craeted a mapping between countries and regions that will be used later in the analysis
4. Merged Wikipedia articles with populaiton based on the country and stored in a dataframe
5. Added article counts, ratings, and GA or FA rating counts for each country and region to the dataframe in step 4

## Writeup: Reflections and Implications and Results
Please refer to the Jupyter Notebook 'hcds-a2-bias'

## License
This repository is licensed under [MIT License](https://opensource.org/licenses/MIT)
