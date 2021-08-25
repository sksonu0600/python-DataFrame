import pandas as pd
import numpy as np
from pandas import DataFrame, Series

covid=pd.read_csv("covid_19_india.csv")
covid

covid.head()

covid.tail()

covid.info()

type(covid)
covid.shape

covid.dtypes

covid2=covid.iloc[:,1:]
covid2

covid2

covid=covid2.copy()

covid

covid['ConfirmedIndianNational']=pd.to_numeric(covid['ConfirmedIndianNational'],errors='coerce')
covid['ConfirmedForeignNational']=pd.to_numeric(covid['ConfirmedForeignNational'],errors='coerce')


covid.info()

covid[covid.duplicated()].shape

covid2['Cured'].hist()


covid2['Deaths'].hist()


covid2['Confirmed'].hist()


covid2.boxplot(column=['Cured'])


covid2.boxplot(column=['Deaths'])


covid2.boxplot(column=['Confirmed'])

covid['Date'].value_counts().plot.bar()

covid['Time'].value_counts().plot.bar()

covid['State/UnionTerritory'].value_counts().plot.bar()
     

import seaborn as sns
cols = covid.columns 
colours = ['#000099', '#ffff00'] # specify the colours - yellow is missing. blue is not missing.
sns.heatmap(covid[cols].isnull(),
            cmap=sns.color_palette(colours))

covid[covid.isnull().any(axis=1)].head()





