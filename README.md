# Custom Multimodal Attention GNN — Obuasi Landcover Change
## Obuasi Municipality, Ghana | 2018–2025

---

## Project Overview
Urban landcover change classification using a **Custom Multimodal Attention Graph Neural Network (CMAGNN)** combining Sentinel-2 optical and Sentinel-1 radar data.

**5 Landcover Classes:** Water · Trees · Crops · Built-up Areas · Bare Ground

---

## Quick Start

### 1. Install dependencies
```bash
pip install earthengine-api geemap rasterio geopandas numpy pandas \
            matplotlib seaborn scikit-learn torch torch-geometric scipy tqdm joblib nbformat
```

### 2. Authenticate Google Earth Engine
```bash
earthengine authenticate
```

### 3. Run notebooks in order
Either open `MAIN_PIPELINE.ipynb` and follow the steps, or run each notebook manually:

| Order | Notebook | Steps |
|-------|----------|-------|
| 1 | `01_data_acquisition/data_acquisition.ipynb` | GEE data collection & export |
| 2 | `02_preprocessing/preprocessing.ipynb` | Align rasters, remove background pixels |
| 3 | `03_graph_construction/graph_construction.ipynb` | Build graph, normalise features |
| 4 | `04_model/model_architecture.ipynb` | CMAGNN model design |
| 5 | `05_training/training.ipynb` | Train model, plot curves |
| 6 | `06_evaluation/evaluation.ipynb` | Test, confusion matrix, metrics |
| 7 | `07_prediction_mapping/prediction_mapping.ipynb` | Annual classified maps |
| 8 | `08_change_analysis/change_analysis.ipynb` | Area stats & trend plots |

---

## Folder Structure
```
obuasi_landcover/
├── MAIN_PIPELINE.ipynb
├── README.md
├── 01_data_acquisition/
├── 02_preprocessing/
├── 03_graph_construction/
├── 04_model/
├── 05_training/
├── 06_evaluation/
├── 07_prediction_mapping/
├── 08_change_analysis/
├── data/
│   ├── raw/            ← Download GEE exports here
│   ├── processed/      ← Aligned arrays & graph
│   └── exports/        ← Final classified maps (GeoTIFF)
└── outputs/            ← Figures, metrics, model weights
```

---

## Results
| Metric | Value |
|--------|-------|
| Overall Accuracy | 93.80% |
| Avg Producer's Accuracy | 93.79% |
| Avg User's Accuracy | 93.71% |
| Avg F1-score | 93.74% |
