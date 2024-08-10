# Spotify-EDA

# 📊 Exploratory Data Analysis (EDA) on the Spotify Dataset 🎹

**Python for Data Science Mini Project**

By,
* **Abhijith S D**
* **Arvind C R**
* **Ayyasamy S**
* **Gurumurthy Kalyanpur Viswanathaiah**
* **Manjunath**

# 📋 Dataset Overview and Preprocessing 🔍

## 📈 Data Setup linking kaggle and google colab
### 📰 Read the kaggle API token to interact with your kaggle account
### ⚙️ Series of commands to set-up for download
### ♿ giving rw access (if 401-nathorized)
### ✅ Sanity check if able to access kaggle
### ⬇️ Download data command
### 🤐 Unzip Dataset

## 🗂️ Loading the Dataset 📥
We began by loading the Spotify dataset using `pandas`. This dataset contains information about various tracks, including metrics from different streaming platforms.

## 🏷️ Initial Data Examination 👀
We reviewed the last few rows of the dataset to understand its structure and content. The dataset consists of 29 columns and 4599 rows with diverse types of information such as track names, artists, release dates, and various streaming metrics.

## 📜 Column Names 📑
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


## 📉 Missing Values Analysis ⚠️
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

## 🔄 Removing Duplicates 🔥
We checked for duplicate entries in the dataset:
* 🚨 **Duplicates Found**: 2
* 🗑️ **Duplicates Removed**: The dataset now contains 4598 rows.

## 📊 Descriptive Statistics 📈
We computed descriptive statistics for the following columns:
* ⭐ **Track Score**: Mean of 41.85, Standard Deviation of 38.55
* 🎼 **Spotify Popularity**: Mean of 63.50, Standard Deviation of 16.19
* 🍏 **Apple Music Playlist Count**: Mean of 54.61, Standard Deviation of 71.63
* 🎶 **Deezer Playlist Count**: Mean of 32.32, Standard Deviation of 54.29
* 📚 **Amazon Playlist Count**: Mean of 25.35, Standard Deviation of 25.99
* 🎶 **TIDAL Popularity**: This column was dropped due to all missing values.
* 🔞 **Explicit Track**: 0 or 1 indicating the explicit nature of the track.

## 🗑️ Dropping Unnecessary Columns 🧹
The **TIDAL Popularity** column was dropped from the dataset:
* ❌ **Reason**: This column contained only missing values and did not contribute to our analysis.
