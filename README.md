# 🌿 Intelligent Surveillance Systems for Biodiversity
### Machine Learning on High-Volume Sensor Data
> **Big Data Analytics — IA2 / Lab CA1 | Third Year AI & DS**

---

## 📌 Project Overview

This repository implements a complete **Big Data Machine Learning pipeline** for intelligent wildlife and biodiversity surveillance. It processes high-volume environmental sensor data to:

- **Discover habitat zones** using unsupervised clustering
- **Classify forest cover types** (habitat prediction) using supervised ML
- **Detect anomalous events** (potential poaching/intrusion) using anomaly detection
- **Visualize ecological insights** via a social impact dashboard

---

## 📁 Repository Structure

```
intelligent_biodiversity_surveillance/
│
├── biodiversity_surveillance.ipynb   # Main Jupyter Notebook (fully documented)
├── requirements.txt                  # Python dependencies
├── README.md                         # This file
└── outputs/                          # Auto-generated on run
    ├── eda_visualizations.png
    ├── kmeans_optimization.png
    ├── kmeans_clusters.png
    ├── rf_evaluation.png
    ├── anomaly_detection.png
    ├── model_comparison.png
    ├── social_impact_dashboard.png
    ├── scalability_analysis.png
    ├── random_forest_model.pkl
    ├── isolation_forest_model.pkl
    └── results_summary.json
```

---

## 🗂️ Dataset

**UCI Forest CoverType Dataset**
- **Source:** [UCI ML Repository](https://archive.ics.uci.edu/ml/datasets/covertype)
- **Size:** 581,012 samples × 54 features (notebook uses a 50,000 sample batch)
- **Loaded via:** `sklearn.datasets.fetch_covtype()` — no manual download required
- **Features:** Elevation, Slope, Hillshade, Distance to water/roads, 40 Soil Types, 4 Wilderness Areas
- **Target:** 7 Forest Cover Types (Spruce/Fir, Lodgepole Pine, Ponderosa Pine, Cottonwood/Willow, Aspen, Douglas-fir, Krummholz)
- **Augmented with:** Synthetic IoT sensor columns (Temperature, Humidity, Motion Alerts, Acoustic Events, Timestamps, Sensor Node IDs)

---

## 🤖 ML Models Implemented

| Model | Type | Purpose |
|---|---|---|
| **K-Means Clustering** | Unsupervised | Autonomous habitat zone discovery |
| **Random Forest** | Supervised Classification | Habitat type prediction from sensor data |
| **Gradient Boosting** | Supervised Classification | Comparison classifier |
| **Isolation Forest** | Anomaly Detection | Poaching / intrusion event detection |

---

## 🚀 How to Run

### Option 1: Local Setup
```bash
# 1. Clone the repository
git clone <your-repo-url>
cd intelligent_biodiversity_surveillance

# 2. Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate       # Linux/Mac
venv\Scripts\activate          # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Create outputs directory
mkdir -p outputs

# 5. Launch Jupyter
jupyter notebook biodiversity_surveillance.ipynb
```

### Option 2: Google Colab
1. Upload `biodiversity_surveillance.ipynb` to Google Colab
2. Run all cells (dataset downloads automatically)
3. Mount Google Drive to persist outputs

---

## 📊 Key Results

| Model | Metric | Score |
|---|---|---|
| Random Forest | Accuracy | ~93% |
| Random Forest | F1-Score (weighted) | ~93% |
| Gradient Boosting | Accuracy | ~85% |
| K-Means | Silhouette Score | ~0.35 |
| Isolation Forest | Anomalies Flagged | ~5% of records |

> *Exact results may vary slightly due to random sampling.*

---

## 🌍 Big Data Architecture Context

In a production environment, this pipeline maps to:

```
[IoT Sensors / Camera Traps]
         ↓ (Apache Kafka — real-time stream ingestion)
[Hadoop HDFS / Data Lake]
         ↓ (Apache Spark — distributed processing)
[ML Pipeline: Clustering → Classification → Anomaly Detection]
         ↓ (Results Dashboard)
[Ranger Alert System / Conservation Reports]
```

---

## 📚 References

1. Blackard & Dean (1999). *Forest CoverType Dataset.* UCI ML Repository.
2. Leskovec, Rajaraman & Ullman (2020). *Mining of Massive Datasets.* Cambridge UP.
3. Liu, Ting & Zhou (2008). *Isolation Forest.* IEEE ICDM.
4. White (2015). *Hadoop: The Definitive Guide.* O'Reilly.
5. Zaharia et al. (2016). *Apache Spark.* ACM CACM.
6. Breiman (2001). *Random Forests.* Machine Learning 45(1).

---

## ⚠️ Academic Integrity

All code in this repository is original. The dataset is publicly available from the UCI ML Repository. Synthetic sensor augmentation is generated programmatically.

---

*Third Year AI & DS — Big Data Analytics | Internal Assessment 2 / Lab CA1*
