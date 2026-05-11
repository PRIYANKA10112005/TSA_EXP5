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
plt.plot(data['money'].head(150), label='Monthly sales')
plt.legend(loc='upper left')
plt.title('Monthly sales')

plt.subplot(4, 1, 2)
plt.plot(decomposition.trend.head(150), label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

plt.subplot(4, 1, 3)
plt.plot(decomposition.seasonal.head(150), label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

plt.subplot(4, 1, 4)
plt.plot(decomposition.resid.head(150), label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()
```
### OUTPUT:
ORIGINAL TIME SERIES DATA:
<img width="543" height="146" alt="image" src="https://github.com/user-attachments/assets/6fdc04fd-268b-47cc-bb08-3c5214d1f8c1" />


LINEAR TREND PLOT:
<img width="543" height="146" alt="image" src="https://github.com/user-attachments/assets/9a58dccf-18f9-4ad2-9893-5d7a37dc4c63" />


SEASONALITY PLOT:
<img width="547" height="146" alt="image" src="https://github.com/user-attachments/assets/3315d52f-8517-4364-843b-b99f2674ef6b" />


RESIDUAL PLOT:
<img width="554" height="146" alt="image" src="https://github.com/user-attachments/assets/0aebbb87-36ca-44bf-b340-e167a4f86b18" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
