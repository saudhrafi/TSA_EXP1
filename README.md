# Ex.No: 01A PLOT A TIME SERIES DATA

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:

```python
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv("weatherHistory.csv")
data['Formatted Date'] = pd.to_datetime(data['Formatted Date'], utc=True)
data.set_index('Formatted Date', inplace=True)

print("Mean Temperature:", data['Temperature (C)'].mean())
print("Mean Apparent Temperature:", data['Apparent Temperature (C)'].mean())
print("Mean Humidity:", data['Humidity'].mean())
print("Mean Wind Speed:", data['Wind Speed (km/h)'].mean())

plt.figure(figsize=(12, 6))
plt.plot(data['Temperature (C)'])
plt.title('Temperature over Time')
plt.xlabel('Date')
plt.ylabel('Temperature (C)')
plt.show()

plt.figure(figsize=(12, 6))
plt.plot(data['Apparent Temperature (C)'])
plt.title('Apparent Temperature over Time')
plt.xlabel('Date')
plt.ylabel('Apparent Temperature (C)')
plt.show()

plt.figure(figsize=(12, 6))
plt.plot(data['Humidity'])
plt.title('Humidity over Time')
plt.xlabel('Date')
plt.ylabel('Humidity')
plt.show()

plt.figure(figsize=(12, 6))
plt.plot(data['Wind Speed (km/h)'])
plt.title('Wind Speed over Time')
plt.xlabel('Date')
plt.ylabel('Wind Speed (km/h)')
plt.show()

monthly_avg = data.resample('M').mean(numeric_only=True)
plt.figure(figsize=(12, 6))
plt.plot(monthly_avg['Temperature (C)'])
plt.title('Average Monthly Temperature')
plt.xlabel('Month')
plt.ylabel('Temperature (C)')
plt.show()

yearly_avg = data.resample('Y').mean(numeric_only=True)
plt.figure(figsize=(12, 6))
plt.plot(yearly_avg['Temperature (C)'])
plt.title('Average Yearly Temperature')
plt.xlabel('Year')
plt.ylabel('Temperature (C)')
plt.show()
```

# OUTPUT:
<img width="1977" height="934" alt="image" src="https://github.com/user-attachments/assets/1e644ad1-aad9-475e-967e-7c804b1a7b6b" />
<img width="1744" height="835" alt="image" src="https://github.com/user-attachments/assets/1e5a787f-483d-4585-9c8b-501768d4ad4c" />
<img width="2092" height="819" alt="image" src="https://github.com/user-attachments/assets/ec0e6ce6-f532-4b75-bb45-cff3c9ca0034" />
<img width="1759" height="826" alt="image" src="https://github.com/user-attachments/assets/84fdef92-8eef-4542-b41f-e4e3cd304991" />
<img width="1651" height="877" alt="image" src="https://github.com/user-attachments/assets/55ea5666-8b1a-4857-9a76-6e4578fb65af" />
<img width="1623" height="883" alt="image" src="https://github.com/user-attachments/assets/8a7a13ed-bc84-4787-802d-907417bbac61" />







# RESULT:
Thus we have created the python code for plotting the time series of given data.
