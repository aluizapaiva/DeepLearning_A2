# Skin Lesion Classification: CNN-Based Diagnostic Support Prototype

## Project Overview
Deep learning models that classify dermoscopic images as benign or malignant, built as a research prototype for a hospital dermatology department scenario. The main goal is high recall (sensitivity), because a missed malignant lesion is the costly error.

This is a student prototype. It has not been validated clinically and is not a medical device.

## Dataset
- **Source**: ISIC (International Skin Imaging Collaboration) dermoscopic images with metadata
- **Size**: 7,818 images, 85.8% benign and 14.2% malignant (about 6:1)
- **Split**: stratified 70/15/15 by image into train, validation and test sets

## Models Compared
A naive baseline, a small CNN, and four ImageNet transfer learning models (VGG16, ResNet50, InceptionV3, MobileNetV2), each trained with two class-weight strategies: weights that penalise missed malignant cases (original) and equal weights (balanced).

## Key Results (test set, 1,173 images, threshold 0.5)
| Model | Weights | Recall | Precision | AUC |
|---|---|---|---|---|
| VGG16 | original | 93.4% | 31.8% | 0.90 |
| InceptionV3 | original | 88.6% | 31.0% | 0.89 |
| MobileNetV2 | original | 80.8% | 37.0% | 0.89 |
| MobileNetV2 | balanced | 61.1% | 60.4% | 0.90 |
| InceptionV3 | balanced | 59.3% | 61.5% | 0.89 |
| ResNet50 | both | 1% to 26% | 54% to 67% | 0.84 |

The class weights mainly move the model along the recall and precision trade-off. They do not change the AUC, which stays close to 0.9 for three of the four architectures.

## Limitations
- The images are split by image, not by lesion or patient, so near-duplicate images may sit in both train and test and inflate the results
- The generator found 4,228 training images in the organised folder, not the 5,472 that a 70% split implies, so the models were trained on less data than the notebook states
- Models were compared on the test set, and the reported figures are for the model after the last epoch, not the best checkpoint
- Images are only rescaled to 0 to 1, while the ImageNet models expect their own preprocessing. This is a more likely cause of the poor ResNet50 result than the architecture itself
- No external validation, and the metadata is not used
- The management report makes business claims (speed, capacity, biopsy reduction, regulatory compliance) that come from the scenario and are not supported by this analysis

## Files
- `skin_lesion_classification.ipynb`: technical notebook with code, outputs and analysis
- `ISIC_ManagementReport.pdf`: executive summary for the hospital scenario

The images and metadata are not included. To rerun the notebook, open it in Google Colab and set the data paths to your own copy of the ISIC data. Libraries: tensorflow, opencv, pandas, numpy, matplotlib, seaborn, scikit-learn.

## Technologies Used
Python, TensorFlow and Keras, Google Colab

## Academic Context
**Course**: DTSC301 - Deep Learning Through Neural Networks  
**Institution**: Bond University  
**Focus**: Real-world application of CNNs in medical imaging

## Contact
Ana Paiva  
Data Analyst Student, Bond University  
GitHub: @aluizapaiva
