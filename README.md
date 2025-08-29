# DeepLearning_A2
Personal Projects with Deep Learning

# Skin Lesion Classification: CNN-Based Diagnostic Support System

## Project Overview
This project develops a machine learning model to assist dermatologists in classifying skin lesions as either benign or malignant using dermoscopic images. The solution aims to serve as a diagnostic support tool to accelerate dermatological assessments and improve early cancer detection.

## Business Context
**Problem**: Manual screening of skin lesions is time-intensive and can result in missed early-stage cancers (15% miss rate in routine triage).

**Solution**: An automated image classification system that provides instant risk assessment and biopsy recommendations, helping clinicians prioritize high-risk cases.

## Technical Approach

### Model Architecture
- **Primary Model**: Convolutional Neural Network (CNN) using VGG16 architecture
- **Task Type**: Binary classification (benign vs. malignant)
- **Input**: Dermoscopic images from ISIC dataset
- **Output**: Malignancy probability score (0-100%)

### Dataset
- **Source**: ISIC (International Skin Imaging Collaboration) dataset
- **Size**: 7,818 dermoscopic images
- **Classes**: Benign and malignant skin lesions
- **Format**: High-resolution dermoscopic images with corresponding metadata

### Performance Results
- **Cancer Detection Rate**: 93.4%
- **Processing Time**: <5 seconds per image
- **Clinical Impact**: 60x faster than manual review
- **Capacity Increase**: Enables 67% more cases annually

## Repository Structure
```
skin-lesion-classification/
├── skin_lesion_analysis.ipynb    # Main technical notebook
├── management_report.pdf         # Executive summary for clinical staff
├── data/                        # Dataset files 
│   ├── ISIC_Metadata.csv
│   └── images/                  # Dermoscopic images
├── models/                      # Saved model files
├── results/                     # Output visualizations and metrics
└── README.md                    # This file
```

## Key Features
- **Multiple Model Comparison**: Testing various CNN architectures
- **Data Preprocessing**: Image normalization and augmentation
- **Performance Evaluation**: Comprehensive metrics for medical applications
- **Clinical Visualization**: Charts and graphs suitable for medical professionals
- **Risk Assessment**: Probability scores for clinical decision support

## Clinical Applications
- **Diagnostic Support**: Assists dermatologists in lesion assessment
- **Triage Enhancement**: Prioritizes high-risk cases for immediate review
- **Workflow Integration**: Seamlessly fits into existing clinical processes
- **Quality Assurance**: Reduces diagnostic variability and improves consistency

## Technologies Used
- **Python**: Primary programming language
- **TensorFlow/Keras**: Deep learning framework
- **CNN Architecture**: VGG16 for image classification
- **Google Colab**: Development and training environment
- **Jupyter Notebooks**: Documentation and analysis

## Installation & Usage
1. Clone this repository
2. Install required dependencies: `pip install tensorflow pandas numpy matplotlib seaborn scikit-learn`
3. Open `skin_lesion_analysis.ipynb` in Jupyter or Google Colab
4. Follow the notebook cells sequentially for model training and evaluation

## Reports Included
- **Management Report**: Non-technical executive summary for hospital administration
- **Technical Report**: Detailed Jupyter notebook with complete methodology and results

## Academic Context
**Course**: DTSC301 - Deep Learning Through Neural Networks  
**Institution**: Bond University  
**Assessment**: Assignment 2 (40% weighting of Final Grade)  
**Focus**: Real-world application of CNNs in medical imaging

## Ethical Considerations
- Model serves as diagnostic support only - final decisions remain with physicians
- Continuous monitoring ensures performance standards
- Compliant with medical device regulations
- Patient privacy and data security maintained throughout

## Contact
Ana Luiza Lerch Paiva  
Data Analyst Student, Bond University  
GitHub: @aluizapaiva

---
*This project demonstrates practical application of deep learning techniques to healthcare challenges, combining technical rigor with clinical relevance.*
