# **STREAMTIME FILMS RECOMMENDATION SYSTEM**
<img width="2400" height="465" alt="image" src="https://github.com/user-attachments/assets/f20ac682-ca70-47a2-a20f-a00fd8338a0e" />

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

1. Utilize the SVD model's accuracy to power personalized recommendations of movies to specific users.
2. Implement a weighted hybrid model to combine thestrengths of collaborative filtering and content-based filtering, improving recommendation diversity and accuracy. 
3. Leverage the model insights to surface highly rated but under-watched movies and push them to relevant users increases exposure for lesser-known content
4. Invest in encouraging users to contribute more high-quality tags which will help reduce noise and improve content discoverability for niche titles.


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


