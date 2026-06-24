# Bird Acoustic Monitoring AI

This project implements an automated pipeline to identify bird species from long-duration audio recordings using Deep Learning.

## Approach
- **Data Processing:** Converted raw audio into **Mel-spectrograms** to treat sound as image data.
- **Model:** A custom Convolutional Neural Network (CNN) trained to classify 182 bird species.
- **Inference:** Developed a **sliding-window pipeline** to process long-form audio files and generate timestamped activity logs.

## Key Features
- **Overfitting Mitigation:** Used Dropout and Data Augmentation to improve model generalization.
- **Data Pipeline:** Custom handling of spectrogram channels and dimensions to match model requirements.
- **Validation:** Includes automated logging and timeline visualization of bird activity.

## Results
- Successfully processed long-form audio files into structured CSV logs.
- Visualized bird activity patterns over time.

## Future Improvements
- Implement Transfer Learning using pre-trained models like YAMNet for higher precision.
- Introduce confidence thresholding to filter background noise.
