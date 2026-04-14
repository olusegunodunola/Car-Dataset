# Car-Dataset

# Car-DataSet

🚗 Car Dataset Analysis Project

This project demonstrates basic data cleaning and exploratory data analysis (EDA) on a car dataset using Python and pandas. It includes handling missing values, understanding feature distributions, filtering records, and applying simple transformations to derive insights about different car specifications.

📂 Dataset
The dataset used is:
Project+2+-+Cars+Dataset.csv

Key features include:
•	Make
•	Origin (e.g., Asia, Europe, USA)
•	Cylinders
•	EngineSize
•	Horsepower
•	Length
•	Wheelbase
•	Weight
•	MPG_City


Note: File path is currently set to a local drive. Update it based on your environment to load the data successfully.
🛠️ Technologies Used
•	Python 3.x
•	pandas


🔍 Key Analysis Tasks
✅ Data Cleaning
•	Identified and filled missing values in:
o	Cylinders
o	EngineSize
o	Horsepower
o	Length
o	Wheelbase
o	Weight
o	MPG_City


Each missing value was replaced with the column mean to ensure data consistency.
📊 Data Exploration
•	Displayed full dataset shape and previews using .head(), .shape, and .count()
•	Checked most common car makes with .value_counts()
•	Filtered cars by region: Asia and Europe
•	Retrieved cars with weight over 4000 lbs and cars under that threshold
•	Increased city fuel efficiency (MPG_City) by 3 using .apply(lambda x: x + 3)

🧪 Sample Insights
•	High-weight vehicles often come from North America
•	Cars of Asian origin are well-represented in the dataset
•	Data transformation on fuel efficiency can simulate improved performance or emissions regulation compliance
python car_data_analysis.py


🤝 Contributions
Feel free to fork, open issues, or submit pull requests to contribute to the project's enhancement.


Code:

#!/usr/bin/env python
# coding: utf-8

# In[19]:


import pandas as pd


# In[20]:


car = pd.read_csv (r"C:\Users\oodan\Downloads\Project+2+-+Cars+Dataset.csv")


# In[75]:


car


# In[76]:


car.head(50)


# In[77]:


car.shape


# In[82]:


car.isnull().sum()


# In[83]:


car['Cylinders'].fillna(car['Cylinders'].mean(), inplace = True)


# In[84]:


car.isnull().sum()


# In[85]:


car['EngineSize'].fillna(car['EngineSize'].mean(), inplace = True)


# In[48]:


car.isnull().sum()


# In[87]:


car['Horsepower'].fillna(car['Horsepower'].mean(), inplace = True)


# In[86]:


car.isnull().sum()


# In[56]:


car['Length'].fillna(car['Length'].mean(), inplace = True)


# In[57]:


car['Wheelbase'].fillna(car['Wheelbase'].mean(), inplace = True)


# In[59]:


car['Weight'].fillna(car['Weight'].mean(), inplace = True)


# In[65]:


car['MPG_City'].fillna(car['MPG_City'].mean(), inplace = True)


# In[89]:


car.isnull().sum()


# In[94]:


car.count()


# In[95]:


car.head(2)


# In[99]:


car.value_counts()


# In[100]:


car.head(2)


# In[101]:


car['Make'].value_counts()


# In[103]:


car.head(2)


# In[105]:


car[car['Origin'] == 'Asia']


# In[107]:


car[car['Origin'] == 'Europe']


# In[114]:


car[(car['Origin'] == 'Asia') | (car['Origin'] == 'Europe')]


# In[5]:


car.head(2)


# In[7]:


car[car['Weight']> 4000]


# In[10]:


car[~(car['Weight']> 4000)]


# In[11]:


car.head(2)


# In[17]:


car['MPG_City'] = car['MPG_City'].apply(lambda x: x + 3)


# In[21]:


car.head(2)


# In[ ]:




