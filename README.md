
# Project 1 LEDE: China visits dataset analysis

This project explores patterns in the international visits of Chinese leaders (presidents and premiers) from 1998 to 2020, using a dataset by Yu Wang and Randall W. Stone.

## Short description of what you aimed to accomplish

The dataset "China Visits: a dataset of Chinese leaders’ foreign visits" covers formal visits (state, official, goodwill, working) by Chinese presidents and premiers from 1998 to 2020. It provides insights into patterns in how both the Chinese president and the premier approach international relations, highlighting key diplomatic priorities of the Chinese leadership up to the outbreak of the COVID-19 pandemic. While the data may seem dated, this period is in fact ideal for analysis, as the pandemic effectively halted all foreign travel by Chinese leaders after 2020, which would otherwise distort the data.

## Project contents

- `XXXX.ipynb` – a Jupyter Notebook with the main analysis
- `china_visits.csv` – cleaned version of the dataset
- `plots/` – visualizations of visit patterns

## Short description of your findings and key insights

- Russia and Kazakhstan are the most frequently visited countries.
- SCO and ASEAN memberships significantly increase the likelihood of visits.
- XXXXX IRAN / Russia? 
  
## Summary of the data collection process, with links

The data was compiled by Yu Wang and Randall W. Stone, scholars at the University of Rochester. The dataset includes auxiliary information such as the date, duration, purpose, involvement in multilateral meetings, and the sequence of visits.
- [Original data article](https://link.springer.com/article/10.1007/s11558-022-09459-z)
- [Dataset and documentation](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/GJYNU1)

## Overview of the data analysis process

- I started by looking for the raw data, which was available for download as a dta-file. I had never seen this format before and tried to import it with pandas, but that didn't work. The version of the Stata file was 99 and pandas only supports newer versions apparently. I then tried to convert the dta-file into a csv-file:

import pandas as pd

df = pd.read_stata("Programming/china_visits.v1.dta", convert_categoricals=False)

print(df.head())

But that didn't work. ValueError: Version of given Stata file is 99. pandas supports importing versions 105, 108, 111 (Stata 7SE), 113 (Stata 8/9), 114 (Stata 10/11), 115 (Stata 12), 117 (Stata 13), 118 (Stata 14/15/16),and 119 (Stata 15/16, over 32,767 variables).

I spent hours trying to figure it out and then ask somebody else to try the same. And it simply worked. The person had Python 3.13.5 and I only have Python 3.11.8. Was that the issue maybe? I honestly don't know. Anyhow, the person shared the csv with me to import.

---


## New skills, approaches, etc you used, or where you grew the most during the project

## Things you tried to do or wanted to do but did not have the skills/time (but if you have more time you might do)

- After importing the data I faced a strange problem - my project folder seemed to have an issue. The path from Github Desktop opened a different folder than the one I created originally. Which is strange, because the path was the same and it was supposily saved in the same folder and named the same. But the data didn't appear by opening it without Github Desktop. (It did with Jupyter Notebook, there I didn't have the problem. Not sure and difficult to explain. From that onwards I only opened the folder via Github Desktop. That helped. If I had more time I would have tried to understand the issue.

- If I would have more time, I would have tried to compare my data this other data set I found. https://academic.oup.com/isq/article/69/2/sqaf013/8081642

- My html had a lot of white space, something to do with my first graph. But I couldn't fix it.
