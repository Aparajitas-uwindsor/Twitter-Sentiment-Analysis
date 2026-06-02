# 🐦 Twitter Sentiment Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0%2B-orange)
![NLTK](https://img.shields.io/badge/NLTK-3.7%2B-green)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-yellow)
![Dataset](https://img.shields.io/badge/Dataset-Sentiment140-lightgrey)

A machine learning project that classifies tweets as **positive** or **negative** using Natural Language Processing (NLP) and Logistic Regression. Built on the Sentiment140 dataset with 1.6 million labeled tweets.

---

## 📊 Results

| Metric | Score |
|--------|-------|
| Accuracy | ~80% |
| Dataset Size | 1.6M tweets |
| Training Sample | 200,000 tweets |
| Model | Logistic Regression + TF-IDF |

---

## 📁 Project Structure

```
twitter-sentiment-analysis/
│
├── sentiment_analysis.ipynb    ← Main Google Colab notebook
├── sentiment_model.pkl         ← Trained Logistic Regression model
├── tfidf_vectorizer.pkl        ← Fitted TF-IDF vectorizer
├── plots/
│   ├── tweet_length.png        ← Tweet length distribution
│   ├── wordcloud_negative.png  ← Negative tweets word cloud
│   └── wordcloud_positive.png  ← Positive tweets word cloud
└── README.md
```

---

## 🔍 Dataset

**Sentiment140** — 1.6 million tweets automatically labeled using emoticons:
- `0` = Negative sentiment
- `1` = Positive sentiment (originally `4`, remapped)

📥 Download: [Kaggle — Sentiment140](https://www.kaggle.com/datasets/kazanova/sentiment140)

> **Note:** The dataset file is not included in this repo due to size. Download it from Kaggle and place it in the root directory before running the notebook.

---

## 🧠 Methodology

### 1. Data Cleaning
- Lowercasing
- Removing URLs, @mentions, punctuation, and numbers
- Stopword removal
- Lemmatization using NLTK WordNetLemmatizer

### 2. Exploratory Data Analysis (EDA)
- Class distribution (perfectly balanced: 800K positive, 800K negative)
- Tweet length distribution by sentiment
- Top 20 most frequent words per class
- Word clouds for positive and negative tweets

### 3. Feature Engineering
- **TF-IDF Vectorizer** with unigrams + bigrams (`ngram_range=(1,2)`)
- `max_features=50,000`

### 4. Model Training
- **Logistic Regression** (`C=1.0`, `solver='lbfgs'`, `max_iter=1000`)
- 80/20 train-test split with stratification

### 5. Evaluation
- Accuracy score
- Precision, Recall, F1-score (classification report)
- Confusion matrix

---

## 📈 Visualizations

### Sentiment Distribution
Perfectly balanced dataset — 800,000 tweets per class.

### Tweet Length Distribution
![Tweet Length](plots/tweet_length.png)

### Word Clouds
| Negative Tweets | Positive Tweets |
|----------------|----------------|
| ![Negative](plots/wordcloud_negative.png) | ![Positive](plots/wordcloud_positive.png) |

---

## 🚀 How to Run

### Option 1: Google Colab (Recommended)
1. Open `sentiment_analysis.ipynb` in [Google Colab](https://colab.research.google.com/)
2. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/kazanova/sentiment140)
3. Upload the CSV when prompted in the notebook
4. Run all cells in order

### Option 2: Local
```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/twitter-sentiment-analysis.git
cd twitter-sentiment-analysis

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn nltk wordcloud

# Launch Jupyter
jupyter notebook sentiment_analysis.ipynb
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.8+ | Core language |
| Pandas & NumPy | Data manipulation |
| NLTK | Text preprocessing |
| Scikit-learn | TF-IDF & Logistic Regression |
| Matplotlib & Seaborn | Visualizations |
| WordCloud | Word cloud generation |
| Google Colab | Development environment |
| Pickle | Model serialization |

---

## 💡 Example Predictions

```python
predict_sentiment("I love this product, it changed my life!")
# 🟢 Positive — 91.3% confidence

predict_sentiment("This is the worst experience I've ever had.")
# 🔴 Negative — 94.7% confidence
```

---

## 🔮 Future Improvements

- [ ] Try BERT or DistilBERT for higher accuracy
- [ ] Add neutral sentiment class
- [ ] Deploy as a web app using Streamlit or Flask
- [ ] Add real-time Twitter API integration
- [ ] Experiment with LSTM / GRU deep learning models

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙋 Author

**Your Name**
- LinkedIn: [linkedin.com/in/yourprofile](https://linkedin.com/in/yourprofile)
- GitHub: [github.com/yourusername](https://github.com/yourusername)

---

⭐ If you found this project helpful, please give it a star!
