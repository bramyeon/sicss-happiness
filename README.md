# World Happiness Score: Analysis, Interpretation, and Modeling
__SICSS-Korea 2024 Team Project__  
Bryan Nathanael Wijaya<sup>1,2</sup>, Inkoo Kang<sup>3</sup>, Ju Hee Jeung<sup>4,5,6</sup>, Kyungmin Lee<sup>7</sup>, and Yumi Park<sup>4</sup> *(in ABC order)*  

<sup>1</sup> School of Computing, Korea Advanced Institute of Science and Technology (KAIST)  
<sup>2</sup> Center for Mathematical and Computational Sciences, Institute for Basic Science (IBS)  
<sup>3</sup> Urban Systems, New York University (NYU)  
<sup>4</sup> Korea Development Institute (KDI) School of Public Policy and Management  
<sup>5</sup> UNESCO International Centre for Water Security and Sustainable Management (i-WSSM)  
<sup>6</sup> Korea Water Resource Corporation (K-water)  
<sup>7</sup> Energy and Environmental Policy, University of Delaware  

## Datasets
Datasets for this project are saved in `data`, where preprocessed data is located in its `clean` subdirectory. However, as the city temperature __raw__ dataset is larger than 100MB, this repository does not include the file. Kindly download the raw dataset at [this Kaggle dataset link](https://www.kaggle.com/datasets/subhamjain/temperature-of-all-countries-19952020) and save it as `city-temperature.csv` in the `data` directory. The following is our dataset summary.

- `data/clean/world-happiness-2005-2023.csv` (1), `data/clean/world-happiness-2024.csv` (2): https://www.kaggle.com/datasets/jainaru/world-happiness-report-2024-yearly-updated/data <br>The world happiness data for 2005-2023 serves as our <b>main</b> dataset, while 2024 data is auxiliary (<b>WARNING:</b> The distribution of the happiness factors in 2024 is different from that in 2005-2023 data, so do NOT merge this to the 2005-2023 data and simply use for separate analysis or as reference only)  
- `data/clean/temperature-2005-2023.csv` (3): https://www.kaggle.com/datasets/subhamjain/temperature-of-all-countries-19952020 <br>This dataset contains the daily temperature of the main cities in each country, which we preprocessed to get the annual average, max, min, and gap (i.e., max-min) temperatures for each country for each (country, year) cases that are considered in our <b>main</b> dataset.
- `data/clean/un-gini-index-2005-2023.csv` (4): https://data.un.org/Data.aspx?d=WDI&f=Indicator_Code%3ASI.POV.GINI <br>This dataset contains the annual Gini index value for each country for each (country, year) cases that are considered in our <b>main</b> dataset.
- `data/clean/world-bank-2005-2023.csv` (5): https://databank.worldbank.org/reports.aspx?source=2&series=AG.LND.PRCP.MM&country=# <br>This is an auxiliary dataset taken from the World Bank Dataset to help with our analysis or happiness model training. The elements considered are hand-picked by me (Bryan), where I tried to take those that seem to have some influence on the nation's happiness. (Also since we do not want to have more features than our number of entries, since in that case, model training will likely not converge!) Do let me know if there is any other feature that you would like to additionally consider for our project.
- `data/clean/core.csv`: This is the combination of datasets (1), (3), (4), and the `co2 emissions (metric tons per capita)` column of (5). 
- `data/clean/combined.csv`: This is the combination of datasets (1), (3), (4), and (5). Please use with caution and feel free to remove columns that you think are irrelevant!
