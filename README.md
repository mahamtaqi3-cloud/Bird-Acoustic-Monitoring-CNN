# Bird Acoustic Monitoring CNN

### The Problem

Traditional ecological monitoring requires manual, time-intensive analysis of large audio datasets to identify bird species. This process is inherently non-scalable and prone to human fatigue, making large-scale biodiversity tracking difficult.

### The Dataset

This project utilizes the **BirdCLEF 2024** dataset (sourced from [Kaggle](https://www.kaggle.com/)), which provides high-quality, labeled soundscapes and recordings for **182 distinct bird species**. This dataset serves as the foundation for training the model to recognize diverse avian vocalizations in complex acoustic environments.

### How It Works

The system follows a rigorous three-stage engineering pipeline:

1. **Acoustic Pre-processing:** Raw audio is sliced into uniform 5-second segments and transformed into **Mel-spectrograms**. This maps frequency and time into a 2D visual heatmap, allowing the model to interpret sound as an image.
2. **Classification Engine:** A custom-built **Convolutional Neural Network (CNN)**, optimized with **Dropout** and **Data Augmentation** to prevent overfitting, analyzes the spectrograms to classify bird species.
3. **Inference Pipeline:** A sliding-window processor handles long-form audio files, generating a structured **Activity Log (CSV)** that maps species detections to precise timestamps.

### Technical Highlights

* **Scale of Classification:** Architected to perform multi-class classification across **182 bird species** defined in the BirdCLEF 2024 benchmark.
* **Data Engineering:** Solved complex dimension mismatches by implementing custom tensor reshaping and channel-stacking, ensuring spectrogram inputs strictly align with the CNN architecture.
* **Robust Generalization:** Implemented aggressive regularization techniques, including Dropout and Data Augmentation, to ensure the model learns generalized bioacoustic patterns rather than memorizing training data.
* **Validation Pipeline:** Includes automated data export and visualization tools that map timestamped detections against the 182-species class list. As shown in **image_f6e888.png**, the system generates structured logs containing timestamps, species labels, and confidence scores.

### Validation & Test Data

To validate the model's performance in real-world scenarios, the pipeline was tested on an external, long-duration audio recording: **XC1148800 (Common Blackbird - *Turdus merula*)**. This test confirmed the model's ability to:

1. Ingest raw, unsegmented audio files.
2. Maintain temporal consistency by mapping detections to specific timestamps.
3. Output reliable activity logs for species identification.

### Results

The model successfully automates the identification of bird activity within raw audio files. The output is a structured dataset providing temporal insights into species occurrence, supporting ecological research.

### Future Development

* **Model Precision:** Planned transition to **Transfer Learning** using pre-trained architectures (e.g., YAMNet or BirdNET) to further improve classification accuracy.
* **System Robustness:** Implementation of confidence thresholding to dynamically filter non-target environmental noise from the final activity logs.


