## EXP 2:  TIME SERIES ANALYSIS AND DECOMPOSITION
## NAME : LIVYA DHARSHINI G
## REGISTER NUMBER : 2305001013
## AIM
To perform time series analysis and decomposition on the monthly average temperature of a city using Python.
## objective 
• To create monthly temperature time-series data using Pandas.

• To visualize temperature variations using Matplotlib.

• To decompose the time series into observed, trend, seasonal, and residual components using the seasonal_decompose() function.

• To understand the components of additive time-series decomposition.
## program
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Create monthly temperature data
temperature = [
    25, 27, 29, 32, 34, 33,
    32, 31, 30, 29, 27, 25
]

# Repeat data for 2 years (24 months)
temperature = temperature * 2

# Step 2: Create date index
dates = pd.date_range(
    start="2025-01-01",
    periods=24,
    freq="ME"
)

# Step 3: Create time series
data = pd.Series(
    temperature,
    index=dates
)

# Step 4: Display data
print("Monthly Temperature:")
print(data)

# Step 5: Plot original time series
plt.figure(figsize=(10, 5))
plt.plot(
    data.index,
    data.values,
    marker="o"
)

plt.title("Monthly Average Temperature")
plt.xlabel("Month")
plt.ylabel("Temperature (°C)")
plt.grid()
plt.show()

# Step 6: Decompose the time series
result = seasonal_decompose(
    data,
    model="additive",
    period=12
)

# Step 7: Display decomposition
result.plot()
plt.show()
```
## output
<img width="182" height="327" alt="image" src="https://github.com/user-attachments/assets/c70ec048-d31d-482b-b4dc-f0ab2a3cdafb" />

<img width="610" height="683" alt="image" src="https://github.com/user-attachments/assets/da7f1cb5-188b-4339-ac32-6af87e312390" />

## Result
The monthly temperature time series was successfully plotted and decomposed into observed,
trend, seasonal, and residual components using Python.

