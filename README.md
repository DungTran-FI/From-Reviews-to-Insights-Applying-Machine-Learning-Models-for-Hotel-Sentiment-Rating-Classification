# From Reviews to Insights: Applying Machine Learning Models for Sentiment Rating Classification

## 1. Business Problem & Motivation
Civil services companies, such as hotels, rely heavily on customer reviews to understand their service's strengths and weaknesses. Positive reviews help attract more customers and boost profits. However, manually analyzing each review is labor-intensive and inefficient for capturing the overall picture of customer satisfaction.

This project aims to automate the classification of customer reviews using machine learning, sorting them into positive or negative categories. By automating this process, hotels can:
- Eliminate manual biases
- Receive instant feedback
- Quickly identify customer attitudes and take action

Ultimately, this approach can increase customer satisfaction and improve profits.

**Dataset**:  
The data is sourced from a large open TripAdvisor review dataset available on Kaggle, consisting of 878,561 rows and 19 attributes. To reduce processing time, a subset of the data will be used. The dataset includes two files:

- offerings.csv (hotel information)
- reviews.csv (customer reviews)

These two files will be merged using the shared column offering_ID, representing the hotel ID.

Also, web scraping was used to gather additional information about the hotels, including details such as the hotel class, number of amenities, price range, distance to the nearest metro station, and the number of nearby attractions, etc. among other features.

The final dataset (after data collection & merging) has **239,1666 rows and 16 attributes.**


## 2. Aim of Study
The goal is to build a robust model that classifies customer ratings as:
- **High**: ratings of 4 or 5 stars
- **Negative**: ratings below 4 stars

Automating this classification helps reduce manual review efforts, enabling hotels to:
- Address negative reviews promptly to reduce customer churn
- Engage satisfied customers with personalized offers

This automation will improve marketing strategies, customer retention, and overall decision-making for businesses.

## 3. Methods

### Data Preprocessing
To prepare the customer reviews for analysis, the following preprocessing steps will be applied:
- **Text cleaning**: Remove irrelevant symbols, stopwords, and punctuation.
- **Tokenization**: Break text into meaningful tokens.
- **Lemmatization**: Standardize words to their base form.

### Exploratory Data Analysis (EDA)
The following techniques will be used to uncover key themes and sentiment trends:
- **Word Clouds**: To highlight key words in guest reviews.
- **Rating Distribution**: To visualize the distribution of customer ratings.
- **Correlation Analysis**: To identify relationships between review content and ratings.

As this is a condensed version of the report, exploratory data analysis (EDA) has been excluded.

### Predictive Modeling
Several models will be implemented to automate sentiment classification:
- Logistic Regression
- Decision Tree
- Random Forest
- Näive Bayes
- Ensemble methods: Bagging, Boosting (AdaBoost, XGBoost)

These models will classify reviews as Low or High. Additionally, hybrid models will combine sentiment classification with numerical features (e.g., review length, hotel information) to predict customer ratings more accurately.

## 4. Expected Outcomes
The project demonstrated that the **ability to predict True Negatives (actual low ratings)** significantly improves with balanced data across all models. Among the resampling methods evaluated:

- SMOTE emerged as the best method, achieving an F1-score of 0.83 and a precision of 0.81, effectively capturing low ratings while minimizing false positives.
- Random Under-Sampling yielded the highest recall of 0.90, successfully identifying more low ratings, although it sacrificed some precision.

Correctly predicting low ratings is crucial for the company, enabling timely interventions to enhance customer retention. Given our focus on accurately identifying True Negatives, we selected **XGBoost with the Random Under-Sampling method (accuracy: 0.8974)** as our final model. Additionally, the hyperparameter tuning implementation of **Bayesian Search** improved the model's performance, **increasing the True Negative rate from 0.9007 to 0.9016** compared to the model with default hyperparameters.

## Disclaimer
This project was developed as a group assignment for the "30E03000 - Data Science for Business I" course at Aalto University. While the design, implementation, and analysis aspects of the project were collaboratively completed by the team, each individual contributed to specific parts of the project.

The work presented here includes contributions from all team members, and the final deliverables reflect a collective effort. When showcasing this project in a personal portfolio, it is important to acknowledge that it was a group effort. The skills demonstrated and the results achieved are representative of the collaborative work undertaken by the team as a whole.
