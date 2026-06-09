# Day 1: Machine Learning Mental Models

## 1. What is Machine Learning?
**Traditional Programming:** You give the computer Rules + Data → it gives you Answers.
**Machine Learning:** You give the computer Answers + Data → it figures out the Rules. 
*In short: ML replaces explicit, hard-coded rules with patterns learned automatically from data.*

## 2. Supervised vs. Unsupervised Learning
*The Mentor Test: Do you have an "Answer Key" (a target variable/label) in your training data?*

| Type | Do you have labels? | Goal | Real-World Example |
|------|---------------------|------|--------------------|
| **Supervised** | ✅ YES. You know the historical outcome. | Predict the future outcome. | Predicting house prices (you have past sale prices). |
| **Unsupervised** | ❌ NO. You only have features, no target. | Find hidden structure or groupings. | Customer segmentation (you don't know the segments yet, you want the data to reveal them). |

## 3. Regression vs. Classification (Supervised Sub-types)
*The Mentor Test: What is the data type of the thing you are trying to predict?*

| Type | What are you predicting? | The "Can I Average It?" Trick | Real-World Example |
|------|--------------------------|-------------------------------|--------------------|
| **Regression** | A **continuous number** (quantity). | ✅ YES. You can average prices, temperatures, or sales. | Predicting Sales ($), Temperature (°C), Age (years). |
| **Classification** | A **discrete category** (label/class). | ❌ NO. You can't average "Cat" and "Dog". | Predicting Churn (Yes/No), Spam (Spam/Ham), Disease (Positive/Negative). |