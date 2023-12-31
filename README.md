# Visual Narratives and Hidden Languages: A Machine Learning Approach to Movie Poster Analysis

## Table of Contents
- [About](#about)
    - [Information About The Datasets](#information-about-the-datasets)
- [Prerequisites](#prerequisites)
- [Results](#results)
- [Future Steps](#future-steps)
- [Contact](#contact)

## About
This project leverages machine learning techniques such as Convolutional Neural Networks (ResNet50) and Natural Language Processing (BERTopic) to:

1. **Explore the Connection**: We delve into the intriguing interplay between a movie's poster and its narrative content. Our goal is to discern patterns and insights on how a movie's storyline is visually depicted in its poster.

2. **Analyze the Impact**: The study further evaluates the influence of this visual-to-narrative alignment on a movie's success. This success is quantified using IMDB scores, allowing us to gauge how effectively the posters' conveyance of the plot reflects in audience reception.

The project is divided into three Jupyter notebooks that should be run in the following order:

1. `Predicting Genres.ipynb`: Downloads poster images and uses the RESNET50 model to predict genres from the posters.
2. `NLP Processing.ipynb`: Performs NLP cleaning on the plot descriptions and creates a BERTopic model.
3. `Predicting Plot Topics.ipynb`: Uses the RESNET50 model to predict the topics generated by the BERTopic model.

### Information About The Datasets
This project makes use of two main datasets sourced from Kaggle. Details about the specific sections used from each dataset are provided below:

1. **[Movie Genre from its Poster: Kaggle](https://www.kaggle.com/datasets/neha1703/movie-genre-from-its-poster)**
   - `Year`: Used for Exploratory Data Analysis (EDA)
   - `Movie Posters`: Images were processed and fed into the ResNet50 model to predict movie genres.
   - `IMDB Score`: Utilized as a Key Performance Indicator (KPI) to evaluate our hypothesis that the narrative content represented in movie posters influences the performance of the movie.
   - `Genres`: Each movie has 1 to 3 genres listed from a list of 28 possible genres. These were also used in the genre prediction model. 
   
   The data for this dataset was originally sourced from the Internet Movie Database (IMDB).

2. **[Wikipedia Movie Plots: Kaggle](https://www.kaggle.com/datasets/jrobischon/wikipedia-movie-plots)**
   - `Plot`: This dataset provides movie plot descriptions scraped from Wikipedia. We merged this data into our main dataframe by matching the 'Movie Title' and 'Year' fields across both datasets. This enriched our main dataset with a detailed narrative content description for each movie.

By combining these datasets, we achieved a robust dataset that incorporates both visual (poster) and textual (plot and genre) elements of each movie, paving the way for a comprehensive analysis of our hypothesis.


## Prerequisites
To run this project, the following packages need to be installed. You can install them using pip:

```sh
pip install numpy pandas seaborn matplotlib tensorflow keras scikit-learn torch torchvision ipython bertopic umap-learn hdbscan nltk sentence_transformers scipy wordcloud

```
## Results
This project yielded several interesting findings:

1. The machine learning model used to predict movie genres based on their posters found a correlation with IMDB review scores. Posters that the model correctly predicted had a higher average IMDB review score of 6.55, compared to those incorrectly predicted which had an average score of 6.37.

2. When using the BERTopic model to generate and predict plot topics based on movie posters, we observed an even higher average IMDB review score of 6.56 for correctly predicted movies.

A t-test was performed to compare the IMDB scores of the correctly predicted and incorrectly predicted groups in the plot-based movie poster analysis. 
The t-statistic was 1.5565164618584724 and the p-value was 0.11982128879652984.

The relatively high p-value indicates that we fail to reject the null hypothesis that there is no significant difference in IMDB scores between movies for which the model correctly predicted the plot and those for which it did not. This suggests that while the model showed some predictive ability, there is room for improvement in its accuracy.

## Getting Started
Clone this repository to your local machine.
Set up a virtual environment and install the required dependencies using pip.
Run the notebooks in the order specified above. Note: Make sure to update the file paths in the notebooks if necessary.

## Future Steps
The current project presents an intriguing opportunity for extension to other forms of visual media. Potential areas to explore include TV show posters, book covers, video game covers, and album artwork. Analyzing these additional sources could reveal universal trends in visual-to-narrative representation, providing valuable insights for advertising and publicity strategies. Moreover, it could enhance our data-driven understanding of audience perception across a range of media.

The insights obtained from the p-values suggest room for improvement in the predictive accuracy of the current model. Future iterations of this project might focus on improving the model's capability to distinguish between movies based on their narrative content as depicted in posters. This could involve tuning the existing model, exploring different machine learning algorithms, or employing additional features. The ultimate goal is to decrease the p-value, indicating a more significant difference between the IMDB scores of correctly and incorrectly predicted movies, thereby demonstrating the model's efficacy.

## Contact
For any queries, please feel free to reach out to me at sergiy12422@gmail.com or connect with me on [LinkedIn](https://www.linkedin.com/in/sergiy-chepiga/).
