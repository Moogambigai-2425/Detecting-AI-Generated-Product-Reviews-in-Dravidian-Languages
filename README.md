# Detecting-AI-Generated-Product-Reviews-in-Dravidian-Languages
This repository contains the implementation details for the shared task on on Detecting AI-Generated Product Reviews in Dravidian Languages, as part of DravidianLangTech@NAACL 2025.
# Detecting AI-Generated Product Reviews in Dravidian Languages

## Introduction

The proliferation of AI-generated content has brought both opportunities and challenges across various domains, including e-commerce, social media, and journalism. While AI can generate text efficiently, it also raises significant concerns regarding authenticity, particularly in online reviews, where fake or AI-generated content can manipulate consumer trust and market dynamics. Detecting such content is essential for ensuring credibility and maintaining user trust in digital platforms

This shared task focuses on detecting AI-generated product reviews in Dravidian languages, specifically Tamil and Malayalam. These languages pose unique challenges for natural language processing (NLP) due to their rich morphology, agglutinative nature, code-mixing tendencies, and lack of extensive annotated datasets. Tamil and Malayalam also frequently incorporate regional slang, making text analysis even more complex.

**Keywords**: AI-generated content detection, Dravidian languages, Tamil and Malayalam, machine learning models, BERT, code-mixed text classification.

## Dataset

The datasets provided in the shared task consisted of human-written and AI-generated product reviews in Tamil and Malayalam, structured with distinct features and labeled samples. The data distribution is presented in Table 1.

- **Training Data**: 
  - Tamil: 808 comments
  - Malayalam: 800 comments
  - Features: ID, DATA, and LABELS

- **Test Data**: 
  - Tamil: 100 comments
  - Malayalam: 200 comments
  - Features: ID and DATA

Comprehensive preprocessing was performed to standardize the datasets, including feature encoding, label normalization, and partitioning into training and evaluation subsets. This ensured optimal compatibility and performance across both traditional and transformer-based models

### Models for Classification

- **Logistic Regression (LR)**: Utilized TF-IDF vectorization to transform textual data into numerical features, enabling efficient linear classification.
- **Support Vector Machine (SVM)**: Combined robust preprocessing techniques with traditional classification to handle complex decision boundaries.
- **BERT**: Leveraged the pre-trained transformer model with fine-tuning tailored separately for Tamil and Malayalam, incorporating advanced tokenization techniques.

### Preprocessing Steps

To ensure data consistency and enhance model performance, the following preprocessing steps were undertaken:

- **Text Cleaning**: Removed special characters, normalized transliterated text, and addressed the challenges of code-mixing.
- **Feature Extraction**: Applied TF-IDF vectorization for LR and SVM to capture key textual patterns.
- **Tokenization**: Used BERT’s subword tokenization to segment text into meaningful units for deep learning.

### Training Process

The training process was designed to maximize the models' predictive capabilities:

- **Data Partitioning**: Split datasets into training and validation subsets, ensuring balanced representation of classes.
- **Model Optimization**: Conducted cross-validation and hyperparameter tuning to identify optimal configurations for each model.
- **Evaluation**: Monitored performance using accuracy and macro F1 metrics to ensure alignment with task objectives.

## Experimental Results

The experimental evaluation reveals the performance of the classification models as summarized in Table 2. Among the models, **SVM-Tamil** achieved the highest accuracy (89.0%) and Macro F1 score (89.0%), demonstrating its robustness in classifying Tamil AI-generated and human-written reviews. **LR-Tamil** followed closely with an accuracy of 88.27% and an F1 score of 89.14%. **BERT** demonstrated competitive performance but faced challenges with code-mixed and nuanced text.

### Performance Summary

| Model | Language | Accuracy | Precision | Recall | F1 Score |
|-------|----------|----------|-----------|--------|----------|
| Logistic Regression (LR) | Tamil | 88.27% | 87.64% | 90.70% | 89.14% |
| Logistic Regression (LR) | Malayalam | 76.88% | 77.92% | 75.00% | 76.43% |
| Support Vector Machine (SVM) | Tamil | 89.00% | 89.00% | 89.00% | 89.00% |
| Support Vector Machine (SVM) | Malayalam | 77.00% | 77.00% | 77.00% | 77.00% |
| BERT | Tamil | 78.00% | 88.24% | 62.50% | 73.17% |
| BERT | Malayalam | 79.01% | 85.14% | 73.26% | 78.75% |

## Conclusion

This study investigates the use of machine learning and deep learning models to detect AI-generated content in Tamil and Malayalam product reviews. The results show that traditional machine learning models, particularly **SVM**, are highly effective in classifying AI-generated and human-written reviews, especially in low-resource languages. While **BERT** provided promising results, its performance was affected by the complexity of code-mixing and nuanced language use in Tamil and Malayalam.

