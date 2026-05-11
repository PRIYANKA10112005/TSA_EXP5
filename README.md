# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date:11-05-2026

### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```PY
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('/content/index_1.csv',
                   parse_dates=['date'],
                   index_col='date')

decomposition = seasonal_decompose(
    data['money'],
    model='additive',
    period=12
)

plt.figure(figsize=(10, 12))

plt.subplot(4, 1, 1)
plt.plot(data['money'], label='Monthly sales')
plt.legend(loc='upper left')
plt.title('Monthly sales')

plt.subplot(4, 1, 2)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

plt.subplot(4, 1, 3)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

plt.subplot(4, 1, 4)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()
```
### OUTPUT:
ORIGINAL TIME SERIES DATA:
<img width="543" height="146" alt="image" src="https://github.com/user-attachments/assets/1ffa127a-e700-4784-8862-23461fa6fbc1" />

LINEAR TREND PLOT:
<img width="543" height="146" alt="image" src="https://github.com/user-attachments/assets/be5ab9ff-7cf1-49c6-b2a9-fd372a2ca38e" />

SEASONALITY PLOT:
<img width="547" height="146" alt="image" src="https://github.com/user-attachments/assets/bfc61579-d6f1-4339-9f9a-b5cf88860b97" />

RESIDUAL PLOT:
<img width="554" height="146" alt="image" src="https://github.com/user-attachments/assets/646c8734-28d3-48d6-98cb-51d0c5427972" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
