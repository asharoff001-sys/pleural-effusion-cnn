# Pleural Effusion Classification from Chest X-ray Images Using CNN

## Project Overview

This project focuses on detecting **Pleural Effusion** from chest X-ray images using a Convolutional Neural Network (CNN).

The model performs binary image classification:

- **Effusion:** Images labelled with pleural effusion.
- **No Finding:** Images labelled as having no finding in the NIH dataset.

The goal is to develop a CNN model that can learn visual patterns from chest X-ray images and classify them into these two categories.

## Dataset

This project uses the **NIH Chest X-ray Dataset**.

The selected dataset contains 73,678 images:

| Class | Number of Images |
|---|---:|
| No Finding | 60,361 |
| Effusion | 13,317 |
| **Total** | **73,678** |

The dataset was divided into training, validation, and testing sets using patient-level splitting to prevent images from the same patient appearing in multiple sets.

- Training: 58,428 images
- Validation: 7,609 images
- Testing: 7,641 images

The dataset is not included in this repository. Users must obtain it separately from its official source.

## Methodology

The project follows these main steps:

1. **Data Selection:** Selected images labelled as Effusion or No Finding.
2. **Preprocessing:** Images were resized to 224 × 224 pixels, converted to grayscale, and normalized to the range 0–1.
3. **Data Augmentation:** Applied random rotation, zoom, translation, and contrast adjustment to improve model generalization.
4. **Model Development:** Built a CNN with convolutional layers, batch normalization, ReLU activation, max pooling, global average pooling, dropout, and a sigmoid output layer.
5. **Training:** Trained the model using the Adam optimizer and binary cross-entropy loss.
6. **Evaluation:** Evaluated the final model on an independent test set using accuracy, precision, recall, F1-score, and a confusion matrix.

## Model Performance

The final test results are:

| Evaluation Metric | Score |
|---|---:|
| Accuracy | 81.13% |
| Precision | 49.10% |
| Recall | 81.93% |
| F1-score | 0.614 |

### Confusion Matrix

| Actual / Predicted | No Finding | Effusion |
|---|---:|---:|
| No Finding | 5,052 | 1,189 |
| Effusion | 253 | 1,147 |

The model achieved 81.93% recall for Effusion, meaning it identified a substantial proportion of the Effusion-labelled test images. However, its precision was 49.10%, indicating that false positive predictions remain a limitation.

## Repository Contents

- **Jupyter Notebook:** Complete Python implementation and experiment workflow.
- **best_cnn_v4.keras:** Trained CNN model.
- **accuracy_curve.png:** Training and validation accuracy graph.
- **loss_curve.png:** Training and validation loss graph.
- **confusion_matrix.png:** Final test confusion matrix.
- **evaluation_metrics.csv:** Evaluation metrics.
- **classification_report.txt:** Detailed classification report.
- **training_log_v4.csv:** Training history.
- **experiment_details.json:** Experiment configuration and details.
- **model_architecture.json:** Model architecture information.
- **model_summary.txt:** Model summary.
- **train_df.csv, val_df.csv, test_df.csv:** Dataset split information.
- **test_predictions.npz:** Saved test predictions.

## Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Kaggle Notebook

## How to Run

1. Clone or download this repository.
2. Download the NIH Chest X-ray Dataset separately.
3. Open the Jupyter Notebook in Kaggle or a compatible Python environment.
4. Configure the dataset paths according to your environment.
5. Install the required Python libraries.
6. Run the notebook cells in order.

## Limitations

The NIH dataset uses labels extracted from radiology reports, which may contain noise. The No Finding label should not be interpreted as a confirmed clinical diagnosis of a normal chest.

This model is an academic research project and is not intended for clinical diagnosis or medical decision-making.

## Author

**Yasin Hossain**

GitHub Repository: https://github.com/asharoff001-sys/pleural-effusion-cnn

## License

This project is intended for academic and educational purposes. Please follow the NIH dataset's terms of use when accessing or using the dataset.
