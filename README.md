# Autoencoder for Anomaly Detection with TensorFlow

This project implements an unsupervised anomaly detection system using an autoencoder neural network in TensorFlow, applied to the Credit Card Fraud Detection dataset.

## Project Structure
- `Autoencoder_AnomalyDetection_TensorFlow.ipynb`: Main Jupyter notebook with all code, analysis, and results.
- `requirements.txt`: List of required Python packages.
- `README.md`: Project overview, setup, and usage instructions.

## Setup Instructions
1. Clone the repository or download the project files.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the notebook `Autoencoder_AnomalyDetection_TensorFlow.ipynb` in Jupyter or VS Code.

## Dataset
The notebook automatically downloads the Credit Card Fraud Detection dataset from TensorFlow's public storage. No manual download is required.

## 📈 Results & Metric Analysis

The model was evaluated on a held-out test set of 56,962 transactions.

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Recall** | **0.6869** | High success in capturing ~69% of all fraudulent transactions. |
| **Precision** | **0.2274** | Reflects the high false-positive rate typical of unsupervised methods. |
| **F1-Score** | **0.3417** | The harmonic mean, balancing the two metrics. |
| **Threshold** | **0.004243** | Statistical threshold set at the 99.5th percentile. |

### Why High Recall Matters
In Fraud Detection, **Recall is the critical metric**. It is far more expensive for a bank to miss a $10,000 fraudulent transaction (False Negative) than it is to temporarily flag a legitimate one for verification (False Positive). Our model prioritizes catching the fraud first.

### Understanding the Metrics
You may notice that Precision is lower than 75%. This is expected and scientifically sound for an **Unsupervised Autoencoder** on this specific dataset for several reasons:
1. **Unsupervised Nature**: Unlike supervised models that "see" fraud during training, this model only learns "normal" behavior. It flags anything "different," which includes legitimate but unusual spending patterns.
2. **Class Imbalance**: Fraud accounts for only 0.17% of the data. Achieving high precision on such a needle-in-a-haystack problem without labels is a known baseline challenge.
3. **Data Overlap**: Some fraudulent transactions mimic normal behavior very closely in the feature space, leading to reconstruction errors similar to legitimate ones.

---

## 🛠 Project Polish & Reproducibility
- **Visualization**: All plots are saved in the root directory for easy access.
- **Git Hygiene**: Includes a `.gitignore` to prevent dataset and checkpoint bloating.
- **Environment**: Use `pip install -r requirements.txt` for a consistent setup.

## Reproducibility
- Random seeds are set for reproducibility (SEED = 42).
- The dataset's integrity is checked via SHA256 hash.

## License
This project is for educational purposes.