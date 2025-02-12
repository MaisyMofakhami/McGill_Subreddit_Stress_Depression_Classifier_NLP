# McGill Subreddit Stress & Depression Classifier (NLP)

## 📌 Project Overview

Mental health issues among students are a growing concern, particularly in high-stress academic environments like McGill University. One in five postsecondary students struggles with their mental health. Reddit serves as a valuable platform for students to express their struggles anonymously, making it a rich data source for understanding mental health trends.

This project leverages **Natural Language Processing (NLP)** and **Machine Learning (ML)** techniques to classify Reddit posts related to stress and depression, providing insights into student well-being.

## 📊 Data Sources Overview

Our dataset includes two primary sources of Reddit posts:

- **Training Data:** Two datasets sourced from **Kaggle**:
  - Depression-related posts (7,732 rows)
  - Stress detection posts from social media (5,557 rows)
- **Testing Data:** Scraped from **r/McGill** using **BeautifulSoup**, containing **2,800 rows**.

This combination allows us to train models on diverse mental health discussions while testing on student-specific conversations.

**Potential Bias:** The model may be biased due to training on general Reddit posts rather than university-specific discussions, which may impact its ability to generalize to McGill-related stressors.

---

## 🛠️ Methodology: NLP & Machine Learning Pipeline
![image](https://github.com/user-attachments/assets/7e91caad-1ed9-45c7-8b04-37004923fb00)


### **1. Data Collection & Preprocessing**

- Scraped Reddit posts from McGill-related subreddits.
- Cleaned and tokenized text (lowercasing, punctuation removal, stopword filtering).
- Applied **TF-IDF** and **Word2Vec** embeddings to convert text into numerical representations.

### **2. Text Classification Models**

- **Logistic Regression:** Used as a base model.
- **Support Vector Machines (SVM):** Applied for improved classification accuracy.
- **Random Forest**
- **Adaboost**

### **3. Model Performance & Evaluation**

- **Accuracy & Recall:** Key metrics to ensure accurate stress and depression detection.
- **Cross-validation & Hyperparameter Tuning:** Used GridSearchCV to optimize model performance.
- **Feature Importance Analysis:** Examined key terms contributing to classification decisions.
- The **Word2Vec** method produced results that were closer to sentiment analysis in terms of the proportion of messages labeled as 1 and the ratio of false positives.

---

## 📊 Findings & Insights

Our model's performance on the labeled datasets was strong. Using **TF-IDF** and **SVM**, we achieved **90% test accuracy**. With **Word2Vec** and **Random Forest**, we obtained **83% accuracy** on the test split. However, when comparing model outputs with sentiment analysis and manually checking classifications, we found that **although Word2Vec had lower accuracy, it captured context better, and its labels appeared more logical**.

By applying our classifier to McGill subreddit posts, we uncovered meaningful insights:

- **High prevalence of stress-related discussions**, particularly during exam periods.
- ![image](https://github.com/user-attachments/assets/bc0170db-edbc-4abe-9c99-325007c0d03f)


- Using **LDA (Latent Dirichlet Allocation)** topic modeling analysis to uncover common themes in student discussions regarding stress and depression, we uncovered three main groups:
1. **Academic Stress**: Students frequently discuss exams, courses, and academic workload, with emotional terms like "feel" and "much" indicating stress.
2. **Seeking Guidance & Reassurance**: Many students express uncertainty and emotional burden, seeking help, validation, or shared experiences.
3. **Need for Social Connection**: There is a noticeable demand for friendship and emotional support, highlighting the role of community in coping with stress.
We also realized that there is an overlap in discussions. The coherence score suggests that these concerns are interconnected rather than strictly distinct topics.
![image](https://github.com/user-attachments/assets/3966a1d2-b01f-45df-abfa-1da5e47f8ee0)


Our work highlights how **NLP-driven classifiers** can help analyze student mental health trends, potentially guiding universities to offer better support systems.

---

## 🚀 Technologies Used

- **NLP:** TF-IDF, Word2Vec
- **Machine Learning:** Logistic Regression, SVM, Random Forest, Adaboost
- **Libraries & Tools:** Scikit-Learn, Pandas, Matplotlib

---

## 💡 Future Work

- Expand the dataset with more university subreddits for broader analysis.
- Improve classification by addressing dataset bias and incorporating additional linguistic features.
- Use Topic Modeling to cluster the McGill dataset based on the themes of the posts (course-related, facilities, sports, etc.) and filter out unrelated topics (e.g., students asking for directions on campus) to focus more on posts related to student well-being.

---

## 🔗 Kaggle Datasets:

[Stress Detection from Social Media Articles](https://www.kaggle.com/datasets/mexwell/stress-detection-from-social-media-articles)

[Depression Reddit Dataset (Cleaned)](https://www.kaggle.com/datasets/infamouscoder/depression-reddit-cleaned)

📢 **Contributions are welcome!** Let's work towards better mental health insights using AI! 💙

