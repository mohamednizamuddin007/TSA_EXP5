# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
## Date: 02.05.2026
## NAME : MOHAMED NIZAMUDDIN A
## REG NO: 212224040194


## AIM:
To illustrate time series analysis and decomposition on daily humidity data using the Daily Delhi Climate dataset.

## TOOLS USED:
GOOGLE COLAB SOFTWARE 
## ALGORITHM:
1. Import the required packages like pandas, numpy and matplotlib.
2. Read the dataset using pandas.
3. Convert the date column into datetime format and set it as index.
4. Perform seasonal decomposition on humidity data.
5. Plot original, trend, seasonal and residual components.
6. Display the overall results.

## PROGRAM:


```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Load YOUR dataset
data = pd.read_csv('DailyDelhiClimateTrain.csv', parse_dates=['date'], index_col='date')

# Step 2: Perform decomposition on humidity
decomposition = seasonal_decompose(data['humidity'], model='additive', period=30)

# Step 3: Plot decomposition

plt.figure(figsize=(10, 12))

# Original Data
plt.subplot(411)
plt.plot(data['humidity'], label='Daily Humidity')
plt.legend(loc='upper left')
plt.title('Original Time Series Data')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend Plot')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()

```




### OUTPUT:

<img width="989" height="1189" alt="image" src="https://github.com/user-attachments/assets/1c97c326-b93a-461a-8e2e-ddfa08316f38" />



### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
