# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)

## Name:H.Berjin Shabeck
## Reg no:212222240018
## Date:31/08/2024

### AIM:
To Compute the AutoCorrelation Function (ACF) of the given study hour score data..
### ALGORITHM:
1. Import the necessary packages
2. give the necessary score data.
3. Find the mean, variance and then implement normalization for the data.
4. Implement the correlation using necessary logic and obtain the results
5. Store the results in an array
6. Represent the result in graphical representation as given below.
### PROGRAM:
```
import numpy as np
import matplotlib.pyplot as plt
df = pd.read_csv('score.csv')
n = len(scores)
lags = 35
acf_values = np.zeros(lags)


mean_scores = np.mean(scores)
variance_scores = np.var(scores)

normalized_data = scores - mean_scores

for lag in range(lags):
    autocovariance = 0
    for i in range(n - lag):
        autocovariance += normalized_data[i] * normalized_data[i + lag]
    acf_values[lag] = autocovariance / (n * variance_scores)

plt.figure(figsize=(10, 6))
plt.stem(range(lags), acf_values, use_line_collection=True)
plt.title('Autocorrelation Function (ACF) for Scores')
plt.xlabel('Lags')
plt.ylabel('ACF Value')
plt.grid(True)
plt.show()
```

### OUTPUT:
![download](https://github.com/user-attachments/assets/86e4b414-3bd2-4452-8fb4-bbb138da80e2)


### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
