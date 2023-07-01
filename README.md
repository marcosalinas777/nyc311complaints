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

![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/5de6b4e3-4c0e-4003-b826-55dd4e1d193a)
<br>
<br>
Let's take a look of which are the columns of this dataframe
<br>
<br>
df.columns

![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/cab7a9bb-0e42-4063-8a46-7ad3fd1a6109)
<br>
<br>
We want to see which is the Borough with the most complaints
<br>
<br>
df.groupby(['Borough'])['Unique Key'].count().sort_values(ascending=False)
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/d6393ee1-4468-4614-a57b-b30f9faec8df)
<br>
<br>
Let's see what's the total count of Noise Complaint Type in the dataframe
<br>
<br>
df[df['Complaint Type']=='Noise'].count()
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/7340e1a0-ad5e-4e85-a8c1-2b2df670f3d3)
<br>
<br>
If we want to in general Noise as a broad complaint type, and not only <b>Noise<b>, we can use the following method that will include a broader type of Noises.
df2=df[df['Complaint Type'].str.contains('oise')]
df2.count()
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/93aefdbe-546f-4ad4-9eb6-98a1fadad44b)
<br>
<br>
We can visualize that the code above brought in all types of Noise, because we used a "wildcard" method for the word Noise
<br>
df
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/4eb74b2d-22ae-4228-b0d5-923b0fb27192)
<br>
<br>
Let's plot a line chart of the above dataframe df2
<br>
df2.groupby(['Borough'])['Unique Key'].count().sort_values(ascending=False).plot()
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/05ba6cfc-f3ce-4cbd-8283-eeefc6ef4749)
<br>
<br>
The above dataframe df2 now its presented as a bar chart
<br>
df2.groupby(['Borough'])['Unique Key'].count().sort_values(ascending = False).plot(kind='bar')
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/cf5b2100-566f-4587-a8c1-c464e21e701a)
<br>
<br>
A similar way of groping the dataframe df2, by Borough and calling it to become a bar chart is achieved by the followig code:
<br>
<br>
grouping=df2.groupby(['Borough'])['Unique Key']
<br>
count_of_grouping=grouping.count()
<br>
sorting=count_of_grouping.sort_values(ascending=False)
<br>
sorting.plot(kind='bar')
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/ae01acf5-f68f-4565-aaf0-fc8c0766cc85)
<br>
<br>
If we want to see how many are the specific "Noise - Residential" Complaint type, we can see there are 5838 cases by using the .shape command
<br>
df_noise_res=df[df['Complaint Type'] =='Noise - Residential']
<br>
df_noise_res.shape
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/1b9f7f00-872f-45c3-88f9-32d1a3e82bd5)
<br>
<br>
If we want to see how many are the specific "Noise - Commercial" Complaint type, we can see there are 1297 cases by using the .shape command
<br>
df_noise_com=df[df['Complaint Type'] =='Noise - Commercial']
<br>
df_noise_com.shape
![image](https://github.com/marcosalinas777/nyc311complaints/assets/95108103/cdb1bd7c-15c3-4776-9015-92be899b9d72)





















