# Spotify-EDA

# 📊 Exploratory Data Analysis (EDA) on the Spotify Dataset 🎹

**Python for Data Science Mini Project**

To understand the dataset, uncover underlying patterns, and generate insights that could guide further analysis or decision-making.
    - Select a dataset
    - Perform data cleaning 
    - Pre-processing, 
    - Conduct exploratory data analysis (EDA)
    - Present the findings

By,
* **Abhijith S D**
* **Arvind C R**
* **Ayyasamy S**
* **Gurumurthy Kalyanpur Viswanathaiah**
* **Manjunath**


# 📋 Dataset Overview and Preprocessing 🔍

## Requirements
    - Google Colab
    - Kaggle account (to access datasets)
    - Anacoda
    - Jupyter lab

## Getting Started

Follow these steps to use the notebook:

### 📈 Data Setup linking kaggle and google colab
   - Go to your Kaggle account settings and create a new API token. This will download a file named `kaggle.json`.
   - In your Colab notebook, use the following code to upload the `kaggle.json` file:
### 📰 Read the kaggle API token to interact with your kaggle account
    from google.colab import files
    files.upload()
    !pip install -q kaggle
### ⚙️ Series of commands to set-up for download    
### ♿ giving rw access (if 401-nathorized)
### ✅ Sanity check if able to access kaggle
    !mkdir -p ~/.kaggle
    !cp kaggle.json ~/.kaggle/
    !chmod 600 ~/.kaggle/kaggle.json
### ⬇️ Download data command
    !kaggle datasets list
    !kaggle datasets download -d nelgiriyewithana/most-streamed-spotify-songs-2024
### 🤐 Unzip Dataset
    !unzip most-streamed-spotify-songs-2024.zip

## 📈 (OR) Data Setup linking kaggle and google colab
    1. Place the dataset csv file inside the unzipped folder "EDA_Spotify_Group3" as a sibling to this ReadME file.
    2. Opne the Jupyter lab and import the EDA_Spotify_Group3 directory.
    3. Run the "EDA_Spotify_Group3.ipynb" file.


# Features: Key features of the Spotify Data set.

### 🗂️ Loading the Dataset 📥
We began by loading the Spotify dataset using `pandas`. This dataset contains information about various tracks, including metrics from different streaming platforms.

### 🏷️ Initial Data Examination 👀
We reviewed the last few rows of the dataset to understand its structure and content. The dataset consists of 29 columns and 4599 rows with diverse types of information such as track names, artists, release dates, and various streaming metrics.

### 📜 Column Names 📑
The dataset includes columns like:
* 🎵 **Track**
* 📀 **Album Name**
* 🎤 **Artist**
* 📅 **Release Date**
* 🔢 **ISRC**
* 📈 **All Time Rank**
* ⭐ **Track Score**
* 🎧 **Spotify Streams**
* 📋 **Spotify Playlist Count**
* 🌐 **Spotify Playlist Reach**
* 🎼 **Spotify Popularity**
* 📹 **YouTube Views**
* 👍 **YouTube Likes**
* 🎥 **TikTok Posts**
* 💖 **TikTok Likes**
* 👁️ **TikTok Views**
* 🎵 **YouTube Playlist Reach**
* 🍏 **Apple Music Playlist Count**
* 📻 **AirPlay Spins**
* 📡 **SiriusXM Spins**
* 🎶 **Deezer Playlist Count**
* 🌍 **Deezer Playlist Reach**
* 📚 **Amazon Playlist Count**
* 🎙️ **Pandora Streams**
* 📻 **Pandora Track Stations**
* 🔊 **Soundcloud Streams**
* 🕵️ **Shazam Counts**
* 🎶 **TIDAL Popularity**
* 🔞 **Explicit Track**

### 📉 Missing Values Analysis ⚠️
We identified columns with missing values:
* 🎤 **Artist**: 5 missing values
* 🎧 **Spotify Streams**: 113 missing values
* 📋 **Spotify Playlist Count**: 70 missing values
* 🌐 **Spotify Playlist Reach**: 72 missing values
* 🎼 **Spotify Popularity**: 804 missing values
* 📹 **YouTube Views**: 308 missing values
* 👍 **YouTube Likes**: 315 missing values
* 🎥 **TikTok Posts**: 1173 missing values
* 💖 **TikTok Likes**: 980 missing values
* 👁️ **TikTok Views**: 981 missing values
* 🎵 **YouTube Playlist Reach**: 1009 missing values
* 🍏 **Apple Music Playlist Count**: 561 missing values
* 📻 **AirPlay Spins**: 498 missing values
* 📡 **SiriusXM Spins**: 2123 missing values
* 🎶 **Deezer Playlist Count**: 921 missing values
* 🌍 **Deezer Playlist Reach**: 928 missing values
* 📚 **Amazon Playlist Count**: 1055 missing values
* 🎙️ **Pandora Streams**: 1106 missing values
* 📻 **Pandora Track Stations**: 1268 missing values
* 🔊 **Soundcloud Streams**: 3333 missing values
* 🕵️ **Shazam Counts**: 577 missing values
* 🎶 **TIDAL Popularity**: 4600 missing values

### 🗑️ Dropping Unnecessary Columns 🧹
The **TIDAL Popularity** column was dropped from the dataset:
* ❌ **Reason**: This column contained only missing values and did not contribute to our analysis.
*❌ **Reason for ISRC**: This column is not helpful for any real analysis.
*❌ **Reason for TIDAL Popularity**: This column contained only missing values and did not contribute to our analysis.

### Changing data type of columns as per the data analysis
    - Release Date column has been changed to datetime
    - Removed comma "," and strange char "ý" in the string cells of dataframe
    - Updated blank string columns to UNKWN
    - Converted all numerical columns to corresponding numerical types

### Numeric columns analysis
    - Spotify_Popularity has 2 tails
    - All Other columns are positively skewed
    - TikTok_Views, Soundcloud_Streams and Shazam_Counts have lot of outliers

### 🔄 Cleaning data and filling NA values 🔥
Checke for NaN entries in the dataset and fill with 0/mean/median if numerical or unknown if categorical
*🚨 **replaced NaN with 0 for "Soundcloud Streams" as almost 75%+ had null values
*🚨 **replaced NaN with 0 for "Shazam Counts" as almost most values were outliers
*🚨 **replaced NaN with 0 for "TikTok Views" as almost most values were outliers
*🚨 **replaced NaN with median valus for all other columns as all columns had outliers and hence used median instead of mean
*🚨 **replaced Explicit Track with True for "1" and False for "0"

### 🔄 Removing Duplicates 🔥
We checked for duplicate entries in the dataset:
* 🚨 **Duplicates Found**: 2
* 🗑️ **Duplicates Removed**: The dataset now contains 4598 rows.

### Removing Logical Duplicates
    Here we notice that same tracks have been used in multiple albums. But upon further investigation and looking at the dataset it seems that some Tracks were uploaded multiples times but are not necessarily duplicates.

### Shorteting track names with more than 30 characters
    Reduced cell data of track column to less than 30 characters if the value is crossing 30 characters.s

### ➕ Adding Columns for further analysis¶
    Like, 'month' and 'year' are 2 columns helps in analysis and visualization, based on realease date


## 📊 Descriptive Statistics 📈
We computed descriptive statistics for the following columns:
* ⭐ **Track Score**: Mean of 41.85, Standard Deviation of 38.55
* 🎼 **Spotify Popularity**: Mean of 63.50, Standard Deviation of 16.19
* 🍏 **Apple Music Playlist Count**: Mean of 54.61, Standard Deviation of 71.63
* 🎶 **Deezer Playlist Count**: Mean of 32.32, Standard Deviation of 54.29
* 📚 **Amazon Playlist Count**: Mean of 25.35, Standard Deviation of 25.99
* 🎶 **TIDAL Popularity**: This column was dropped due to all missing values.
* 🔞 **Explicit Track**: 0 or 1 indicating the explicit nature of the track.


## DATA SET Analysis and Visualization

### Correlation Analysis using heatmap
    A correlation heatmap is a graphical tool that displays the correlation between multiple variables as a color-coded matrix
    As Years progressed, the Spotify and pandora streams have reduced showing how streaming in music domain have reduced slowly.

### Monthly releases analysis
    - Total number of songs released per month
    - Average songs per month
    - Number of songs released each year
    - Number of songs released in last 5 years
    
### Stream Analysis
    - By Spotify Streams, Spotify playlist count, Spotify Popularity, and Explicit contents- While Spotify popularity, Spotify Streams, and Spotify playlist counts are positively correlated.
    - How does being on a playlist affect a song's plays?
    - Do songs tend to do the same across different platforms?

### Track analysis
    - 1 Average Track Score for each Year
    - 2 The best Track Score for each year
    - 3 The worst Track Score for each year
    - 4 Number of Tracks every Year
    - 5 Interest in Explicit Music
    - 6 Change in Explicitness throughout the Years

### Spotify Analysis
    - Top 20 Ranked Songs on Spotify
    - Top 20 Streamed Songs on Spotify

### Spotify Analysis
    - Top 20 most viewed videos in youtube
    - Top 20 most liked videos in youtube

### TikTok Analysis
    - Top 20 most used on tiktok

### Shazam Analysis
    - Top 20 most searched songs on Shazam

### Most Popular Artist
    - Top 20 most popular artist from youtube views
    - Top 20 most popular artist from spotify and youtube combined
    - We can even choose an particular artist to analyze during the execution


# Acknowledgement :
    Thanks to the python's opensource libraries for data analysis and visualization and are:
    - Pandas
        Purpose: Data manipulation and analysis.
        Usage: To handle and process data, including reading and cleaning the dataset.
    - Seaborn
        Purpose: Statistical data visualization.
        Usage: To create informative and attractive visualizations such as histograms, pair plots, and violin plots.
    - Matplotlib
        Purpose: Plotting and visualization.
        Usage: For creating static, animated, and interactive visualizations, including histograms and plots with customized styles.
    - Plotly
        Purpose: Interactive data visualization.
        Usage: To create interactive plots and visualizations that allow for deeper exploration of the data.
    Also special thanks to third party libraries:
    - chardet
        Purpose: Determine the encodings of files
        Usage: To understand the charset of the kaggle dataset pypi-url
    - missingno
        Purpose: Missing data visualization module for Python.
        Usage: To visualize the null values easily git-url

# Contact Information
    - Abhijith S D  - (+91)-97314 14414 - abhinomega135@gmail.com
    - Arvind C R    - (+91)-94454 53443 - arvindcr4@gmail.com
    - Ayyasamy S    - (+91)-98860 01482 - samysubu12@gmail.com
    - Gurumurthy    - (+91)-99000 61441 - gurumurthy.kv@gmail.com
    - Manjunath     - (+91)-96118 84272 - manju.crz@gmail.com
