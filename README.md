![image](https://media.licdn.com/dms/image/v2/D4D12AQEFDU4XuJP11w/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1698229402254?e=2147483647&v=beta&t=7mnB7C9BMj6bXQwypYXIwFoQuZ5vItSRLZ0Ox9qvMKA)


# Exploratory Data Analysis on Spotify 2023 Dataset

In this deliverable, an exploratory data analysis (EDA) is performed on a dataset containing information about popular tracks on Most Streamed Spotify Songs 2023. This task aims to analyze, visualize, and interpret the data to extract meaningful insights.
<br>
<br>
  
## What is Exploratory Data Analysis?
 
<p class="justified"> 
  [Exploratory data analysis (EDA)](https://www.ibm.com/topics/exploratory-data-analysis) is used by data scientists to analyze and investigate data sets and summarize their main characteristics, often employing data visualization methods.
  
  EDA helps determine how best to manipulate data sources to get the answers you need, making it easier for data scientists to discover patterns, spot anomalies, test a hypothesis, or check assumptions.

  EDA is primarily used to see what data can reveal beyond the formal modeling or hypothesis testing task and provides a provides a better understanding of data set variables and the relationships between them. It can also help determine if the statistical techniques you are considering for data analysis are appropriate. Originally developed by American mathematician John Tukey in the 1970s, EDA techniques continue to be a widely used method in the data discovery process today.
</p>


<br>
<br>
 
## Find the following:
<br>
<pre> 
  
**1. Overview of Dataset<br>
2. Basic Descriptive Statistics<br>
3. Top Performers<br>
4. Temporal Trends<br>
5. Genre and Music Characteristics<br>
6. Platform Popularity<br>
7. Advanced Analysis<br>**

</pre>
<br>
<br>

## How can we perform it?

<h3 align="center">Prerequisites</h3>
<pre>

**Step 1:** Access and Download the "spotify-2023.csv" from the link bellow:<br>
link: https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023/data
![image](https://github.com/user-attachments/assets/d6cb1a80-85be-4cf5-807d-f9cc47542fc9)
<br>

**Step 2:** Open Jupyter Notebook and create new .ipynb file
![image](https://github.com/user-attachments/assets/35b2a80c-4ca6-4d30-94f8-a1039309f70b)
<br>
**Step 3:** Import necessary Python libraries
<br>
</pre>

<hr>
<h3 align="center">Solutions</h3>
<pre>
  
**1. Overview of Dataset**
<br>
How many rows and columns does the dataset contain?<br>
\tThe Dataset consist of 953 rows × 24 columns.<br>
What are the data types of each column? Are there any missing values?<br>

  
<br>
<br>

**2. Basic Descriptive Statistics**
<br>
What are the mean, median, and standard deviation of the streams column?<br>
What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?<br>
<br>
<br>

**3. Top Performers**
<br>
Which track has the highest number of streams? Display the top 5 most streamed tracks.<br>
Who are the top 5 most frequent artists based on the number of tracks in the dataset?<br>
<br>
<br>

**4. Temporal Trends**
<br>
Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year.<br>
Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases?<br>
<br>
<br>

**5. Genre and Music Characteristics**
<br>
Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most?<br>
Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?<br>
<br>
<br>

**6. Platform Popularity**
<br>
How do the numbers of tracks in spotify_playlists, spotify_charts, and apple_playlists compare? Which platform seems to favor the most popular tracks?<br>
<br>
<br>

**7. Advanced Analysis**
<br>
Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)?<br>
Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts.<br>
<br>
<br>

</pre>
