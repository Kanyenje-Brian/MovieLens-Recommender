# **Movie Recommendation System**

This project aims to build a personalized movie recommendation system using the **MovieLens dataset**. It combines **collaborative filtering** and **content-based filtering** to produce movie recommendations for users. The system is designed to handle both regular users and new users with little or no rating history.

----

## **Problem Statement** 

Users on the StreamTime Films platform often struggle to discover content that matches their preferences due to the vast number of available options. With thousands of movies to choose from, users are often overwhelmed and find it difficult to locate movies that match their interests, especially since most don't scroll deeply or explore the site extensively. This results in user-frustration, decision fatigue and in some cases platform abandonment. 

As a result, StreamTime Films faces a critical challenge in retaining users and maintaining long-term engagement, which directly impacts business sustainability. 

---

## **Project Goal**

The goal of this project is to develop a personalized movie recommendation system that suggests relevant movies to users based on their preferences in order to improve user satisfaction and engagement.

---

## **Project Objectives**

1. Identify the most popular movies based on metrics like number of ratings and average rating
2. Investigate how users rate movies 
3. Developing and evaluating advanced recommender models (e.g., collaborative filtering, matrix factorization, or hybrid methods).
4. Explaining recommendation results, using example user profiles and insights derived from the model.

---

## **Dataset Summary**

- Dataset: [`ml-latest-small`](https://grouplens.org/datasets/movielens/) 
- 100,836 ratings | 610 users | 9,742 movies  
- Files used:
  - `movies.csv` – movie titles + genres
  - `ratings.csv` – user-movie ratings
  - `tags.csv` – user-added tags for describing movies

---
## **Exploratory Data Analysis (EDA)**
Before building the recommendation models, we performed extensive EDA to understand the dataset better. Key insights included:
### - ***Distribution of movie ratings***
<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f0676eec-4ca0-4596-907f-4196da26979a" />

Many users tend to give positive ratings with the peak being around 4.0 and the mean around 3.5. shows us we have good positive feedback to learn from 

### - ***Distribution of Number of Ratings per Movie***
<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/22c025e8-c174-4fed-b755-ddcb88a082c8" />

Most users have only rated a small number of movies, while a few users rate very many. This clearly shows the cold-start user challenge – many users don't have enough history for standard recommendations<img


### - ***Distribution of Number of Ratings per Movie***

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/37a9efad-63df-4ce7-9f85-07ac10017518" />

This histogram shows that most movies in our dataset have been rated by a very small number of users. This pattern confirms that we have a significant cold-start item problem.

## **Modeling Approach**

 Recommendation strategies that were implemented include:

- **Collaborative Filtering (CF)**: Using neighborhood-based methods (KNN Basic, KNNWithMeans) and matrix factorization (SVD) to capture latent patterns in user-item ratings.
- **Content-Based Filtering (CBF)**: Using TF-IDF vectorization of genres and tags to recommend similar movies.
- **Hybrid Approach**: A weighted and a switching mechanism that combines collaborative and content-based filtering.

Models were evaluated using **RMSE** on a held-out test set and through cross-validation.


## **Results**

We used RMSE (Root Mean Squared Error) to compare model performance.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/17519a30-21a5-4bfb-95d3-618ea55355f2" />


The **SVD model** yielded the best results among the collaborative filtering models, and the hybrid approaches leverage its strengths.


## **Business Recommendations**

Utilize the SVD Model's Accuracy to power Personalized
Recommendations of movies to specific users  
Rating Predictions: 
<img width="629" height="118" alt="image" src="https://github.com/user-attachments/assets/b2396f40-ccfb-4174-b8f6-a2b300e519dc" />

Implement a weighted hybrid model to combine the
strengths of collaborative filtering and content-based 
filtering, improving recommendation diversity and accuracy. 
<img width="636" height="118" alt="image" src="https://github.com/user-attachments/assets/b0934f7d-016c-4d06-91cb-a670fb55359c" />


Leverage the model insights to surface highly rated but under-watched movies and push them to relevant users increases exposure for lesser-known content
<img width="1602" height="49" alt="image" src="https://github.com/user-attachments/assets/a6afb42d-7bc6-4122-bcb7-21f6be4b8ceb" />

Invest in encouraging users to contribute more high-quality tags which will help reduce noise and improve content discoverability for niche titles.
<img width="2301" height="74" alt="image" src="https://github.com/user-attachments/assets/630eb7fb-4b60-4403-a1d3-f8b319caf157" />

1. ***Cold-Start Strategy for New Users***  
   Use content-based filtering to recommend movies to new users based on selected genres or movie preferences during onboarding. This mitigates cold-start issues and improves first-time user satisfaction.

2. ***Hybrid Approach for Balanced Recommendations***  
   Implement a weighted or switching hybrid model to combine the strengths of collaborative filtering and content-based filtering, improving recommendation diversity and accuracy.

3. ***Promote Hidden Gems to Maximize Catalog Value***  
   Leverage the model insights to surface highly rated but under-watched movies and push them to relevant users. This increases exposure for lesser-known content and improves catalog utilization across the platform.

4. ***Improve Tag Quality to Enhance Discovery***
Encourage more user tagging and curate high-quality, relevant tags to enrich movie metadata. This can improve the discoverability of niche content and increase recommendation precision, especially for long-tail or lesser-known titles.


## **Conclusion**
This project demonstrates how a hybrid recommender system can address the content discovery problem on a platform like StreamTimeNow. By combining collaborative filtering and content-based techniques, we’re able to provide high-quality, personalized movie recommendations even for new users.



## **For More Information**
Please review our full analysis in our [Jupyter Notebook](https://github.com/Kanyenje-Brian/MovieLens-Recommender/blob/master/notebook.ipynb) or our [presentation](https://github.com/Kanyenje-Brian/MovieLens-Recommender/blob/master/Presentation.pdf).

For any additional questions, please contact:

- **Brian Kanyenje** – [bkanyenje@gmail.com](https://mail.google.com/mail/?view=cm&fs=1&to=bkanyenje@gmail.com)  
- **Calistus Mwonga** – [calistusmwonga@gmail.com](https://mail.google.com/mail/?view=cm&fs=1&to=calistusmwonga@gmail.com)  
- **Samwel Kipkemboi** – [samkemboi201@gmail.com](https://mail.google.com/mail/?view=cm&fs=1&to=samkemboi201@gmail.com)  
- **Kelvin Mutua** – [kelvinmutua787@gmail.com](https://mail.google.com/mail/?view=cm&fs=1&to=kelvinmutua787@gmail.com)
- **Hannah Nyambura** – [anngachuhipg1@gmail.com](https://mail.google.com/mail/?view=cm&fs=1&to=anngachuhipg1@gmail.com)  


## **Project Structure**
```
├── app/
│   ├── api/
│   │   ├── main.py
│   ├── app/
│   │   ├── streamlit.py
│   ├── models/
│   │   ├── cosine_sim.pkl
│   │   ├── keras_model.h5
│   │   ├── svd_model.pkl
├── data/
│   ├── README.txt
│   ├── links.csv
│   ├── movies.csv
│   ├── ratings.csv
│   └── tags.csv
├── .gitignore
├── Presentation.pdf
├── Presentation.pptx
├── README.md
├── data_utils.py
└── notebook.ipynb

```


