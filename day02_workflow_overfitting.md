# Day 2: ML Workflow, Data Splitting, and Overfitting

## 1. The Professional ML Workflow
*The Mentor Reality: Textbooks say Data → Model → Prediction. Production says Problem → Data → Cleaning → Feature Engineering → Model → Evaluation → Deployment.*

| Phase | What You Actually Do | Real-World Example (Churn Prediction) |
|-------|----------------------|---------------------------------------|
| **1. Problem Definition** | Translate a business pain point into a measurable ML objective. | "We lose 15% of users monthly. Let's predict *who* will leave next month." |
| **2. Data Collection** | Pull data via SQL, APIs, or CSVs. Check for grain and leakage. | Querying the `users`, `subscriptions`, and `activity_logs` tables. |
| **3. EDA & Preprocessing** | Find missing values, handle outliers, fix data types. (The 80% rule). | Converting `signup_date` to days active. Imputing missing `income`. |
| **4. Feature Engineering** | Create new variables that make the signal stronger for the model. | Creating `login_frequency_last_7_days` instead of just `total_logins`. |
| **5. Model Training** | Feed data to algorithms (Trees, Regression) to learn patterns. | Training a Random Forest classifier on 80% of the historical data. |
| **6. Evaluation** | Test on unseen data. Check metrics (Accuracy, Precision, Recall). | Checking if the model catches churners without flagging loyal users. |
| **7. Deployment** | Wrap the model in an API or dashboard for stakeholders to use. | Deploying to Streamlit so Sales can upload a CSV and get risk scores. |

## 2. Training vs. Test Data (The "Time Machine")
*The Mentor Test: If you train and test on the same data, you are giving the model an open-book test on questions it has already memorized. We split data to simulate the future.*

| Dataset | Purpose | Analogy | What Happens If You Skip It? |
|---------|---------|---------|------------------------------|
| **Training Set** (e.g., 80%) | The data the model *learns* the patterns from. | Studying with past years' exam papers. | N/A (You need this to build the model). |
| **Validation Set** (e.g., 10%) | Used *during* training to tune hyperparameters (e.g., tree depth). | Taking a practice quiz to see if your study method works. | **Overfitting to the test set.** You'll pick a model that only works by luck. |
| **Test Set** (e.g., 10%) | The final, locked-away data used *only once* at the very end. | The actual final exam. You've never seen these questions before. | **False confidence.** You won't know if your model actually generalizes to new users. |

> 🚨 **Mentor Pro-Tip (Data Leakage):** Never let information from the future leak into your training data. If you are predicting if a user will churn in *December*, you cannot use "December customer support calls" as a feature. That data didn't exist when you needed to make the prediction.

## 3. Overfitting Intuition (Memorization vs. Learning)
*The Mentor Test: Overfitting is the #1 reason junior data scientists fail technical interviews. It happens when your model memorizes the noise instead of learning the signal.*

| State | Training Error | Test Error | What is happening? | The Technical Terms |
|-------|----------------|------------|--------------------|---------------------|
| **Underfitting** | High | High | The model is too simple. It didn't even learn the training data well. | **High Bias** |
| **Good Fit** | Low | Low (Slightly higher than train) | The model learned the true underlying patterns and generalizes well to new data. | **Balanced** |
| **Overfitting** | Very Low (Near 0) | High | The model memorized the exact training points, including random noise/outliers. | **High Variance** |

**The "Student" Analogy for Interviews:**
*   **Underfitting:** The student didn't study at all and fails both the practice test and the real exam.
*   **Good Fit:** The student learns the core concepts, aces the practice test, and aces the real exam.
*   **Overfitting:** The student memorizes the exact answers to the practice test (A, C, B, D) without understanding the math. They get 100% on the practice test, but fail the real exam because the questions are slightly different.