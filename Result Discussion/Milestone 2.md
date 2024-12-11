# Skin Cancer Detection using ISIC SLICE-3D Data

## Evaluation Experiment
### Objective
The goal is to evaluate the effectiveness of EfficientNet-based models for skin cancer detection on lower-quality, non-dermoscopic images from the ISIC SLICE-3D dataset, while maintaining a sensitivity threshold of at least 80% for clinical relevance.
### Independent Variable
- Model Architecture
- Ensemble Approach
- Training Data Size
- Image Preprocessing
### Dependent Variable
- Area under ROC Curve and above 80% TPR
- True Positive Rate
- False Positive Rate
- Accuracy
### Control Variables
- Hardware Setup
- Optimizer and Learning Rate
### Experiment Design
-	Start by training a baseline EfficientNet model on the entire dataset with default preprocessing. Record the ROC curve, sensitivity, and AUC.
-	Test the same model with different image resolutions to evaluate how image quality affects performance.
-	Train larger versions of EfficientNet and ensemble models to compare performance improvements.
-	Apply various image preprocessing techniques to the dataset and test their impact on model.
-	Measure how the model performs on smaller subsets of the dataset to evaluate how much training data is necessary for reliable performance.
### Expected Outcome
Insights into:
- The sensitivity of EfficientNet-based models for real-world, low-quality images.
- The effect of model size and training data on achieving a clinical-grade sensitivity threshold.
- The trade-off between sensitivity and false positives, using ROC curve analysis.
