# Distributed Denial-of-Service (DDoS) Detection Using Deep Learning

**Group Members:**  
- Ishman Singh  
- Elijah Sthuthikar G

## Overview

This project reproduces a GRU-based deep learning model for detecting DDoS attacks using the CIC-DDoS2019 dataset. It includes the original single-layer GRU implementation and a contribution in the form of a deeper two-layer GRU model.

## Aim

- **Reproduce** the original GRU model as in Assis et al. (2020).  
- **Extend** the model by stacking an additional GRU layer to improve detection accuracy.
- **Compare** the performance:
  - **Original GRU:** ~98.46% test accuracy  
  - **Modified GRU:** ~99.27% test accuracy

## Setup

- **Python Version:** 3.7+  
- **Key Libraries:** TensorFlow (2.10.0), Keras, Scikit-learn, Pandas  
- **Dataset:** `cicddos2019_dataset.csv` (431,371 records; 80 columns with 78 numeric features after preprocessing)

## Installation

1. Clone the repository.
2. Create an Anaconda environment with GPU support (if available).
3. Install dependencies:
   ```bash
   pip install tensorflow==2.10.0 keras scikit-learn pandas
   ```

## Usage

1. Place `cicddos2019_dataset.csv` in the working directory.
2. Run the provided Jupyter Notebook to:
   - Load and preprocess data.
   - Train the original single-layer GRU model.
   - Train the modified two-layer GRU model.
   - Evaluate both models and compare metrics.

## Contribution

- **Modified Model:** Stacked a second GRU layer (64 units with `return_sequences=True` followed by a GRU with 32 units) to improve classification performance.
- **Results:**  
  - **Original GRU:** ~98.46% accuracy  
  - **Modified GRU:** ~99.27% accuracy  
  - Nearly perfect precision, recall, and F1-score in the modified model.

## Running the Experiments

- **Training & Evaluation:**  
  The Notebook details how to load the dataset, preprocess it (drop non-numeric columns, normalize features), build both models, and train them with a batch size of 128 for 5 epochs.
- **Output:**  
  The Notebook prints model summaries, training history, and classification reports for both models.

## References

- [Assis et al., 2020 – GRU Deep Learning System](https://www.sciencedirect.com/science/article/abs/pii/S1084804520304008)
- [CIC-DDoS2019-DeepLearning GitHub Repository](https://github.com/mvoassis/CIC-DDoS2019-DeepLearning)
- CIC-DDoS2019 Dataset: [Mendeley Data](https://data.mendeley.com/datasets/ssnc74xm6r/1)
