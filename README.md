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
```
import seaborn as sns
import matplotlib.pyplot as plt
df=sns.load_dataset('tips')
df
```
![image](https://github.com/user-attachments/assets/d9ed497b-1875-4946-bf1a-2b67f05922f8)

```
sns.lineplot(x='total_bill',y='tip',data=df,hue='sex',linestyle='solid',legend='auto')
```
![image](https://github.com/user-attachments/assets/a434eba6-c069-4f4a-975e-849a58ba524a)

```
avg_tb=df.groupby('day')['total_bill'].mean()
avg_tip=df.groupby('day')['tip'].mean()
print(avg_tb)
print(avg_tip)
```
![image](https://github.com/user-attachments/assets/3d28bc29-c831-48a0-8257-e9c4c17b9b9e)

```
p1=plt.bar(avg_tb.index,avg_tb.values,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip.values,label='Tip')
plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/4d9104c2-c477-4b0c-9a3c-00476c8fa968)

```
avg_tb=df.groupby('time')['total_bill'].mean()
avg_tip=df.groupby('time')['tip'].mean()
p1=plt.bar(avg_tb.index,avg_tb.values,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip.values,label='Tip')
plt.xlabel('Time of the day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/07d04e5e-a1d4-4047-8bce-6fb29ed9d985)

```
sns.barplot(x='day',y='total_bill',hue='sex',data=df,palette='Set1')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Average Total Bill by Day and Sex')
```
![image](https://github.com/user-attachments/assets/11f99fed-7b32-4313-8898-cb54d04cb9e7)

```
sns.scatterplot(x='total_bill',y='tip',hue='sex',data=df)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs Tip Amount')
```
![image](https://github.com/user-attachments/assets/b9110e9b-241a-44ac-b5c2-3bb46ab7ac36)

```
import pandas as pd
df=pd.read_csv('/content/titanic_dataset.csv')
df
```

![image](https://github.com/user-attachments/assets/f32bf108-274b-4d19-b58f-c65cd79d4a56)

```
sns.histplot(data=df,x='Pclass',hue='Survived',kde=True)
```
![image](https://github.com/user-attachments/assets/e6b8f0fa-7577-45bc-bdcf-a7d679aaba80)

```
df=sns.load_dataset('tips')
sns.boxplot(x=df['day'],y=df['total_bill'],hue=df['sex'])
```

![image](https://github.com/user-attachments/assets/dfaf4efc-fd0f-4d7d-ba3b-fdfd1ea6a8a6)

```
sns.boxplot(x='day',y='total_bill',hue='smoker',data=df,linewidth=2,width=0.8,boxprops={"facecolor":"pink","edgecolor":"red"},whiskerprops={"color":"blue","linestyle":"-","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.2})
```

![image](https://github.com/user-attachments/assets/07ec2947-227a-40e0-9ed0-049af81c1512)

```
sns.violinplot(x='day',y='total_bill',hue='smoker',data=df,linewidth=2,width=0.6,palette='Set3',inner='quartile')
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/842fcdfc-5b25-439e-b227-a6345e6c64bd)

```
sns.set(style='darkgrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip)
```
![image](https://github.com/user-attachments/assets/37ef4c32-c62a-4b5b-9799-af005b6f3f2e)

```
sns.set(style='darkgrid')
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```
![image](https://github.com/user-attachments/assets/93868589-a429-46e3-8143-b330e5e16c80)

```
sns.set(style='darkgrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='tip',y='day',data=tip)
```
![image](https://github.com/user-attachments/assets/1e336f2f-5c60-4dd3-8448-46bbad95d6a4)

```
sns.kdeplot(data=df,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set1',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/19fd2d56-78b4-4f6f-aea9-8c38c529893d)

```
sns.kdeplot(data=df,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='Set1',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/d4f77d82-ded8-470f-9256-baffaeda0edd)

```
import matplotlib.pyplot as plt
import numpy as np
df=sns.load_dataset('tips')
numeric_cols=df.select_dtypes(include=[np.number]).columns
corr=df[numeric_cols].corr()
hm=sns.heatmap(corr,annot=True,cmap='YlGnBu',linewidths=0.5)
```

![image](https://github.com/user-attachments/assets/a9b2fe2a-8615-4418-bca8-b90e62be0f8a)

# Result:
Thus the data visualization using seaborn executed successfully.
