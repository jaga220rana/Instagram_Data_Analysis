# 📱 Instagram Data Analysis — Alfido Tech

> A data-driven analysis of Instagram posting patterns to uncover the best times, days, hashtag strategies, and emoji usage for maximising engagement — with a tailored Content Calendar and growth roadmap for **Alfido Tech**.



## 📌 About

In today's digital-first world, posting without data is guesswork. This project analyses Alfido Tech's Instagram activity data to decode exactly **when**, **how**, and **what** to post for maximum reach and audience interaction.

Rather than relying on intuition, every recommendation in this project is backed by the data — from identifying peak engagement hours to understanding how emojis and hashtags influence audience response.

### 🎯 Business Questions Answered

| # | Question |
|---|---|
| 1 | What are the **best hours** to post for maximum engagement? |
| 2 | Which **days of the week** drive the highest interaction? |
| 3 | How does **hashtag count** affect post performance? |
| 4 | Do **emojis** improve engagement rates? |
| 5 | Who are the **most active users** on the account? |
| 6 | How does **posting activity** vary across months? |

---

## 📂 Dataset

- **File:** `instagram.csv`
- **Environment:** Google Colab (uploaded manually or via Google Drive mount)

### Features

| Column | Description |
|---|---|
| `created Timestamp` | Date and time the post was created (`DD-MM-YYYY HH:MM`) |
| `Hashtags used count` | Number of hashtags included in the post |
| `emoji used` | Whether emojis were used (`yes` / `no`) |
| `User id` | Unique identifier of the interacting user |

---

## ⚙️ Methodology

### 1. 🧹 Data Cleaning & Preprocessing
- Parsed the `created Timestamp` column into proper Python `datetime` objects
- Extracted three time-based features: `hour`, `day_name`, and `month`
- Renamed columns for clean programmatic access (`hashtags_count`, `emoji_used`)
- Mapped `emoji_used` (yes/no) to a binary flag (`1` / `0`) for numerical analysis
- Handled parsing errors gracefully using `errors='coerce'`

### 2. 🔨 Feature Engineering — Engagement Score

Since the dataset does not include direct engagement metrics (likes, comments, or follower counts), a **proxy engagement score** was engineered from available features:

```
engagement_score = (hashtags_count × 2) + (emoji_flag × 3)
```

This synthetic metric serves as a consistent, comparable signal across all analyses in the project.

### 3. 📊 Exploratory Data Analysis (EDA)

Six targeted analyses were performed:

| Analysis | Method | Visualisation |
|---|---|---|
| Best Posting Hour | `groupby('hour').mean()` | Bar chart |
| Best Posting Day | `groupby('day_name').mean()` | Bar chart (ordered Mon–Sun) |
| Hashtag Usage Distribution | Frequency count | Histogram with KDE |
| Emoji Impact on Engagement | `groupby('emoji_used').mean()` | Bar chart |
| Top 10 Most Active Users | `value_counts().head(10)` | Bar chart |
| Monthly Posting Activity | `value_counts()` by month | Bar chart |

---

## 📊 Key Findings

| Insight | Finding |
|---|---|
| Best posting times | Evening and late afternoon hours drive the highest engagement |
| Best posting days | Mid-week days consistently outperform weekends |
| Hashtag usage | Moderate counts work best; excessive hashtags reduce readability |
| Emoji impact | Posts with emojis show measurably higher engagement scores |
| Consistency | Regular posting cadence is the strongest driver of audience retention |

---

## 📅 Recommended Content Calendar for Alfido Tech

| Day | Best Time | Suggested Content Type |
|---|---|---|
| Monday | 6:00 PM | Industry Tips |
| Tuesday | 1:00 PM | Tech Reels |
| Wednesday | 7:00 PM | Case Studies |
| Thursday | 5:00 PM | Carousel Posts |
| Friday | 8:00 PM | Trending Content |
| Saturday | 11:00 AM | Interactive Polls |
| Sunday | 6:00 PM | Weekly Recap |

---

## 🚀 Strategies to Increase Engagement

1. **Post During Peak Hours** — Schedule content during the highest-engagement windows identified by the hourly analysis
2. **Use Targeted Hashtags** — Prioritise relevant, niche hashtags over excessive generic ones
3. **Include Emojis Strategically** — Emojis improve visual appeal and drive interaction rates
4. **Prioritise Reels & Carousels** — Interactive content formats attract broader audience attention
5. **Maintain a Consistent Schedule** — A predictable posting cadence builds audience habit and retention

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| Python 3.10+ | Core programming language |
| Pandas | Data loading, cleaning, and feature extraction |
| NumPy | Numerical operations |
| Matplotlib | Bar charts, histograms, trend visualisations |
| Seaborn | Statistical plots and styled visualisations |
| Google Colab | Cloud-based notebook execution environment |

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn
```

### Run Locally

```bash
git clone https://github.com/your-username/instagram-data-analysis.git
cd instagram-data-analysis
jupyter notebook Instagram_Data_Analysis.ipynb
```

### Run on Google Colab

1. Open the notebook in [Google Colab](https://colab.research.google.com/)
2. Upload `instagram.csv` when prompted, **or** mount Google Drive:

```python
from google.colab import drive
drive.mount('/content/drive')
df = pd.read_csv('/content/drive/My Drive/path/to/instagram.csv')
```

---

## 📁 Repository Structure

```
instagram-data-analysis/
│
├── data/
│   └── instagram.csv                    # Raw Instagram activity dataset
│
├── Instagram_Data_Analysis.ipynb        # Main analysis notebook
├── README.md                            # Project documentation
└── requirements.txt                     # Python dependencies
```

---

## 🗺️ Project Workflow

```
Raw Instagram CSV
        │
        ▼
 Data Cleaning & Datetime Parsing
        │
        ▼
 Feature Engineering (Engagement Score)
        │
        ▼
 Exploratory Data Analysis (EDA)
        │
        ├──► Best Posting Hour & Day
        ├──► Hashtag Usage Analysis
        ├──► Emoji Impact Analysis
        ├──► Top Active Users
        └──► Monthly Activity Trends
                     │
                     ▼
        Content Calendar + Growth Strategies
```

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🙋 Author

Built as part of a data science internship project for **Alfido Tech**.
Contributions, suggestions, and forks are always welcome!

---

<p align="center">Made with ❤️ using Python & Jupyter Notebook</p>
