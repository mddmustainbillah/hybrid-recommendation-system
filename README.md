# 🎵 Hybrid Recommendation System: Personalized Music That Drives Retention and Revenue

## 🚀 Project Overview

In the world of streaming platforms, *personalization is king*. Whether it's Spotify, YouTube, or Netflix—users return because the system understands their taste. I wanted to explore that idea deeper, so I built the **Hybrid Recommendation System**—an intelligent engine that delivers personalized music recommendations by combining **collaborative** and **content-based filtering** using **Spotify song data**.

This system isn’t just about suggesting the next song—it’s about increasing **user engagement**, **boosting retention**, and **converting free users into paid subscribers** through data-driven personalization.

---

## 🎯 Objectives & Goals

This project was built with a clear business case in mind:

- 🎧 Increase **user engagement** by providing more relevant and diverse song recommendations.
- ⏱ Boost **retention** so users spend more time on the platform.
- 💳 Convert **free users to subscribers**, reducing churn and increasing revenue.
- 📈 Improve **Click-Through Rate (CTR)** on recommendations—an indicator of user satisfaction.
- 💰 Maximize **ad revenue** by keeping free users engaged longer.

---

## 🧩 Why This Project Was Challenging

Like any real-world system, this one had its share of complexities:

- **Massive Dataset**: With **1 million users** and **30K unique songs**, the collaborative matrix grew to **~2.9 billion rows**.
- **Cold Start Problem**: Not all songs were played by users—so collaborative filtering wouldn’t work for them.
- **Performance Bottlenecks**: Streamlit was slow to load large datasets on the first run.
- **Dynamic Weighting**: I needed a hybrid system that **adjusts based on user type**—old users get more collaborative signals, while new users rely more on content-based filtering.

---

## ⚙️ System Architecture (End-to-End Flow)

Here's how the system works:

User Input → Streamlit Interface → Hybrid Engine → Personalized Song List


### Components:

- **Frontend**: Built with 🧼 **Streamlit**, providing a smooth, interactive UI.
- **Backend Logic**:
  - **Collaborative Filtering**: Item-based, using user-song play history.
  - **Content-Based Filtering**: Based on audio features, genre, etc.
  - **Hybrid Recommender**: A **weighted mix** based on user behavior.
- **Dynamic Control**: Users can choose their preference — more collaborative, more content-based, or balanced.
- **Cold Start Handling**: If a song hasn’t been played, the system defaults to content-based recommendations.

---

## 📊 Data Engineering & Processing

Here’s where the technical story gets really interesting.

- 📥 Two Kaggle datasets:
  - `User Listening History.csv` — 1M+ rows of user-song interactions.
  - `Music Info.csv` — 50K songs, including audio features.
- 🔗 Joined and filtered to 30K active songs.
- 💥 After matrix multiplication, data ballooned to **~60 GB**.
- ✂️ **Reduced to ~30 MB** using:
  - **SciPy’s sparse matrices** to drop ~99% zero values.
  - **Dask** for chunked processing and parallelization.
- ⏩ Streamlit **caches processed data**, solving the initial loading issue.

> **Result**: A lightning-fast system that went from **60GB to 30MB** and can make real-time recommendations using optimized pipelines.

---

## 🎁 Features

✅ Personalized song recommendations  
✅ Hybrid filtering: collaborative + content-based  
✅ Dynamic weight slider  
✅ Cold-start support  
✅ Streamlit UI  
✅ Optimized for large-scale data  
✅ Memory-efficient using sparse matrices  
✅ Business-impact focus

---

## 📈 Business Impact

This system was designed not just to "work", but to **deliver measurable results**:

| Metric                         | Before Optimization | After Optimization |
|-------------------------------|---------------------|--------------------|
| Data Volume                   | ~60 GB              | ~30 MB             |
| Memory Footprint              | Very High           | ⚡ 99.95% Reduction |
| Recommendation Latency       | High on Load        | ⚡ Near Instant     |
| Cold Start Problem            | Exists              | ✅ Handled          |
| Dynamic User Personalization | No                  | ✅ Yes              |
| CTR Potential                 | Baseline            | 📈 15–30% Expected Boost |
| Churn Rate                    | Moderate            | 📉 Decrease Expected |
| Subscription Conversion      | Flat                | 📈 Projected Growth |

By delivering **better recommendations**, we **retain more users**, **convert more subscribers**, and **earn more ad revenue** from free users who stay longer.

---

## 👥 Who Is This For?

This system is useful for:

- 🎧 **Music Streaming Platforms** (e.g., Spotify clones, local music services)
- 📺 **Media Streaming Services** (Netflix, YouTube-like platforms)
- 🛍 **E-commerce Product Recommendations**
- 🧠 **ML Engineers & Data Scientists** learning large-scale recommender systems
- 📊 **Product Managers** focusing on user retention and monetization

---

## 🧰 Tech Stack

- **Python**
- **Pandas**, **NumPy**
- **Dask** – For parallel data processing
- **SciPy** – For sparse matrix compression
- **Streamlit** – For UI and user control
- **Scikit-learn** – For similarity measures

---

## 🛠 Installation & Usage

```bash
# Clone the repo
git clone https://github.com/your-username/hybrid-recommendation-system.git
cd hybrid-recommendation-system

# Create virtual environment
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run app.py
```