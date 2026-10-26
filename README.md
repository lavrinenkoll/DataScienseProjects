# Data Science Projects

A collection of data science micro-projects covering the full pipeline - from web scraping and statistical modelling to clustering, neural-network forecasting, credit-scoring, and geospatial analysis.

| Project | Topic | Methods / tools | Key takeaway |
|---|---|---|---|
| [`web_scraping/`](web_scraping/) | Web scraping & trend analysis | requests, BeautifulSoup, pandas, sklearn (polynomial regression), matplotlib | Parsed e-commerce price history, fitted the best polynomial trend (R²-based search), and generated synthetic data that preserves the original distribution |
| [`anomaly_detection/`](anomaly_detection/) | Anomaly detection & filtering | sliding-window z-score, α-β recursive filter, polynomial regression (LSM) | Injected controlled anomalies into synthetic data, compared removal vs. mean-replacement cleanup, and validated results with extrapolation |
| [`multicriteria_analysis/`](multicriteria_analysis/) | Multi-criteria decision analysis | pandas, OR-Tools (linear programming) | Ranked 10 companies by 19 normalised KPIs through additive integral scoring and solved a constrained optimisation problem |
| [`job_market_pipeline/`](job_market_pipeline/) | Job-market data pipeline | Selenium, BeautifulSoup, deep-translator, Groq LLM (Llama 3.1), WordCloud, OLAP pivot tables | Scraped DOU & LinkedIn vacancies, used an LLM to extract skills/offers from descriptions, compared platforms with word-clouds and 3D OLAP cubes |
| [`clustering/`](clustering/) | Clustering & object identification | KMeans, silhouette score, OpenCV (CLAHE, morphology, contour detection) | Clustered price time-series, segmented images by colour, and built an interactive object-counter with adjustable filters |
| [`lstm_forecasting/`](lstm_forecasting/) | Time-series forecasting (LSTM) | TensorFlow/Keras (stacked LSTM), StandardScaler, matplotlib | Trained multi-layer LSTM on synthetic price data, predicted future values, and evaluated accuracy by comparing forecasts against held-out segments |
| [`exploratory_analysis/`](exploratory_analysis/) | Exploratory data analysis | pandas, matplotlib, numpy, sklearn | Analysed a retail dataset (sales, profit, delivery time) across regions/categories, built trend models with LSM, and checked metric correlations |
| [`credit_scoring/`](credit_scoring/) | Credit scoring & fraud detection | pandas, sklearn (Random Forest, Logistic Regression, StandardScaler), matplotlib | Cleaned a loan dataset, flagged potential fraud with heuristic rules, and predicted loan repayment with an ensemble of classifiers |
| [`geospatial_analysis/`](geospatial_analysis/) | Geospatial analysis | GeoPandas, Shapely, Folium, contextily | Loaded fire-station shapefiles, computed inter-station distance matrices, and visualised stations on interactive and static maps |

## Setup

```bash
pip install pandas numpy matplotlib scikit-learn requests beautifulsoup4 \
            selenium openpyxl deep-translator python-dotenv groq wordcloud \
            opencv-python tensorflow geopandas folium contextily ortools
```

Script-based projects: `python -m web_scraping.main`, `python -m anomaly_detection.main`, etc.  
Notebook-based projects (`exploratory_analysis`, `credit_scoring`, `geospatial_analysis`): open with `jupyter notebook`.

> **Note:** `job_market_pipeline` calls the Groq API (Llama 3.1) for NLP tasks. Set your key via a `.env` file (`GROQ_API_KEY=...`); the key itself is **not** committed to the repo.
