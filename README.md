# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
import seaborn as sns
import matplotlib.pyplot as plt
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x, y=y)
<img width="725" height="505" alt="image" src="https://github.com/user-attachments/assets/5b06b902-51d9-4f35-8390-c1e23f730183" />



df = sns.load_dataset("tips")
sns.lineplot(x="total_bill", y="tip", data=df, hue="sex", linestyle='solid', legend='auto')
<img width="764" height="533" alt="image" src="https://github.com/user-attachments/assets/96fba66e-822d-4e7b-977e-e9638ff0f64b" />



x = [1, 2, 3, 4, 5]
y1 = [3, 5, 2, 6, 1]
y2 = [1, 6, 4, 3, 8]
y3 = [5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title('Multi-Line Plot')
plt.xlabel('X Label')
plt.ylabel('Y Label')
<img width="752" height="563" alt="image" src="https://github.com/user-attachments/assets/c340e07f-da48-4009-a910-498e41a405f8" />



import seaborn as sns
import matplotlib.pyplot as plt
tips = sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
<img width="988" height="785" alt="image" src="https://github.com/user-attachments/assets/846b286d-4f25-4c12-85ef-ee978d336c2e" />



avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip = tips.groupby('time')['tip'].mean()
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip', width=0.4)
plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
<img width="764" height="563" alt="image" src="https://github.com/user-attachments/assets/804765f3-cf52-42ef-b0a3-2c446bff369e" />



years = range(2000, 2012)
apples = [0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
<img width="756" height="505" alt="image" src="https://github.com/user-attachments/assets/6d6bf691-943a-4789-b798-bebfaf1d8c63" />



import seaborn as sns
dt = sns.load_dataset('tips')
# Bar plot with hue parameter
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
# Set labels and title
plt.xlabel('Day of the Week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')
<img width="764" height="563" alt="image" src="https://github.com/user-attachments/assets/c672eecb-873c-42a3-9798-bdc72ac3ec7d" />



import pandas as pd 
tit = pd.read_csv("titanic_dataset.csv")
tit
<img width="593" height="294" alt="image" src="https://github.com/user-attachments/assets/0f99c186-97f1-4f52-8854-fb2a3522348e" />



plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare',data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
<img width="988" height="674" alt="image" src="https://github.com/user-attachments/assets/8be2661a-ee2d-4597-9198-05293a96adb8" />




plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare',data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
<img width="1000" height="674" alt="image" src="https://github.com/user-attachments/assets/e3f69df0-f6dd-4e92-abf1-c88c660ba111" />



import seaborn as sns
# Load the tips dataset
tips = sns.load_dataset('tips')
# Scatter plot of total bill vs. tip amount
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
# Set labels and title
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
<img width="772" height="572" alt="image" src="https://github.com/user-attachments/assets/c1f3aa4c-62fa-4edc-8fa9-d1d3d940df0a" />



import seaborn as sns
import matplotlib.pyplot as plt # implicitly used by seaborn plots
import numpy as np
import pandas as pd
np.random.seed(1)
num_var = np.random.randn(1000)
num_var = pd.Series(num_var, name = "Numerical Variable")
sns.histplot(data = num_var, kde = True)
<img width="777" height="532" alt="image" src="https://github.com/user-attachments/assets/de0c9836-f49a-45bb-9581-a1a8d37320b9" />



import seaborn as sns
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
np.random.seed(0)
marks = np.random.normal(loc=70, scale=10, size=100)
marks
<img width="632" height="427" alt="image" src="https://github.com/user-attachments/assets/6af11851-b598-4080-a964-fdaf2c1d3eea" />



sns.histplot(data=marks, bins=10, kde=True, stat='count', cumulative=False, multiple='stack', element='bars', palette='Set1', shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of Students Marks')
<img width="783" height="563" alt="image" src="https://github.com/user-attachments/assets/4732e53e-a53d-4e88-9497-e6844b65033d" />



import seaborn as sns
import pandas as pd
tips = sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips['total_bill'], hue=tips['sex'])
<img width="765" height="532" alt="image" src="https://github.com/user-attachments/assets/23ddd26f-65c9-4705-b0f4-a7c9deae3a2c" />



sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"}, whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
<img width="765" height="532" alt="image" src="https://github.com/user-attachments/assets/3653f42f-e262-480f-a058-82b8d15a8d75" />



sns.boxplot(x='Pclass', y='Age', data=tit, palette='rainbow')
plt.title("Age by Passenger Class, Titanic")
<img width="764" height="563" alt="image" src="https://github.com/user-attachments/assets/871747ac-01bc-44a2-bca9-5c8e96396318" />



sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6,
               palette="Set3", inner="quartile")
# Add labels and title
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
<img width="764" height="563" alt="image" src="https://github.com/user-attachments/assets/0401653f-5490-472c-b6a3-f9c8e6dc5830" />



import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x='day', y='tip', data = tip)
<img width="698" height="542" alt="image" src="https://github.com/user-attachments/assets/4d010ca4-d84a-4973-8dfa-97e786a70f38" />



sns.set(style="whitegrid")
sns.violinplot(x="tip",y="day",data=tip)
<img width="793" height="542" alt="image" src="https://github.com/user-attachments/assets/05a136ae-430f-406f-be22-4228d1eca099" />



sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='fill', linewidth=3, palette='Set2', alpha=0.8)
<img width="779" height="550" alt="image" src="https://github.com/user-attachments/assets/5f6856ed-00c7-4d34-9852-708964cab904" />


# Result:
Thus Performed Data Visualization using seaborn python library for the given datas.
