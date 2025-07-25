# DWT-Former: Fusing Wavelet-Based Multi-Scale Features and Transformer-Based Temporal Representations for Photovoltaic Power Forecasting
zh_CN [简体中文](README.md)


Photovoltaic (PV) power forecasting faces challenges in capturing long-range temporal dependencies and fusing multi-source heterogeneous information such as meteorological data and historical power data. Accurately modeling the multi-scale dynamics of PV power, from seasonal variations to high-frequency fluctuations, is crucial for achieving accurate predictions. The proposed DWT-Former in this project is a novel hybrid deep learning framework designed to address these challenges. Its unique dual-branch structure combines the advantages of Transformer models in handling temporal dependencies with the ability of multi-scale wavelet analysis to capture frequency characteristics. Through excellent performance on multiple real-world PV datasets, DWT-Former has demonstrated its strong capability in capturing complex PV power generation dynamics, providing a valuable tool for optimizing grid management and promoting solar energy integration.

The core of the DWT-Former model is a dual-branch collaborative prediction framework, aiming to tackle the inherent challenges in PV power forecasting, such as non-stationarity, multi-scale coupling characteristics, and multi-source data fusion.

---------------------------------------

## Getting Started

1. **Environmental Requirements**
The software environment for the experiments is based on Python 3.11, PyTorch 2.5.1, and CUDA 12.4.
* Python 3.11+
* PyTorch 2.5.1
* NumPy
* Pandas

2. **Installation**
Clone this repository:
```bash
# Install dependencies
pip install -r requirements.txt  
python setup.py install          
```

```bash
git clone https://github.com/your-username/DWT-Former.git  
cd DWT-Former
```

(Recommended) Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # on Windows use `venv\Scripts\activate`
```

3. **Install Dependencies**
```bash
pip install -r requirements.txt
```

## Model Architecture

The core of the DWT-Former model is a dual-branch collaborative prediction framework, which aims to address the inherent non-stationarity, multi-scale coupling characteristics, and multi-source data fusion challenges in PV power forecasting.

The overall architecture of the model mainly includes:
- **Wavelet Multi-scale Branch**: This branch uses Discrete Wavelet Transform (DWT) to decompose the original power data into Trend and Season components. Subsequently, a refined multi-scale processing module analyzes these components and constructs a rich three-dimensional feature space including time, frequency, and scale.
- **Transformer Branch**: This branch adopts an improved Transformer architecture (inspired by iTransformer) and is responsible for efficiently capturing long-term dependencies and interactions between variables from the input that integrates meteorological data and historical power data.
- **Feature Fusion Module**: Finally, a fusion module integrates the features from the above two branches to achieve high-precision power prediction.

## Results

DWT-Former outperforms or significantly outperforms current mainstream time series prediction benchmark models (such as LSTM, GRU, Informer, TimesNet, etc.) on all four datasets.

| Dataset  | MAE (DWT-Former) | Best Baseline (MAE)       | Improvement |
|----------|------------------|---------------------------|-------------|
| AS-PV    | 0.169            | 0.179 (Bi-LSTM)           | 5.6%        |
| CC-PV    | 0.192            | 0.219 (CNN+GRU+LSTM)      | 12.3%       |
| NWG-PV   | 0.108            | 0.133 (CNN+GRU+LSTM)      | 18.8%       |
| Comp-PV  | 0.278            | 0.300 (GRU)               | 7.3%        |
