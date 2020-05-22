# emotionalAI
Natural Language Understanding for Emotion Classification

# Project
The goal of this project is to develop a Natural Language Understanding (NLU) algorithm for classifying the underlying emotion associated with a chat message so that chatbots and other programs can use this information to deliver a better experience to users.

# Background
People have goals that are explicit and implicit. Explicit goals are usually easy to identify because a person can clearly articulate them, like buying groceries, resolving a billing issue, traveling to the beach, updating a software, etc. Implicit goals, on the other hand, are more difficult to identify. These are emotional goals that aren't always articulated even though the achievement of these emotional goals is often more valuable than the explicit goals. Not only does a person want to buy groceries, they also want to feel good about the experience.  If they don't, then they may never return to that grocery store again.

It requires emotional intelligence to accurately recognize emotions. As we all know from customer service interactions, not all people have this level of emotional intelligence. If a program can automate this emotional classification process, then organizations could use this information to dramatically improve a wide variety of service encounters acorss industries.

# Use Case
The specific application of this classification algorithm will be for the NLU pipeline of an emotionally intelligent chatbot.  The algorithm classifies the general emotion associated with the message and then identifies the approproate custom emoji that represents that emotion.  A demo of the chatbot is coming soon.

Proposed NLU Pipeline for Understanding Implicit Goals

# Datasets
My primary dataset is the [DailyDialogue](http://yanran.li/dailydialog) dataset compiled for the International Joint Conference on Natural Language Processing (IJCNLP) in Taipei, Taiwan by Yanran Li, Hui Su, and Xiaoyu Shen, Wenjie Li, Ziqiang Cao, and Shuzi Niu.

This is a very thorough dataset that includes over 13,000 conversations and over 100,000 utterances.  Each conversation has been manually categroized by a topic while each utterance is additionally categorized with an emotion and a statement type.  For the purposes of this model, which I intend to put into the NLU pipeline of a chatbot, I'm only interested in the emotion classification because I won't be asking users to classify their own messages with a topic and an utterance type (although that would be an interesting classification project for the future).  However, I will include the topics and types below so you can see the diversity of utterances provided.
* ***Dialogue: string.  One utterance per row.***
* ***Emotion: int. The emotion associated with the text.***
    * 0: No emotion
    * 1: Anger
    * 2: Disgust
    * 3: Fear
    * 4: Happiness
    * 5: Sadness
    * 6: Surprise
* ***Type: int. The type of utterance.***
    * 1: Inform
    * 2: Question
    * 3: Directive
    * 4: Commissive
* ***Topic: The general topic of the conversation.***
    * 1: Ordinary Life
    * 2: School Life
    * 3: Culture & Education
    * 4: Attitude & Emotion
    * 5: Relationship
    * 6: Tourism
    * 7: Health
    * 8: Work
    * 9: Politics
    * 10: Finance

Although DailyDialog is thorough, it unfortunately has a significant class imbalance between the "no emotion" class and the other emotion classes.  To address this imbalance, I decided to source two additional datasets that I could use to combine with DailyDialog: a set built from the PushShift API for Reddit and an additional set that I personally developed with the specific use case of an emotional chatbot in mind.




# Process & Repository Contents
* ***Cleaning:*** Cleaning the datasets in preparation for modeling.
  * [emotion_ai_cleaning.ipynb](https://github.com/Frankafka/emotionalAI/blob/master/emotion_ai_cleaning.ipynb)
* ***Baselines:**** Baseline modeling with several multi-class machine learning classification models to guide EDA and Feature Engineering.
  * [emotion_ai_baseline_modeling.ipynb](https://github.com/Frankafka/emotionalAI/blob/master/emotion_ai_eda.ipynb)
* ***Exploratory Data Analysis:*** Analysis of the dataset and visualizations to communicate insights. 
  * [emotion_ai_eda.ipynb](https://github.com/Frankafka/emotionalAI/blob/master/emotion_ai_eda.ipynb)
* ***Feature Engineering:*** Engineering of specific features beyound text tokens to improve predictability.
  * [emotion_ai_feature_engineering.ipynb](https://github.com/Frankafka/emotionalAI/blob/master/emotion_ai_feature_engineering.ipynb)
* ***Modeling & Evaluation:*** Modeling using the new features to examine their impact and identify the best model.
  * notebook coming soon
* ***Findings:*** 
  * Emotional AI Presentation PDF
  * Blog Post Coming Soon
  * Pipeline Coming Soon
  * Trained Model Coming Soon
  
# Findings & Next Steps

Based on the initial performance of the baseline models, it's clear there is a significant class imbalance which needs to be addressed before I continue to model.  I plan to address this by undersampling the majority class (no emotion).  Also there are opportunities for engineering features that capture more meaning from utterances and could improve classification performance.
