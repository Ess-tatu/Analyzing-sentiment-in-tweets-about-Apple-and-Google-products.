# Analyzing Sentiment in Tweets About Apple and Google Products

## Introduction

This repository contains a sentiment analysis project focused on tweets mentioning Apple and Google products. Using machine learning (ML) and natural language processing (NLP), models are built to classify tweets into Positive, Negative, or Neutral categories.

## Business Understanding

This project applies Natural Language Processing (NLP) and machine learning techniques to analyze the sentiment of tweets related to Apple and Google products. By classifying user tweets as **Positive**, **Negative**, or **Neutral**, this project provides insights into how these users feel about the tech giants' products.

## Problem Statement

Companies like Apple and Google receive an overwhelming volume of public feedback daily via social media platforms. Assessing such data manually and at a global scale can be impractical and overwhelming, hence the need to automate sentiment classification and analysis models.

## 🎯Objectives

1.  Build a sentiment classification model for tweets.
2.  Implement Natural Language Processing (NLP) steps to preprocess text, clean and prepare the data.
3.  Compare the performance of various machine learning models and see which one performs best.
4.  Evaluate model performance using metrics such as accuracy, precision, recall, and F1-score and provide business recommendations.

## Research Questions

- Can tweet text alone provide sufficient information to accurately predict sentiment?
- What words or phrases are most common with positive, negative, or neutral tweets?
- Which classification model performs best for this task?
- What evaluation metrics provide the most meaningful insights for model comparison?

## Limitations

- Tweets are often brief and ambiguous.
- Class imbalance — most tweets carry neutral sentiments.
- There is subjective labeling of sentiment.
- The dataset may not reflect current language trends.

## Dataset Summary

- **Size:** 9,093 tweets, annotated by human raters.
- **Features:** 
  - `tweet_text`
  - `emotion_in_tweet_is_directed_at`
  - `is_there_an_emotion_directed_at_a_brand_or_product`

Sentiment labels are encoded as follows:
- Positive = `1`
- Neutral = `0`
- Negative = `-1`

![image](https://github.com/user-attachments/assets/24afc217-7f21-4a06-87c7-d1b9e399f20f)

## Data Preprocessing

The following preprocessing techniques are applied to the raw tweet data:

- Removal of URLs, mentions, hashtags, numbers, and special characters
- Conversion to lowercase
- Stopword removal and tokenization
- Stemming of words to their root form
- Use of TF-IDF vectorization to transform text into features

## Models Evaluated

### Logistic Regression

- Achieved an accuracy of approximately 70%
- Performed best on neutral tweets
- Was efficient and interpretable, with hyperparameter tuning using GridSearchCV

### Random Forest Classifier

- Achieved similar accuracy (~70%) but showed weaker performance in minority classes.
- While more interpretable, it demonstrated weaker recall in negative sentiment classification.
- It provided feature importance insights and better handling of non-linear relationships

### Neural Network

- Achieved a slightly lower accuracy of 68%
- Tuned using various hyperparameters (layers, dropout, optimizers)
- It demonstrated flexibility and potential for further improvement

## Evaluation Metrics 

1. Classification reports generated for each model

![image](https://github.com/user-attachments/assets/b546aac9-9dfb-4b42-a7f6-3e2824bf693b)

  
2. Confusion matrices plotted for each model

 ![image](https://github.com/user-attachments/assets/85114649-b7e0-4791-93a9-d0477bf58c01)


### Model Performance (Mean F1-Score)

| Model              | Mean CV F1-Score |
|--------------------|------------------|
| Logistic Regression | 0.652    |
| Random Forest       | 0.642    |
| Neural Network      | 0.651    |

Due to class imbalance, F1-Score was emphasized as the primary evaluation metric.

![Models](https://github.com/user-attachments/assets/87277851-f5d2-4577-9b80-8ad44d5c1de0)

## Conclusion

1. Sentiment can be accurately predicted using only the text of tweets, as demonstrated by the strong performance of the models, particularly Logistic Regression and Neural Networks.
2. **Positive** tweets often contain words expressing satisfaction or excitement, **negative** tweets include complaints or frustration, and **neutral** tweets are generally factual and unbiased.
3. **Logistic Regression** performed best overall, followed closely by the Neural Network. Both outperformed the Random Forest model in terms of F1-score.
4. The most effective evaluation metric was the **F1-score**, as it provides a balanced measure of precision and recall, making it ideal for sentiment classification tasks.

## Recommendations

1. **Deploy the Model as a Real-Time Monitoring Tool**
   
- Host the trained model in a cloud environment and integrate it with Twitter’s API to continuously collect and analyze tweets. This allows Apple and Google to track public sentiment in real time.
  
2. **Use Sentiment Trends to Inform Product Strategy**
   
- Regularly analyze sentiment data to identify recurring complaints or praise. This can guide product development teams on areas of improvement or features that users love.
  
3. **Enhance the Model with More Data and Context**
   
- Continuously retrain the model with new tweets and expand to include emojis, hashtags, and user metadata to capture richer sentiment signals.
  
4. **Integrate with Customer Support and PR Teams**
   
- Provide alerts for sudden spikes in negative sentiment so support or communications teams can proactively respond and manage brand reputation.

## 👥 Project Team

This project was collaboratively developed by the following team members:

- Audrey 
- Petronilla  
- George  
- Stella  
- Sylvia  
- Job

Overall, this work bridges technical implementation with business impact, showcasing the practical value of sentiment analysis.
