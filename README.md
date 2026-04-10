# 🍅 PopcornMetrics: Exploratory Analysis of Rotten Tomatoes Movie Ratings

An exploratory data analysis project on the Rotten Tomatoes movie dataset
to uncover insights about critic vs. audience ratings, genre trends, and
movie popularity — designed for a movie review podcast audience.

---

## 📁 Project Structure
PopcornMetrics/
├── analysis.ipynb # Main analysis notebook
└── Rotten Tomatoes Movies.csv # Dataset (from Maven's Data Playground)

---


## 🎯 Objectives

- Explore and clean the Rotten Tomatoes movie dataset
- Identify the highest-rated movies by critics and audiences
- Filter and analyze popular movies (100k+ audience ratings)
- Engineer genre-based features (Animation, Action & Adventure, Comedy)
- Compare critic vs. audience ratings across genres and MPAA ratings
- Visualize relationships between key variables using pair plots

---

## 📊 Dataset

**Source:** Rotten Tomatoes Movies — [Maven's Data Playground](https://mavenanalytics.io)

**Key Columns Used:**

| Column               | Description                            |
|----------------------|----------------------------------------|
| `movie_title`        | Title of the movie                     |
| `rating`             | MPAA rating (G, PG, PG-13, R, NR)     |
| `genre`              | Genre(s) of the movie                  |
| `in_theaters_date`   | Theater release date                   |
| `runtime_in_minutes` | Duration of the movie                  |
| `tomatometer_rating` | Critic score (%)                       |
| `tomatometer_count`  | Number of critic reviews               |
| `audience_rating`    | Audience score (%)                     |
| `audience_count`     | Number of audience ratings             |

---

## 🔍 Analysis Workflow

### 0. Data Loading
- Loaded the full dataset (~16,638 movies)
- Selected relevant columns for analysis

### 1. Exploratory Data Analysis
- Filtered to movies released **2010 or later** → 6,053 movies
- Found highest-rated movies by critics and audience
- Identified that top-rated movies often had very few reviews
- Applied a **popularity filter** (≥ 100,000 audience ratings) → 316 movies
- Analyzed MPAA rating distribution among popular movies
- Computed average audience rating per MPAA rating type

### 2. Feature Engineering
- Created binary genre flags using `np.where` + `str.contains`:
  - `Animation` (1/0)
  - `Action & Adventure` (1/0)
  - `Comedy` (1/0)
- Built a **rating × genre pivot table**
- Compared average critic and audience ratings across genres

### 3. Data Visualization
- Generated **pair plots** using Seaborn for the popular movies dataset
- Uncovered relationships between runtime, ratings, and audience counts

---

## 💡 Key Insights

- **Animation movies** score significantly higher with both critics (~75) and
  audiences (~75) compared to non-animation (~58 / ~65)
- **Comedy movies** tend to score *lower* with critics (~55) vs. non-comedies
  (~62)
- **PG-13** dominates popular movies (160 out of 316)
- Popular blockbusters like *Zootopia*, *Guardians of the Galaxy*, and
  *How to Train Your Dragon* top both critic and audience charts
- Pure tomatometer perfection (100%) is common in low-review-count films,
  making review count an important filter for meaningful rankings

---

## 🛠 Technologies Used

| Tool        | Purpose                               |
|-------------|---------------------------------------|
| Python 3    | Core programming language             |
| Pandas      | Data manipulation and analysis        |
| NumPy       | Numerical operations & feature flags  |
| Seaborn     | Pair plot visualizations              |
| Matplotlib  | Underlying plotting support           |
| Jupyter     | Interactive notebook environment      |

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy seaborn matplotlib jupyter
```

### Run the Notebook
```bash
jupyter notebook analysis.ipynb
```

---

## 📌 Notes

- The analysis focuses on **popular movies** (audience_count ≥ 100,000) to
  avoid bias from films with very few reviews.
- Dates are parsed using `pd.to_datetime` for proper year-based filtering.

---

## 👤 Author

Yusif İmamverdiyev  
Computer Engineering Instructor | AI & Data Science Enthusiast
