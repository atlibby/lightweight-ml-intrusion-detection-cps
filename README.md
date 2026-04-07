This project implements a lightweight, multimodal intrusion detection system testbed for cyber-physical systems using both classical machine learning techniques and deep learning models.
It compares model performance across tabular and text-based pipelines, focusing specifically on evaluating whether smaller architectures could achieve competitive performance in intrusion detection tasks.
The repository includes full data pipelines, model implementations, and results used in the accompanying thesis.

## Setup

1. Install dependencies:
   pip install torch transformers datasets scikit-learn pandas numpy matplotlib seaborn

2. Ensure dataset paths are configured inside:
   - data_pipeline.py
   - text_pipeline.py

3. Place datasets (CICIDS2017, TON-IoT) in the specified directories.

---

## Running Models

Each model can be run via test_suite.py, which automatically builds and caches pipelines, then iterates through required training configurations and modalities, afterwhich it records and caches metrics and plots (macro-F1, precision, recall, accuracy, confusion matrices and loss curves):

- Random Forest:
  python rf_baseline.py

- MLP:
  python mlp_baseline.py

- CNN-LSTM:
  python cnn_lstm.py

- MAE:
  python mae.py

- ST-MAE:
  python stmae.py

- DistilBERT:
  python distilbert.py

- TinyLlama:
  python tinyllama.py

---

## Notes
- GPU used to generate current results directory files: A100 (167.1 GB system RAM; 80 GB GPU RAM)
- GPU is required for transformer-based models (DistilBERT, TinyLlama).
- Large datasets may require significant RAM.
- Feature caching is used to speed up repeated runs - verify that cache directories correspond to correct paths.
