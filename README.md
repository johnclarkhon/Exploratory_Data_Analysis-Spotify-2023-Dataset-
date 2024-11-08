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
<img src="https://github.com/user-attachments/assets/e59a6e9a-3c0d-4f59-86ab-64603b494884" width="600" align='center'><br>
<br>

**Step 3:** Import necessary Python libraries

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

<br>
<center><img src="https://github.com/user-attachments/assets/a48e1f85-d7da-43ff-a71c-a2fd106e16aa" width="600"></center><br>

**Step 4** Access "spotify-2023.csv" using Pandas

<br>
<center><img src="https://github.com/user-attachments/assets/1bde783c-80c6-4a3f-a0aa-d740df4d3e5a" width="600"></center>





<br>


---
<div style="background-color: black;"><span style="color:white">
<h3 align="center"><a name="1">Solutions</a></h3>
</div></span>
<br>

**1. Overview of Dataset**
<br>

<pre>

How many rows and columns does the dataset contain?


What are the data types of each column? Are there any missing values?
    _The data types of the columns consists of objects and int-64._
  
</pre>
<br>
<br>

<a name="2">

**2. Basic Descriptive Statistics**</a>
<br>
```
What are the mean, median, and standard deviation of the streams column?

What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?
```
<br>
<br>

<a name="3">

**3. Top Performers**</a>

<br>
```
Which track has the highest number of streams? Display the top 5 most streamed tracks.
Who are the top 5 most frequent artists based on the number of tracks in the dataset?
```
<br>
<br>

<a name="4">

**4. Temporal Trends**</a>
<br>
```
Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year.
Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases?
```
<br>
<br>

<a name="5">

**5. Genre and Music Characteristics**</a>
<br>
```
Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most?
Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?
```
<br>
<br>

<a name="6">

**6. Platform Popularity**</a>
<br>
```
How do the numbers of tracks in spotify_playlists, spotify_charts, and apple_playlists compare? Which platform seems to favor the most popular tracks?
```
<br>
<br>

<a name="7">

**7. Advanced Analysis**</a>
<br>
```
Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)?
Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts.
```
<br>
<br>

## <a name="pogi">Author</a>
Name: John Clark D. Honrado<br>
Section: 2ECE-A

<br>


