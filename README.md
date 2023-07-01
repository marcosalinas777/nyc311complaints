# nyc311complaints
NYC 311 is a non-emergency phone number and online portal that residents and visitors in New York City can use to access various government services, report complaints, and get information about city programs and events.
<br>
<br>
import pandas as pd
import matplotlib as plt
<br>
<br>
df = pd.read_csv('https://raw.githubusercontent.com/CunyLaguardiaDataAnalytics/datasets/master/311_Service_Requests_from_2019May.csv')
<br>
<br>
df
<br>
<br>
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/5de6b4e3-4c0e-4003-b826-55dd4e1d193a)
<br>
<br>
<b>We want to see which is the Borough with the most complaints<b>
<br>
<br>
df.groupby(['Borough'])['Unique Key'].count().sort_values(ascending=False)
<br>
<br>
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/d6393ee1-4468-4614-a57b-b30f9faec8df)
<br>
<br>


