# EX-05  CREATING DASHBOARDS WITH PLOTLY AND DASH
### AIM:
To implement Dashboards creation with Plotly and Dash using python.&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**DATE :18-11-2024**
### About Dash and Plotly tools:
Dash is a Python framework for building analytical web applications. Dash helps in building responsive web dashboards that is good to look at and is very fast without the need to understand complex front-end frameworks or languages such as HTML, CSS, JavaScript. Let’s build our first web dashboard using Dash.
Plotly library in Python is an open-source library that can be used for data visualization and understanding data simply and easily. Plotly supports various types of plots like line charts, scatter plots, histograms, box plots, etc.
### ALGORITHM:
- Step 1: Import Necessary Library like dash and plotly.
- Step 2: Load the dataset.
- Step 3: Add dropdown using layout function and include the necessary options.
- Step 4: Display the necessary visualization tools and include the necessary parameters.
- Step 5: Display the output.
### PROGRAM AND OUTPUT
```Python
import dash
from dash import dcc, html
from dash.dependencies import Input, Output
import plotly.express as px 
import pandas as pd
import plotly.graph_objects as px 
import numpy as np 
import matplotlib.pyplot as plt 
```

```Python
df=pd.read_csv('tips.csv')
df.head()
```
![image](https://github.com/user-attachments/assets/eab4366f-3712-48f5-b461-0fb01d54d29e)

```Python
plot=px.Figure(data=[px.Scatter( x=df['day'], y=df['tip'], mode='markers',) ])
plot.update_layout(updatemenus=[ dict(buttons=list([ dict( args=['type', 'scatter'], 
                   label='scatter', method='restyle' ), dict( args=['type', 'bar'], 
                   label='bar', method='restyle' ) ]), direction="down", ), ] )
plot.show()
```
![image](https://github.com/user-attachments/assets/4c8e17a2-3007-48e2-ac8f-0e536de8da13)

```Python
df=px.data.tips()
fig = px.scatter_3d(df, x="total_bill",y="sex",z="tip",color='day',size='total_bill',symbol='time')
fig.show()
```
![image](https://github.com/user-attachments/assets/562fde28-d527-40f5-8da5-eb09f76840f2)

```Python
df=px.data.tips()
fig = px.bar(df, x='day',y='total_bill',color='sex',facet_row='time',facet_col='sex')
fig.show()
```
![image](https://github.com/user-attachments/assets/0baa4c9c-9e21-4278-a6c7-d1bf35b1c5c7)

```Python
df=px.data.tips()
fig = px.histogram(df, x='total_bill',color='sex',nbins=50,histnorm='percent',barmode='overlay')
fig.show()
```
![image](https://github.com/user-attachments/assets/5c65e675-5505-49d9-a285-f82fdd67c8da)
```Python
plt.figure(fi)
df=px.data.tips()
fig = px.pie(df, values='total_bill',names='day')
fig.show()
```
![image](https://github.com/user-attachments/assets/c5ffd55d-85cc-4b1d-9030-85bfdab79ae0)

### RESULT:
Thus the program to implement Dashboards creation with Plotly and Dash using python is successfully implemented.

**Developed By: ROHIT JAIN D - 212222230120**
