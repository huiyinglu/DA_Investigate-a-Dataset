# DA_Investigate-a-Dataset
Investigate TMDB-Movie Dataset

The dataset we are go to investigate is the TMDb Movie Data (cleaned from the original data on Kaggle). This dataset contains information about 10,000 movies collected from The Movie Database (TMDb), including user ratings and revenue. Some notes on the dataset:
- Certain columns, like 'cast', 'genres', 'director', and 'production companies' contain multiple values separated by pipe (|) characters.   Since we are going to use 'genres' column for our research question, we will transform that column (split, merge, etc) to different cells   for better processing.
- The final two columns ending with “_adj” show the budget and revenue of the associated movie in terms of 2010 dollars, acounting for       inflation over time.
- There are missing values in some of the columns - which need to be cleaned.
- The datatypes/formats of some of the columns (like 'release_date') need to be converted to another datatypes for easier processing.
- Some columns (like revenue, budget, revenue_adj, budget_adj) have value 0, we will need to take care of these.

We will clean the data in following sequence:
1. Remove duplicate rows.
2. Drop the unnecessary columns.
3. Fill in missing values in a column if there are quite a few missing values - in 'director' and 'production_companies' columns, we will      fill in 'Unknown' string.
4. Drop some rows with missing values if there are not too many rows - we will drop the missing rows which does not have 'genres' values.
5. Convert the datatypes - change the release_date column to date_time format.
6. Replace the value 0 with the mean value of the column in certain columns (like revenue, budget, revenue_adj, and budget_adj)
7. Split sample to multiple rows if the 'genres' column contains multiple values.

We like to investigate the dataset and find the answers to the following 2 research questions:
1. Which features (especially numerical features) in the dataset might have impact on revenue of the movie?
2. Which genres are most popular? Which genres make the most money?

We will build our report around analysis of the following
Dependent variable: revenue_adj, popularity
Independent variable: genre, release_year, budget_adj, runtime.
