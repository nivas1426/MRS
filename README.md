# MRS
In these modern days, many corporate employees experience stress and seek relaxation by watching movies they like. However, they often struggle to find the exact movies they want online. A Movie Recommendation System (MRS) is an ML-based model trained using TF-IDF, designed to recommend movies according to user preferences.

*Dataset used* : The Movies Dataset

*Data Cleaning Overview*: Data cleaning improves the quality and reliability of the dataset. Here's how we addressed common issues:

 1.Handling Missing Values: These can occur due to various reasons such as entry errors or incomplete records. We dropped rows and columns containing NULL values.    
 
 2.Data Type Conversion: Ensuring variables have appropriate data types is important for analysis and modeling. For example, in this model, we converted the data 
   type of the movie ID to a string. 
   
 3.Standardizing Data to the same format: Removing spaces between words,converting all text to lowercase,etc. comes under this category.This brought uniformity and        made comparison task easy.

*Content-Based Filtering Process*:

1.Data Extraction:
We extracted data such as actors, directors, and keywords from various CSV files. Directors' and overviews' data types were converted to strings. Subsequently, genres, cast, overview, and keywords were merged into a single column named 'tags' for efficient data handling.

2.TF-IDF Vectorization:
We applied TF-IDF vectorization to the 'tags' column for content-based filtering.

3.Centroid and Euclidean Distances:
In a multidimensional vector space, we calculated the centroid of the input movies to apply a combined effect based on user preferences. Euclidean distances were used as a similarity measure to compare distances between movies and the centroid.

4.K-Nearest Neighbors (KNN) Technique:
Using the distances calculated, and selecting a suitable value for k (often large to minimize noise), we applied the KNN algorithm to find movies nearest to the user's preferences.
   
   ![KNN](https://github.com/nivas1426/MRS/assets/139680679/2a41221e-fd13-46cb-ac8d-fb74a5e28893)

*Collaborative Filtering Process*:

1.Data Extraction:

We extracted ratings and movie data from CSV files. Movie IDs were mapped to titles using a dictionary, and ratings were converted to strings for processing.
       
   ![image](https://github.com/nivas1426/MRS/assets/139680679/a7748f5e-b31e-4d56-807f-fbedaf034ef4)

2.Applying Cosine Similarity:

A pivot table was created with user IDs, movie IDs, and ratings to analyze the distribution of movie ratings by users. Cosine similarity was applied to ratings to measure similarity between users. This allowed us to identify movies unseen by users that are similar to those highly rated by other users.
        
   ![mrs2](https://github.com/nivas1426/MRS/assets/139680679/e7867342-a522-440d-8c7d-92ed48e30191)

*Recommendation*:

Inputs received via a chat bot trigger various recommendation functions. The output, based on collaborative filtering, is displayed to the user, suggesting movies tailored to their preferences and similarity to other users' ratings.

