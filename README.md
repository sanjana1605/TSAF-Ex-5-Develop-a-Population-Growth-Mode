# TSAF-Ex-5-Develop-a-Population-Growth-Mode

## AIM:
To develop a simple mathematical model for population growth using Python and use the
model to predict future population.


## PROGRAM:

```
import matplotlib.pyplot as plt
import numpy as np

# Monthly tracking data
month = np.array([1, 2, 3, 4, 5, 6]) # Months Jan-Jun
mau = np.array([12000, 14500, 16800, 19000, 21500, 24000])
# Time indices (t = 0 to 5)
t = np.arange(len(month))

# Fit linear model
slope, intercept = np.polyfit(t, mau, 1)

# Model predictions
predicted_mau = intercept + slope * t
print(f"Initial MAU: {intercept:.2f}")
print(f"Monthly Active User Increase: {slope:.2f}")
print("\nMonth Actual MAU Predicted MAU")
for m, act, pred in zip(month, mau, predicted_mau):
 print(f"{m:5d} {act:10d} {pred:13.2f}")

# Future projections for months 7, 8, 9
future_month = np.array([7, 8, 9])
future_t = np.array([6, 7, 8])
future_mau = intercept + slope * future_t
print("\nFuture MAU Forecast:")
for fm, f_mau in zip(future_month, future_mau):
 print(f"Month {fm}: {round(f_mau)} users")

# Plotting
plt.plot(month, mau, 'o-', label='Actual MAU')
plt.plot(month, predicted_mau, 'x--', label='Model Fit')
plt.plot(future_month, future_mau, 's:', label='3-Month Forecast')
plt.title("E-Commerce Platform Active Users Growth")
plt.xlabel("Month Index")
plt.ylabel("Monthly Active Users")
plt.legend()
plt.grid(True)
plt.show()
```

## OUTPUT:
<img width="525" height="497" alt="image" src="https://github.com/user-attachments/assets/27a0953b-a65c-4ec7-9bdf-a140e905eb8e" />
