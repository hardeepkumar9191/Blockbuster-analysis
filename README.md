# Running the notebook
1) Open the notebook in your respective environments
2) Run the cells in a descending order starting from the top. 
3) Make sure you have all the import packages installed.
# Possible errors
1) If any of the cells throws an error message, just rerun it and it should run properly. For example, the linear regression model cell might need to be run twice. Fitting the data into PCA might need to be run twice.
## Imports

```python
import urllib.request
from pathlib import Path
import os
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from pandas.tseries.holiday import USFederalHolidayCalendar as calendar
from sklearn.feature_selection import SelectKBest
from sklearn.feature_selection import f_regression, mutual_info_regression
from sklearn.decomposition import PCA
import warnings
foobar.pluralize('word') # returns 'words'
foobar.pluralize('goose') # returns 'geese'
foobar.singularize('phenomena') # returns 'phenomenon'
```

# Problem
The success of a movie is hard to be quantified or formulated. The known factors such as Actors, Director, Writers may not be the only deciding factor in a movie's success. There are external factors that contribute to the success and propel a movie into a blockbuster hit. 

We wanted to identify these external factors that would make a movie successful. So We choose various external factors that could possibly affect the success, factors such as the president, Alcohol consumption, GDP, CPI, and Unemployment rates. 

Movie Production companies, film producers, and Distributors have to make an informed decision on green-lighting movies. Our 
Directors and Actors want to choose a potential blockbuster
Besides the production team, they need everything else to be stimulative for a blockbuster.
We want to minimize the cost and maximize the revenue – marketing expenditure decreases if we choose right time to issue a movie.
For example, movie grossing decreases in current epidemics.

# Objective

By identifying the external factors that correlate to a movie's success Movie Production companies, Film producers and Publishers can make informed decisions in green-lighting movies.


# Factors

Factors that would cause the 
Classical factors: Producer, director, actors, script, genres
Social factors: ongoing social and cultural trends, e.g. alcohol consumption – how much people are willing to spend on entertainment.
Political factors: how election influence movie success?
Economic factors: GDP, CPI, unemployment rate, etc.
Time: issue day, weather of issue day, holiday or not, season, weekend or not, December of not, the day of week, the day of month, etc.


# Data Sources

It is highly recommended the use of the data source attached to this git project. But here are the links to download the data. 
Note: GDP, CPI, and Unemployment data were modified in the CSV format before being imported into their respective Dataframe. I filtered the CSV to the row that has United states data, copied that row, placed it at the top of the CSV, and deleted the rest of the data.  

[IMDB](https://www.kaggle.com/stefanoleone992/imdb-extensive-dataset)

[President](https://www.kaggle.com/samuelstoltenberg/us-presidents-and-first-ladies?select=presidents.csv)

[GDP](https://data.worldbank.org/indicator/NY.GDP.MKTP.CD?locations=US)

[CPI](https://data.worldbank.org/indicator/FP.CPI.TOTL?locations=US) 

[Unemployment](https://data.worldbank.org/indicator/SL.UEM.TOTL.NE.ZS?locations=US)

[Beer](https://ourworldindata.org/alcohol-consumption#global-beer-consumption)

[Spirits](https://ourworldindata.org/alcohol-consumption#global-consumption-of-spirits)

[Wine](https://ourworldindata.org/alcohol-consumption#global-wine-consumption)


## Validate the data
Validating the data involves the clean up of the raw data and transforming it into a format usable for merging and model processing.
We also visualized the data to understand and derive patterns and correlations that could affect the movie's success.

1) We only chose to work with movies made in the US
2) Redundant columns were dropped so that they would not affect the correlation
3) Converted the column to their respective types 
4) Transforming it into the required size for merging.


## Explore the data
We visualized the data to try and understand the factors that correlate and affect the movie's success.

## Feature creation from IMDB dataset
We created a set of features from the IMDB dataset to help us breakdown the dataset into a simpler form, this allows us to monitor the slight changes in the behaviour and correlation heatmap. 

Features created:
1) Profit - This column shows the profit of the movie. The profit is calculated by taking the Total gross income(Worldwide + Domestics) minus the budget.
2) Blockbuster - This is a binary column that indicates if a movie is a blockbuster or not. If the profit is more than 10X the budget it is a blockbuster. 1 means it is a blockbuster.
3) Year - Indicates the year the movie was published. 
4) Month - Indicated the month the movie was published.
5) Holiday - A binary column that indicates if the date is a holiday or not. 1 means it is a holiday.
6) workingday - A binary column that indicates if the date is a working day or not
7) Dayofweek -indicates the day of the week. 0 --> Monday, 1--> Tuesday-->...
8) Total_Movie_count - indicates the total number of movies released for that year.

# Results
Our initial assumption that the director, production company, holiday, workingday might be of high correlation with the profit, but it turns out that they have a really low correlation with the profit.

Also, we thought, GDP and CPI will have a positive correlation with the profit while unemployment has a negative one. But it turned out that it’s the opposite of our expectations.

For these opposite results, we’re still wondering what caused the counterintuitive results.


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update the tests as appropriate.



## License
Creative common License