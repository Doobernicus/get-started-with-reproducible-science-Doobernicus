---

# Get started with open reproducible science!

[Open reproducible science](https://www.earthdatascience.org/courses/intro-to-earth-data-science/open-reproducible-science/get-started-open-reproducible-science/) makes scientific methods, data and outcomes available to everyone. That means that *everyone* who wants should be able to **find**, **read**, **understand**, and **run** your workflows for themselves.

<img alt-text="Components of open science - accessible, reproducible, inclusive" src="https://www.earthdata.nasa.gov/s3fs-public/2021-11/Circle_Diagram_UPDATE_2.jpg?VersionId=pFRniRpjtgc_MEXUJKi9_sXLoMsSX.pB" width=500 />

 > Image from https://www.earthdata.nasa.gov/esds/open-science/oss-for-eso-workshops

Few if any science projects are 100% open and reproducible (yet!). However, members of the open science community have developed open source tools and practices that can help you move toward that goal. You will learn about many of those tools in [the Intro to Earth Data Science textbook](https://www.earthdatascience.org/courses/intro-to-earth-data-science/). Don't worry about learning all the tools at once -- we've picked a few for you to get started with.

1.  open reproducable science is science that has documented steps, open source tools, and clear and free access to the data and results; this is done so that anybody could follow the steps to get the same results without any outside knowledge or tools.

2.  python can be used to replace many licensed programs like excel, since python is open source, anybody can use your code without having to learn to use or pay for a special program or license.

3.  no, the name uses spaces and special characters which make it non-machine .

I can write clean code by:
  * Break up your code with space between blocks so that it is easier to read.
  * document your code with docstrings that explain what each part of the code is doing
  * use descriptive names of variables and functions that make it easier to follow


Advantages of clean code include:
  * Easy to follow and reproduce
  * easier to find and fix bugs
  * easier to make changes to the code later


```python
#can't get this to work :(
import pandas as pd
import seaborn as sns
```

Once you have run the cell above and imported `pandas`, **run the cell below**. It is a test cell that will tell you if you completed the task successfully. If a test cell isn't working the way you expect, check that you ran your code **immediately before** running the test.


```python
# DO NOT MODIFY THIS TEST CELL
points = 0
try:
    pd.DataFrame()
    points += 5
    print('\u2705 Great work! You correctly imported the pandas library.')
except:
    print('\u274C Oops - pandas was not imported correctly.')
print('You earned {} of 5 points for importing pandas'.format(points))
```

    ✅ Great work! You correctly imported the pandas library.
    You earned 5 of 5 points for importing pandas


*Climate at a Glance*

1.  the national oceanic and atomospheric administration collects the data
2.  over the whole world
3.  Celsius
4.  land surface temperature data is combined with sea surface temperature data

NOAA National Centers for Environmental information, Climate at a Glance: Global Time Series, published March 2023, retrieved on April 12, 2023 from https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/global/time-series


```python
# creating a URL link to retrieve data from
rapid_city_temp_url = ('https://www.ncei.noaa.gov/access/monitoring/'
                       'climate-at-a-glance/national/time-series/110/'
                       'tavg/1/4/1895-2023.csv?base_prd=true&begbase'
                       'year=1901&endbaseyear=2000')
rapid_city_temp_url
```




    'https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/national/time-series/110/tavg/1/4/1895-2023.csv?base_prd=true&begbaseyear=1901&endbaseyear=2000'




```python
# DO NOT MODIFY THIS TEST CELL
resp_url = _
points = 0

if type(resp_url)==str:
    points += 3
    print('\u2705 Great work! You correctly called your url variable.')
else:
    print('\u274C Oops - your url variable was not called correctly.')

if len(resp_url)==117:
    points += 3
    print('\u2705 Great work! Your url is the correct length.')
else:
    print('\u274C Oops - your url variable is not the correct length.')

print('You earned {} of 6 points for defining a url variable'.format(points))
```

    ✅ Great work! You correctly called your url variable.
    ❌ Oops - your url variable is not the correct length.
    You earned 3 of 6 points for defining a url variable





```python
# downloaded data with pandas
rapid_city_temp_df = pd.read_csv(rapid_city_temp_url, header=4, 
                        names=['Date', 'Temp', 'Anomoly'])
rapid_city_temp_df


```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Temp</th>
      <th>Anomoly</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>189504</td>
      <td>52.90</td>
      <td>1.85</td>
    </tr>
    <tr>
      <th>1</th>
      <td>189604</td>
      <td>52.34</td>
      <td>1.29</td>
    </tr>
    <tr>
      <th>2</th>
      <td>189704</td>
      <td>51.15</td>
      <td>0.10</td>
    </tr>
    <tr>
      <th>3</th>
      <td>189804</td>
      <td>50.79</td>
      <td>-0.26</td>
    </tr>
    <tr>
      <th>4</th>
      <td>189904</td>
      <td>50.61</td>
      <td>-0.44</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>124</th>
      <td>201904</td>
      <td>52.84</td>
      <td>1.79</td>
    </tr>
    <tr>
      <th>125</th>
      <td>202004</td>
      <td>50.88</td>
      <td>-0.17</td>
    </tr>
    <tr>
      <th>126</th>
      <td>202104</td>
      <td>51.87</td>
      <td>0.82</td>
    </tr>
    <tr>
      <th>127</th>
      <td>202204</td>
      <td>50.65</td>
      <td>-0.40</td>
    </tr>
    <tr>
      <th>128</th>
      <td>202304</td>
      <td>51.37</td>
      <td>0.32</td>
    </tr>
  </tbody>
</table>
<p>129 rows × 3 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [198562.0, 59.04]:
    points += 4
    print('\u2705 Great work! You correctly downloaded data.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for downloading data'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ❌ Oops - your data are not correct.
    You earned 1 of 5 points for downloading data


  > HINT: Check out the `type()` function below - you can use it to check that your data is now in `DataFrame` type object


```python
# Check that the data was imported into a pandas DataFrame
type(rapid_city_temp_df)
```




    pandas.core.frame.DataFrame




```python
# ncei has wacky years .iloc selects a row or column
rapid_city_temp_df.iloc[:,0] = rapid_city_temp_df.iloc[:,0] // 100

```


```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [1985.5, 59.04]:
    points += 4
    print('\u2705 Great work! You correctly cleaned up years.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for cleaning up years'.format(points))
```

    ❌ Oops - make sure to call your DataFrame for testing.



    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[9], line 11
          8 else:
          9     print('\u274C Oops - make sure to call your DataFrame for testing.')
    ---> 11 summary = [round(val, 2) for val in tmax_df_resp.mean().values]
         12 if summary == [1985.5, 59.04]:
         13     points += 4


    TypeError: NDFrame._add_numeric_operations.<locals>.mean() missing 1 required positional argument: 'self'


<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an EXTRA CHALLENGE? Modify the code to be **more expressive**.

Rewrite the code below to select columns by **name** instead of by **index**. You might find the [pandas User Guide section on slicing and dicing](https://pandas.pydata.org/docs/user_guide/indexing.html) to be useful. However - don't worry if you can't figure this out yet! We're going to talk a lot about how to use pandas `DataFrame`s. 


```python
#convert to celcius
rapid_city_temp_df["Temp_C"] = (rapid_city_temp_df["Temp"] - 32) * 5 / 9
rapid_city_temp_df

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Temp</th>
      <th>Anomoly</th>
      <th>Temp_C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1895</td>
      <td>52.90</td>
      <td>1.85</td>
      <td>11.611111</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1896</td>
      <td>52.34</td>
      <td>1.29</td>
      <td>11.300000</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1897</td>
      <td>51.15</td>
      <td>0.10</td>
      <td>10.638889</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1898</td>
      <td>50.79</td>
      <td>-0.26</td>
      <td>10.438889</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1899</td>
      <td>50.61</td>
      <td>-0.44</td>
      <td>10.338889</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>124</th>
      <td>2019</td>
      <td>52.84</td>
      <td>1.79</td>
      <td>11.577778</td>
    </tr>
    <tr>
      <th>125</th>
      <td>2020</td>
      <td>50.88</td>
      <td>-0.17</td>
      <td>10.488889</td>
    </tr>
    <tr>
      <th>126</th>
      <td>2021</td>
      <td>51.87</td>
      <td>0.82</td>
      <td>11.038889</td>
    </tr>
    <tr>
      <th>127</th>
      <td>2022</td>
      <td>50.65</td>
      <td>-0.40</td>
      <td>10.361111</td>
    </tr>
    <tr>
      <th>128</th>
      <td>2023</td>
      <td>51.37</td>
      <td>0.32</td>
      <td>10.761111</td>
    </tr>
  </tbody>
</table>
<p>129 rows × 4 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [1985.5, 15.02]:
    points += 4
    print('\u2705 Great work! You correctly converted to Celcius.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for converting to Celcius'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ❌ Oops - your data are not correct.
    You earned 1 of 5 points for converting to Celcius


<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an **EXTRA CHALLENGE**?
  1. As you did above, rewrite the code to be more expressive
  2. Using the code below as a framework, write and apply a **function** that converts to Celcius.
     > **Functions** let you reuse code you have already written
  
  3. You should also rewrite this function name to be more expressive.
  
        ```python
        def convert(temperature):
            """Convert temperature to Celcius"""
            return temperature # Put your equation in here

        dataframe['temp_c'] = dataframe['temp_f'].apply(convert)
        ```


```python
sns.set(font_scale=1.25, style = 'ticks')
rapid_city_temp_df.plot(
    x='Date', y='Temp_C', title= "Rapid City Temp Over Time",
    ylabel = "Temperature($^\circ$C)", xlabel = "Date", color = "magenta", figsize = (16, 6), legend = False)


```




    <Axes: title={'center': 'Rapid City Temp Over Time'}, xlabel='Date', ylabel='Temperature($^\\circ$C)'>




    
![png](get_started_with_open_reproducible_science_files/get_started_with_open_reproducible_science_21_1.png)
    


**THIS ISN'T THE END! Don't forget to complete the next task where you will describe your plot**
    
<img src="https://www.nps.gov/pais/learn/nature/images/NPS-KempsRidley-Hatchlings.JPG" height=150 style="padding: 1em; border-style: solid; border-color: grey;" />

> Image source: https://www.nps.gov/pais/learn/nature/hatchlingreleases.htm

<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an **EXTRA CHALLENGE**?

There are many other things you can do to customize your plot. Take a look at the [pandas plotting galleries](https://pandas.pydata.org/docs/user_guide/visualization.html) and the [documentation of plot](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.plot.html) to see if there's other changes you want to make to your plot. Some possibilities include:
  * Remove the legend since there's only one data series
  * Increase the figure size
  * Increase the font size
  * Change the colors
  * Use a bar graph instead (usually we use lines for time series, but since this is annual it could go either way)
  * Add a trend line

"Average Rapid City Temperatures Trending Upwards"

**THIS ISN'T THE END EITHER! Don't forget to reproduce your analysis in a new location!**

<img src="https://static.independent.co.uk/s3fs-public/thumbnails/image/2008/12/26/20/107000.jpg" height=150 style="padding: 1em; border-style: solid; border-color: grey;" >

> Image source: https://www.independent.co.uk/climate-change/news/by-the-left-quick-march-the-emperor-penguins-migration-1212420.html

## Your turn: pick a new location and/or measurement to plot
Below, recreate the workflow you just did in a place that interests you OR with a different measurement. See the instructions above fore how to get your URL. You will need to make your own new Markdown and Code cells below this one.


```python
na_avg_temp = ('https://www.ncei.noaa.gov/access/monitoring'
                '/climate-at-a-glance/global/time-series'
                '/northAmerica/land/1/4/1850-2023/data.csv')
na_avg_temp
```




    'https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/global/time-series/northAmerica/land/1/4/1850-2023/data.csv'




```python
# downloaded data with pandas
na_avg_temp_df = pd.read_csv(na_avg_temp, header=4, 
                        names=['Date', 'Temp'])
na_avg_temp_df



```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1910</td>
      <td>0.35</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1911</td>
      <td>-0.98</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1912</td>
      <td>-0.28</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1913</td>
      <td>-0.03</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1914</td>
      <td>-0.98</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>109</th>
      <td>2019</td>
      <td>1.26</td>
    </tr>
    <tr>
      <th>110</th>
      <td>2020</td>
      <td>0.37</td>
    </tr>
    <tr>
      <th>111</th>
      <td>2021</td>
      <td>1.11</td>
    </tr>
    <tr>
      <th>112</th>
      <td>2022</td>
      <td>-0.11</td>
    </tr>
    <tr>
      <th>113</th>
      <td>2023</td>
      <td>0.87</td>
    </tr>
  </tbody>
</table>
<p>114 rows × 2 columns</p>
</div>




```python
#convert to celcius
na_avg_temp_df["Temp_C"] = (na_avg_temp_df["Temp"] - 32) * 5 / 9
na_avg_temp_df

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Temp</th>
      <th>Temp_C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1910</td>
      <td>-17.583333</td>
      <td>-27.546296</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1911</td>
      <td>-18.322222</td>
      <td>-27.956790</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1912</td>
      <td>-17.933333</td>
      <td>-27.740741</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1913</td>
      <td>-17.794444</td>
      <td>-27.663580</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1914</td>
      <td>-18.322222</td>
      <td>-27.956790</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>109</th>
      <td>2019</td>
      <td>-17.077778</td>
      <td>-27.265432</td>
    </tr>
    <tr>
      <th>110</th>
      <td>2020</td>
      <td>-17.572222</td>
      <td>-27.540123</td>
    </tr>
    <tr>
      <th>111</th>
      <td>2021</td>
      <td>-17.161111</td>
      <td>-27.311728</td>
    </tr>
    <tr>
      <th>112</th>
      <td>2022</td>
      <td>-17.838889</td>
      <td>-27.688272</td>
    </tr>
    <tr>
      <th>113</th>
      <td>2023</td>
      <td>-17.294444</td>
      <td>-27.385802</td>
    </tr>
  </tbody>
</table>
<p>114 rows × 3 columns</p>
</div>




```python
sns.set(font_scale=1.25, style = 'ticks')
na_avg_temp_df.plot(
    x='Date', y='Temp_C', title= "North America Temp Over Time",
    ylabel = "Temperature($^\circ$C)", xlabel = "Date", color = "magenta", figsize = (16, 6), legend = False)

```




    <Axes: title={'center': 'North America Temp Over Time'}, xlabel='Date', ylabel='Temperature($^\\circ$C)'>




    
![png](get_started_with_open_reproducible_science_files/get_started_with_open_reproducible_science_29_1.png)
    



```python
# downloaded data with pandas
na_avg_temp_df = pd.read_csv(na_avg_temp, header=4, 
                        names=['Date', 'Temp'])
na_avg_temp_df

```
