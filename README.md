![image](https://media.licdn.com/dms/image/v2/D4D12AQEFDU4XuJP11w/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1698229402254?e=2147483647&v=beta&t=7mnB7C9BMj6bXQwypYXIwFoQuZ5vItSRLZ0Ox9qvMKA)

# <a name="introduction">Exploratory Data Analysis on Spotify 2023 Dataset</a>

<p align="justify">In this deliverable, an exploratory data analysis (EDA) is performed on a dataset containing information about popular tracks on Most Streamed Spotify Songs 2023. This task aims to analyze, visualize, and interpret the data to extract meaningful insights.</p>
<br>

  
## Table of Contents
1. [Introduction](#introduction)<br>
2. [Exploratory Data Analysis (EDA)](#EDA)<br>
3. [Problem Set](#problems)<br>
4. [Solutions](#solutions)<br>
    - [Overview of Dataset](#1)
    - [Basic Descriptive Statistics](#2)
    - [Top Performers](#3)
    - [Temporal Trends](#4)
    - [Genre and Music Characteristics](#5)
    - [Platform Popularity](#6)
    - [Advanced Analysis](#7)
5. [Author](#pogi)

<br>
  
## <a name="EDA">What is Exploratory Data Analysis?</a>

<p align="justify"><a href="https://www.example.com](https://www.ibm.com/topics/exploratory-data-analysis">Exploratory data analysis (EDA)</a> is used by data scientists to analyze and investigate data sets and summarize their main characteristics, often employing data visualization methods.<br><br>EDA helps determine how best to manipulate data sources to get the answers you need, making it easier for data scientists to discover patterns, spot anomalies, test a hypothesis, or check assumptions.<br><br>EDA is primarily used to see what data can reveal beyond the formal modeling or hypothesis testing task and provides a provides a better understanding of data set variables and the relationships between them. It can also help determine if the statistical techniques you are considering for data analysis are appropriate. Originally developed by American mathematician John Tukey in the 1970s, EDA techniques continue to be a widely used method in the data discovery process today.</p>
<br>
<br>
 
## <a name="problems">Find the following:</a>
<br>
<pre>

<b>1. Overview of Dataset</b>
    - How many rows and columns does the dataset contain?
    - What are the data types of each column? Are there any missing values?

<b>2. Basic Descriptive Statistics</b>
    - What are the mean, median, and standard deviation of the streams column?
    - What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?

<b>3. Top Performers</b>
    - Which track has the highest number of streams? Display the top 5 most streamed tracks.
    - Who are the top 5 most frequent artists based on the number of tracks in the dataset?

<b>4. Temporal Trends</b>
    - Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year.
    - Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases?

<b>5. Genre and Music Characteristics</b>
    - Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most?
    - Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?

<b>6. Platform Popularity</b>
    - How do the numbers of tracks in spotify_playlists, spotify_charts, and apple_playlists compare? Which platform seems to favor the most popular tracks?

<b>7. Advanced Analysis</b>
    - Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)?
    - Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts.

</pre>

<br>
<br>

## <a name="solutions">How can we perform it?</a>

<div style="background-color: black;"><span style="color:white"><h3 align="center">Prerequisites</h3></div></span>
<br>

  
**Step 1:** Access and Download the "spotify-2023.csv" from the link bellow:<br>

link: https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023/data

<br>
<div align="center"><img src="https://github.com/user-attachments/assets/80ee276e-0bf2-4e63-8fe4-9e7b914d1d46" width="600"></div><br>
<br>

**Step 2:** Open Jupyter Notebook and create new ".ipynb" file

<br>
<div align="center"><img src="https://github.com/user-attachments/assets/e59a6e9a-3c0d-4f59-86ab-64603b494884" width="600"></div><br>
<br>

**Step 3:** Import necessary Python libraries

```python
# import the necessary libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

<br>
<div align="center"><img src="https://github.com/user-attachments/assets/a48e1f85-d7da-43ff-a71c-a2fd106e16aa" width="600"></div><br>

**Step 4:** Access "spotify-2023.csv" using Pandas
```python
# Access "spotify-2023.csv" using Pandas
dataset = pd.read_csv('spotify-2023.csv', encoding='latin-1')
dataset
```

<br>
<div align="center"><img src="https://github.com/user-attachments/assets/1bde783c-80c6-4a3f-a0aa-d740df4d3e5a" width="600"></div>


<br>


---
<div style="background-color: black;"><span style="color:white">
<h3 align="center"><a name="1">Solutions</a></h3>
</div></span>
<br>

**1. Overview of Dataset**
<br>


How many rows and columns does the dataset contain?<br>

```python
# Use "shape" function to get quantity of rows and columns
num_rows, num_cols = dataset.shape

rows_columns = {'Rows': num_rows,
                'Columns': num_cols}
pd.DataFrame(rows_columns, index=['Quantity'], columns=['Rows', 'Columns'])
```
<br>

What are the data types of each column? Are there any missing values?<br>
  
```python
# Use "dtypes" function to get data types of each column
datatypes = pd.DataFrame(dataset.dtypes)
datatypes.columns = ['Data Type']
datatypes.index.name = 'Columns'
datatypes 
```
<br>
<br>

<a name="2">

**2. Basic Descriptive Statistics**</a>
<br>

What are the mean, median, and standard deviation of the streams column?<br>
```python
# Access the specific column "streams" and convert to numeric
stream = pd.to_numeric(dataset["streams"],errors="coerce")


# Use the function "mean()", "median()", and "std()"
print('\033[1mStreams\033[0m')
print('*'*20)
print("\033[1mMean: \033[0m", stream.mean())
print("\033[1mMedian: \033[0m", stream.median())
print("\033[1mStandard Deviation: \033[0m", stream.std())

```
<br>

What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?<br>
```python
#Access the specific column "artist_count" and convert to numeric
artist = pd.to_numeric(dataset['artist_count'],errors="coerce")


#Use the function "mean()", "median()", and "std()"
print('\033[1mReleased Year\033[0m')
print('*'*20)
print("\033[1mMean: \033[0m", artist.mean())
print("\033[1mMedian: \033[0m", artist.median())
print("\033[1mStandard Deviation: \033[0m", artist.std())
```
<br>

```python
# Access the specific column "released_year" and convert to numeric
year = pd.to_numeric(dataset['released_year'],errors="coerce")


# Use the function "mean()", "median()", and "std()"
print('\033[1mArtist Count\033[0m')
print('*'*20)
print("\033[1mMean: \033[0m", year.mean())
print("\033[1mMedian: \033[0m", year.median())
print("\033[1mStandard Deviation: \033[0m", year.std())
```
<br>

```python
# Count the number of tracks per released year
tracks_counts_by_year = dataset.groupby('released_year')['artist_count'].count()

# Plot the results
plt.figure(figsize=(20, 5))
tracks_counts_by_year.plot(kind='bar')
plt.xlabel('Released Year')
plt.ylabel('Number of Tracks')
plt.title('Number of Tracks Released Per Year')
plt.grid(axis='y', linestyle='--')
plt.show()
```
<br>

```python
# Count the number of tracks per artist count
track_counts_by_artist_count = dataset.groupby('artist_count')['released_year'].count()

# Create the bar plot
plt.figure(figsize=(20, 5))
track_counts_by_artist_count.plot(kind='bar')
plt.xlabel('Artist Count')
plt.ylabel('Number of Tracks')
plt.title('Number of Tracks by Artist Count')
plt.xticks(rotation=360)
plt.show()
```


<br>
<br>

<a name="3">

**3. Top Performers**</a>

<br>

Which track has the highest number of streams? Display the top 5 most streamed tracks.<br>
```python
# Access the specific column "streams" and convert to numeric
dataset["streams"] = pd.to_numeric(dataset["streams"],errors="coerce")

# Sort by streams from lowest to highest then drop null values
top5_tracks = dataset.sort_values(by='streams').dropna(subset='streams')

# Get the top 5 using "tail()" then sort by streams from highest to lowest
top5_tracks = top5_tracks.tail().sort_values(by='streams', ascending=False)
top5_tracks
```
<br>

```python
# print the top 5 most streamed tracks
i=1
print()
print('\033[1mHere are the top 5 most streamed tracks: \033[0m')
for values in top5_tracks['track_name']:
    print("  ",i,". ", values)
    i = i+1
print()
```
<br>

Who are the top 5 most frequent artists based on the number of tracks in the dataset?<br>
```python
# Separate the group of artists into individuals then count the number of occurrences
most_frequent_artists = dataset["artist(s)_name"].str.split(', ').explode('artist(s)_name').value_counts()

# Get the top 5 frequent artists then "reset_index()"
most_frequent_artists = most_frequent_artists.head(5).reset_index()
most_frequent_artists.index += 1

# rename columns
most_frequent_artists.columns = ['Artist Name', 'Number of Tracks']
most_frequent_artists

```

<br>
<br>

<a name="4">

**4. Temporal Trends**</a>
<br>

Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year.<br>

```python
# Count the number of tracks per released year
track_trends = dataset.groupby('released_year')['artist_count'].count()

# Plot the results
plt.figure(figsize=(20, 5))
track_trends.plot(kind='bar')
plt.xlabel('Release Year')
plt.ylabel('Number of Tracks')
plt.title('Number of Tracks Released Per Year')
plt.grid(axis='y', linestyle='--')
plt.show()
```
<br>

Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases?<br>
```python
# Count the number of tracks per released month
track_counts_by_month = dataset.groupby('released_month')['track_name'].count().sort_index()

# Plot the results
plt.figure(figsize=(20,5))
track_counts_by_month.plot(kind='bar')
plt.xlabel('Release Month')
plt.ylabel('Number of Tracks')
plt.title('Number of Tracks Released Per Year')
plt.grid(axis='y', linestyle='--')
plt.xticks(ticks=range(12), labels=['Jan', 'Feb', 'March', 'April', 'May', 'June', 'July', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec'], rotation = 90)
plt.show()
```
<br>

<br>
<br>

<a name="5">

**5. Genre and Music Characteristics**</a>
<br>

Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most?<br>
```python
data = dataset[['streams','bpm', 'danceability_%', 'energy_%']]

# Calculate the correlation matrix
corr_matrix = data.corr()

# Print the correlation between streams and included musical attributes
print(corr_matrix['streams'].sort_values(ascending=False))
```
<br>

Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?<br>
```python
df = dataset[['danceability_%', 'energy_%']]

# Calculate the correlation matrix
corr_matrix = df.corr()

# Print the correlation between danceability_% and energy_%
print(corr_matrix['danceability_%'].sort_values(ascending=False))
```
<br>

```python
df = dataset[['valence_%','acousticness_%']]

# Calculate the correlation matrix
corr_matrix = df.corr()

# Print the correlation between valence_% and acousticness_%
print(corr_matrix['valence_%'].sort_values(ascending=False))
```
<br>

```python
# Get the correlation of streams including all the musical attributes
correlation_matrix = dataset[['streams','bpm', 'danceability_%', 'energy_%','valence_%','acousticness_%']].corr()  

# Plot the heatmap  
plt.figure(figsize=(8, 6))  
sns.heatmap(correlation_matrix, annot=True, fmt=".2f", cmap='coolwarm', square=True)  
plt.title('Summary using Correlation Heatmap')  
plt.show()  
```
<br>

```python
# Set the figure size  
plt.figure(figsize=(20, 4))  
plt.title('Summary using Regression Plots', pad=25, color='blue', fontweight='bold') 

# Regression Plot for BPM vs Streams  
plt.subplot(1, 5, 1)  
sns.regplot(x='bpm', y='streams', data=dataset)  
plt.title('Streams vs BPM')  
plt.xlabel('BPM')  
plt.ylabel('Streams')  

# Regression Plot for Danceability vs Streams  
plt.subplot(1, 5, 2)  
sns.regplot(x='danceability_%', y='streams', data=dataset)  
plt.title('Streams vs Danceability (%)')  
plt.xlabel('Danceability (%)')  
plt.ylabel('Streams')  

# Regression Plot for Energy vs Streams  
plt.subplot(1, 5, 3)  
sns.regplot(x='energy_%', y='streams', data=dataset)  
plt.title('Streams vs Energy (%)')  
plt.xlabel('Energy (%)')  
plt.ylabel('Streams')  

# Regression Plot for Energy vs Danceability
plt.subplot(1, 5, 4)  
sns.regplot(x='energy_%', y='streams', data=dataset)  
plt.title('Danceability (%) vs Energy (%)')  
plt.xlabel('Energy (%)')  
plt.ylabel('Danceability (%)') 

# Regression Plot for acousticness and valence
plt.subplot(1, 5, 5)  
sns.regplot(x='energy_%', y='streams', data=dataset)  
plt.title('valence (%) vs acousticness (%)')  
plt.xlabel('acousticness  (%)')  
plt.ylabel('valence (%)') 

plt.tight_layout()  
plt.show()  

```
<br>


<br>
<br>

<a name="6">

**6. Platform Popularity**</a>
<br>

How do the numbers of tracks in spotify_playlists, spotify_charts, and apple_playlists compare?<br>
```python
# Create a dictionary for the 3 given platforms
# Sum up all the values included in each platforms
b = {'spotify_playlists' : [dataset['in_spotify_playlists'].sum()],
'spotify_charts' : [dataset['in_spotify_charts'].sum()],
'apple_playlists compare': [dataset['in_apple_playlists'].sum()]}

# Display as a DataFrame
pop_platform = pd.DataFrame(b)
pop_platform.index = ['Number of Tracks']   
pop_platform
```
<br>

Which platform seems to favor the most popular tracks?<br>
```python

# Plot the results
pop_platform.plot(kind='bar')
plt.xlabel('Release Year')
plt.ylabel('Number of Tracks')
plt.title('Number of Tracks Released Per Year')
plt.grid(axis='y', linestyle='--')
plt.xticks(rotation=0)
plt.show()
```

<br>
<br>

<a name="7">

**7. Advanced Analysis**</a>
<br>

Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)?<br>
```python
# Getting the Average Streams per key and mode
grouped_df = dataset.groupby(['key', 'mode'])['streams'].mean().reset_index()  

# Plotting  
plt.figure(figsize=(10, 6))  
sns.barplot(data=grouped_df, x='key', y='streams', hue='mode')  

# Adding titles and labels  
plt.title("Average Streams by Key and Mode")  
plt.xlabel("Key and Mode")  
plt.ylabel("Average Streams")  
plt.legend(title='Mode')  
plt.tight_layout()  
plt.show()  
```
<br>

Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts.<br>
```python
# Separate the group of artists into individuals
exploded_artist = dataset["artist(s)_name"].str.split(', ').explode('artist(s)_name')

# Define the platforms to consider into a list
platforms = ['in_apple_playlists', 'in_apple_charts', 'in_deezer_playlists', 
             'in_deezer_charts', 'in_shazam_charts', 'in_spotify_playlists', 
             'in_spotify_charts']

# Convert each column platforms into numeric
dataset['in_apple_playlists'] = pd.to_numeric(dataset['in_apple_playlists'],errors="coerce")
dataset['in_apple_charts'] = pd.to_numeric(dataset['in_apple_charts'],errors="coerce")
dataset['in_deezer_playlists'] = pd.to_numeric(dataset['in_deezer_playlists'],errors="coerce")
dataset['in_deezer_charts'] = pd.to_numeric(dataset['in_deezer_charts'],errors="coerce")
dataset['in_shazam_charts'] = pd.to_numeric(dataset['in_shazam_charts'],errors="coerce")
dataset['in_spotify_playlists'] = pd.to_numeric(dataset['in_spotify_playlists'],errors="coerce")
dataset['in_spotify_charts'] = pd.to_numeric(dataset['in_spotify_charts'],errors="coerce")

# Sum up the values of each platforms for every individual artist
artist_frequency = dataset.groupby(exploded_artist)[platforms].sum()

# Create another column which sum up all the values of each platform for every individual artist
artist_frequency['Total Frequency'] = artist_frequency.sum(axis=1)

# Sort the artists by highest to lowest and only diplay the top 10
top_frequent_artists = artist_frequency.sort_values(by='Total Frequency', ascending=False).head(10)
top_frequent_artists

```
<br>

```python
# Plot the results
plt.figure(figsize=(12, 6))
plt.barh(top_frequent_artists.index, top_frequent_artists['Total Frequency'])
plt.xlabel('Total Frequency')
plt.ylabel('Artists')
plt.title('Top 10 Most Frequent Artists')
plt.grid(axis='x', linestyle='--')
plt.gca().invert_yaxis()  # Invert y-axis to show top artists at the top
plt.show()
```

<br>
<br>

## <a name="pogi">Author</a>
Name: John Clark D. Honrado<br>
Section: 2ECE-A

<br>


