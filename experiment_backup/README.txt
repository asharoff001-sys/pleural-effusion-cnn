
CNN VERSION 4 - PORTABLE PROJECT BACKUP

Project:
Pleural Effusion Detection from Chest X-ray Images.

Model:
Custom CNN, binary classification.
Input: 224 x 224 grayscale images.
Classes: No Finding (0), Effusion (1).

IMPORTANT FILES:
best_cnn_v4.keras       - Trained best model checkpoint
training_log_v4.csv    - Training history
experiment_details.json - Model and experiment details
model_architecture.json - Model architecture
model_summary.txt      - Model summary
train_df.csv           - Training split
val_df.csv             - Validation split
test_df.csv            - Test split
selected_df.csv        - Selected dataset metadata
split_indices.npz      - Saved split indices
test_predictions.npz   - Final test predictions
confusion_matrix.csv   - Final test confusion matrix

Final test accuracy: 81.13%
Final test ROC-AUC: 0.8889
Final test F1-score: 0.6140

The original NIH X-ray images are NOT included in this backup.
On another Kaggle computer session, attach the same NIH dataset
as notebook input to recreate the image datasets.

The model was trained without DenseNet or transfer learning.
The final test evaluation used threshold 0.5.

This experiment is for academic research, not clinical diagnosis.
