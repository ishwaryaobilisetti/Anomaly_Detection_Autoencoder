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

## Results
- The notebook saves the anomaly threshold, evaluation metrics, and confusion matrix image in the working directory.
- All results and visualizations are generated within the notebook.

## Reproducibility
- Random seeds are set for reproducibility.
- The dataset's integrity is checked via SHA256 hash.

## License
This project is for educational purposes.