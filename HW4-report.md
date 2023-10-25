# HW 4 - CS 625, Fall 2023

Eikra Shithil 
Due: October 27, 2023

## Dataset 1

## First Births by Age

I have written a python code to help me plot the data. This data shows the number of first births out of 1000 women and the age they have their first birth.

From the observations of this line plot, we see a steady increase in the number of first births among women aged: 30 to 34, 35 to 39 and even 40 to 44. The most increase being in in the 30 to 34 age group. 

In contrast, we can see a slight decrease in the number of first birth among the age groups: 15 to 19 and 20 to 24. This decrease being the most prominent from 2000 to 2008. 

The age group that has stayed consistent is women ages 25 to 29. There has not been a trend of increase or decrease of the number of first births in this age group. 

I have added a second plot to show the total number of first births in all the age groups in the second plot. The total shows that the number of first births in general has also seen a decrease since 1980

### Line Plot for first births out of 1000 women by age

![Line Plot First Birth](HW4FirstBirthbyAge.png)

![Line Plot First Birth Total](HW4FirstBirthbyAgeTotal.png)

## Total Births by Age

This data shows the number of total births out of 1000 women and the age of the women.

From the observations of this line plot, we see a steady increase in the number of total births among women aged: 30 to 34, 35 to 39 and even 40 to 44. The most increase being in in the 35 to 39 age group. 

In contrast, we can see a slight decrease in the number of total birth among the age groups: 15 to 19 and 25 to 29. 

The age group that has stayed relatively consistent is women ages 20 to 24. There has not been a trend of increase or decrease of the number of total births in this age group. 

I have added a second plot to show the total number of total births in all the age groups in the second plot. The total shows that the number of total births in general has also seen a decrease since 1980. 

These trends are very similar to the "first births" charts.

### Line Plot for total births out of 1000 women by age

![Line Plot First Birth](HW4TotalBirthbyAge.png)

![Line Plot First Birth Total](HW4TotalBirthbyAgeTotal.png)

### Python Code

```{python}
import pandas as pd
import seaborn.objects as so
import matplotlib.pyplot as plt
import numpy as np

from google.colab import drive

data91FB = pd.DataFrame(pd.read_excel("/content/drive/MyDrive/DataCS625HW4/FirstBirth.xlsx"))
data91TB = pd.DataFrame(pd.read_excel("/content/drive/MyDrive/DataCS625HW4/TotalBirth.xlsx"))
data92 = pd.DataFrame(pd.read_excel('https://www2.census.gov/library/publications/2010/compendia/statab/129ed/tables/10s0092.xls'))

data91FB = data91FB.apply(pd.to_numeric, errors='coerce')
data91FB = data91FB.transpose()

data91FB['Years'] = data91FB.index

years = data91FB['Years'].tolist()
years.pop(0)

total = data91FB[0].tolist()
total.pop(0)

y15to19 = data91FB[2].tolist()
y15to19.pop(0)

y20to24 = data91FB[3].tolist()
y20to24.pop(0)

y25to29 = data91FB[4].tolist()
y25to29.pop(0)

y30to34 = data91FB[6].tolist()
y30to34.pop(0)

y35to39 = data91FB[7].tolist()
y35to39.pop(0)

y40to44 = data91FB[8].tolist()
y40to44.pop(0)

f = plt.figure(1)
#totalplt = plt.plot(years, total, label = 'Total')  # Plot the chart
y1519plt = plt.plot(years, y15to19, label = '15 to 19 yo')  # Plot the chart
y2024plt = plt.plot(years, y20to24, label = '20 to 24 yo')  # Plot the chart
y2529plt = plt.plot(years, y25to29, label = '25 to 29 yo')  # Plot the chart
y3034plt = plt.plot(years, y30to34, label = '30 to 34 yo')  # Plot the chart
y3539plt = plt.plot(years, y35to39, label = '35 to 39 yo')  # Plot the chart
y4044plt = plt.plot(years, y40to44, label = '40 to 44 yo')  # Plot the chart
plt.xticks(rotation=90, ha='right')
leg = plt.legend(loc='center right', bbox_to_anchor=(1.3, 0.5))
plt.xlabel('Year')
plt.ylabel('Number of Births')
plt.title('First Births per 1,000 Women')
f.show()  # display

g = plt.figure(2)
y1519plt = plt.plot(years, y15to19, label = '15 to 19 yo')  # Plot the chart
y2024plt = plt.plot(years, y20to24, label = '20 to 24 yo')  # Plot the chart
y2529plt = plt.plot(years, y25to29, label = '25 to 29 yo')  # Plot the chart
y3034plt = plt.plot(years, y30to34, label = '30 to 34 yo')  # Plot the chart
y3539plt = plt.plot(years, y35to39, label = '35 to 39 yo')  # Plot the chart
y4044plt = plt.plot(years, y40to44, label = '40 to 44 yo')  # Plot the chart
totalplt = plt.plot(years, total, label = 'Total')  # Plot the chart
plt.xticks(rotation=90, ha='right')
leg = plt.legend(loc='center right', bbox_to_anchor=(1.3, 0.5))
plt.xlabel('Year')
plt.ylabel('Number of Births')
plt.title('First Births per 1,000 Women')
g.show()  # display

data91TB = data91TB.apply(pd.to_numeric, errors='coerce')
data91TB = data91TB.transpose()

data91TB['Years'] = data91TB.index

years = data91TB['Years'].tolist()
years.pop(0)

total = data91TB[0].tolist()
total.pop(0)

y15to19 = data91TB[2].tolist()
y15to19.pop(0)

y20to24 = data91TB[3].tolist()
y20to24.pop(0)

y25to29 = data91TB[4].tolist()
y25to29.pop(0)

y30to34 = data91TB[6].tolist()
y30to34.pop(0)

y35to39 = data91TB[7].tolist()
y35to39.pop(0)

y40to44 = data91TB[8].tolist()
y40to44.pop(0)

h = plt.figure(3)
#totalplt = plt.plot(years, total, label = 'Total')  # Plot the chart
y1519plt = plt.plot(years, y15to19, label = '15 to 19 yo')  # Plot the chart
y2024plt = plt.plot(years, y20to24, label = '20 to 24 yo')  # Plot the chart
y2529plt = plt.plot(years, y25to29, label = '25 to 29 yo')  # Plot the chart
y3034plt = plt.plot(years, y30to34, label = '30 to 34 yo')  # Plot the chart
y3539plt = plt.plot(years, y35to39, label = '35 to 39 yo')  # Plot the chart
y4044plt = plt.plot(years, y40to44, label = '40 to 44 yo')  # Plot the chart
plt.xticks(rotation=90, ha='right')
leg = plt.legend(loc='center right', bbox_to_anchor=(1.3, 0.5))
plt.xlabel('Year')
plt.ylabel('Number of Births')
plt.title('Total Births per 1,000 Women')
h.show()  # display

k = plt.figure(4)
y1519plt = plt.plot(years, y15to19, label = '15 to 19 yo')  # Plot the chart
y2024plt = plt.plot(years, y20to24, label = '20 to 24 yo')  # Plot the chart
y2529plt = plt.plot(years, y25to29, label = '25 to 29 yo')  # Plot the chart
y3034plt = plt.plot(years, y30to34, label = '30 to 34 yo')  # Plot the chart
y3539plt = plt.plot(years, y35to39, label = '35 to 39 yo')  # Plot the chart
y4044plt = plt.plot(years, y40to44, label = '40 to 44 yo')  # Plot the chart
totalplt = plt.plot(years, total, label = 'Total')  # Plot the chart
plt.xticks(rotation=90, ha='right')
leg = plt.legend(loc='center right', bbox_to_anchor=(1.3, 0.5))
plt.xlabel('Year')
plt.ylabel('Number of Births')
plt.title('Total Births per 1,000 Women')
k.show()  # display
```

## Conclusion

In conslusion, this data shows us that women are waiting longer to have children. The 30s are seeming more like the 20s when it comes to the time of first births and total births. The overall birth rate is also decreseing as less women are per 1000 women are having children. 

## Further Study

For future studies, we can look into factors such as income, inflation, health statistics and education for women that may be playing into these trends of having fewer children / having children later in life. I think that all these factors play into the decision to have children. Women want to be more financially stable before having children to high inflation rates will decrease the urgency to have children. Women may choose to finish their higher level education before having children which pusses back when they start trying for children. Additionally, people may be in better health later in life or have more access to medical tools/methods to help conceive at later ages. I think all these play a big factor in these trends.

## References

* Reference 1, <https://builtin.com/data-science/matplotlib-legend-outside-plot>
* Reference 2, <https://www.w3schools.com/python/matplotlib_labels.asp>
* Reference 3, <https://stackoverflow.com/questions/68917921/converting-object-type-column-to-float-type-converts-all-to-nan>
* Reference 4, <https://www.geeksforgeeks.org/line-chart-in-matplotlib-python/#>
* Reference 5, <https://stackoverflow.com/questions/20461165/how-to-convert-index-of-a-pandas-dataframe-into-a-column>
* Reference 6, <https://stackoverflow.com/questions/7744697/how-to-show-two-figures-using-matplotlib>
* Reference 7, <>
* Reference 8, <>
* Reference 9, <>
* Reference 10, <>
