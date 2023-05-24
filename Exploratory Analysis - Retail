#!/usr/bin/env python
# coding: utf-8

# In[65]:


#importing libraries
import pandas as pd
import numpy as np
import seaborn as sns
from matplotlib import pyplot as plt
get_ipython().run_line_magic('matplotlib', 'inline')


# In[66]:


#loading dataset
data=pd.read_csv("C:/Users/user14/Downloads/SampleSuperstore.csv")
data.head()


# In[67]:


data.shape  #dimensions of data


# In[68]:


data.describe()  #summary of data


# In[69]:


data.isnull().sum() #chaek null values


# In[70]:


data['Postal Code'] = data['Postal Code'].astype('object')


# In[71]:


corr = data.corr()
sns.heatmap(corr,annot=True,cmap='Reds')   #gives correlation


# In[72]:


data = data.drop(['Postal Code'],axis = 1)  #droping postal code columns


# In[73]:


#obs 1
sns.pairplot(data, hue = 'Ship Mode')    #gives scatter plot w.r.t ship mode


# In[74]:


data["Ship Mode"].value_counts() #gives counts for ship mode


# In[75]:


sns.countplot(x=data["Ship Mode"]) #barplot for ship mode


# In[76]:


#obs 2
sns.pairplot(data, hue = 'Segment')    #gives scatter plot w.r.t segment


# In[77]:


data["Segment"].value_counts() #gives counts for segment


# In[78]:


sns.countplot(x=data["Segment"]) #barplot for segment


# In[79]:


#obs 3
sns.pairplot(data, hue = 'Category')    #gives scatter plot w.r.t category


# In[80]:


data["Category"].value_counts() #gives count for category


# In[81]:


sns.countplot(x=data["Category"]) #barplot for category


# In[82]:


#obs 4
data["Sub-Category"].value_counts() #gives counts w.r.t sub-category


# In[83]:


sns.pairplot(data,hue="Sub-Category") #gives scatterplot for sub-category


# In[84]:


plt.figure(figsize=(10,8))
data['Sub-Category'].value_counts().plot.pie()
plt.show()  #gives piechart for individual sub-category


# Here,Maximum sub-category are from Binders, Paper, furnishings, Phones, storage, art, accessories and minimum sub-category are from copiers, machines, suppliers.

# In[85]:


#obs 5
data["State"].value_counts()
plt.figure(figsize=(10,8))
sns.countplot(x='State',data=data,palette='rocket_r',order=data['State'].value_counts().index)
plt.xticks(rotation=90)
plt.show()     #gives barplot for various states


# Here,Highest number of buyers are from California and New York city.

# In[86]:


#obs 6
data.hist(figsize=(7,7),bins=50)
plt.show()    #gives histogram for variuos columns


# Here, Most customers buys quantity of type 2 and 3 respectively and
#       discount tends to be large between 0% to 20%.

# In[87]:


#obs 7
data.groupby('Segment')[['Profit','Sales']].sum().plot.bar(color=['pink','blue'],figsize=(5,3))
plt.ylabel('Profit/Loss and sales')
plt.show()     #gives multiple bar chart for profit and sales w.r.t segment


# Here,profit and sales are maximum in Consumer however minimum in Home Office segment.

# In[88]:


#obs 8
data.groupby('Region')[['Profit','Sales']].sum().plot.bar(color=['orange','red'],figsize=(5,3))
plt.ylabel('Profit/Loss and sales')
plt.show()  #gives multiple bar chart for profit and sales w.r.t region


# Here,profit and sales are maximum in West region however minimum in South region.

# In[89]:


#obs 9
data.groupby('Category')[['Profit','Sales']].sum().plot.bar(color=['grey','purple'],alpha=0.9,figsize=(5,3))
plt.ylabel('Profit/Loss and sales')
plt.show()  #gives multiple bar chart for profit and sales w.r.t category


# Here,Technology and Office Suppliers having high however Furniture have low profit.

# In[90]:


#obs 10
ps = data.groupby('Sub-Category')[['Sales','Profit']].sum().sort_values(by='Sales',ascending=False)
ps[:].plot.bar(color=['red','lightblue'],figsize=(10,5))
plt.xlabel('Sub-Category')
plt.ylabel('Profit/loss & Sales')
plt.show()      #gives multiple bar chart for profit and sales w.r.t sub-category


# Here, Phones have high sales.
#       Chairs have high sales but less profit as compared to phones.
#       Tables and Bookcases has much less profit contains huge loss.
