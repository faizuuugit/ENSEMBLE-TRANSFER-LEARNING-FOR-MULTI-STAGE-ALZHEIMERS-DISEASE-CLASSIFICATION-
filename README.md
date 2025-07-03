
#  ENSEMBLE TRANSFER LEARNING FOR MULTI-STAGE ALZHEIMER’S DISEASE CLASSIFICATION

### Submitted in partial fulfillment of the requirements for the award of the Degree of BACHELOR OF TECHNOLOGY In COMPUTER SCIENCE AND ENGINEERING

## Submitted by:

- **Md. Faizuddin** – 21501A05B4  
- **K. Pavan Kumar** – 21501A0584  
- **N. Nitin Chowdary** – 21501A05C6  
- **K. Nirmal** – 21501A0571  

Under the esteemed guidance of  
**Mr. N. Sudhakar Reddy, M.Tech, (Ph.D.)**  
Assistant Professor, Department of CSE

**Department of Computer Science and Engineering**  
Prasad V. Potluri Siddhartha Institute of Technology  
(AUTONOMOUS)  
(Approved by AICTE, Affiliated to JNTUK, Kakinada, ISO 9001:2015 Certified Institution)  
Kanuru, Vijayawada – 520007  
Academic Year 2024–2025

---

## CERTIFICATE

This is to certify that the project entitled **“ENSEMBLE TRANSFER LEARNING FOR MULTI-STAGE ALZHEIMER’S DISEASE CLASSIFICATION”** is a bonafide record of the work done by:

- Md. Faizuddin – 21501A05B4  
- K. Pavan Kumar – 21501A0584  
- N. Nitin Chowdary – 21501A05C6  
- K. Nirmal – 21501A0571  

in partial fulfillment of the requirements for the award of the degree of **Bachelor of Technology in Computer Science and Engineering** of Jawaharlal Nehru Technological University Kakinada during the academic year 2024–2025.

**Project Guide**  
Mr. N. Sudhakar Reddy  
Assistant Professor  
Department of CSE  

**Head of the Department**  
Dr. K. Bhaskar  
Professor & HOD  
Department of CSE

---

## ACKNOWLEDGEMENT

We would like to express our sincere gratitude to our guide **Mr. N. Sudhakar Reddy**, Assistant Professor, Department of Computer Science and Engineering, for his continuous support, encouragement, and expert guidance throughout the project.

We extend our thanks to **Dr. K. Bhaskar**, Professor & Head, Department of CSE, for his valuable suggestions and motivation.

We also thank our Principal, **Dr. K. Satya Prasad**, and the Management of **P.V.P. Siddhartha Institute of Technology**, for providing us with the resources and support necessary to carry out this project successfully.

---

## ABSTRACT

Alzheimer’s disease (AD) is a chronic neurodegenerative disease that progresses over time and is considered to be the most common cause of dementia. It has become an increasing concern worldwide. Magnetic Resonance Imaging (MRI) scans can provide detailed information on changes in the brain structure.

This project presents a deep learning-based approach for multi-stage classification of Alzheimer’s disease using ensemble transfer learning. We use three pre-trained CNN models: **InceptionV3**, **Xception**, and **ResNet50**, for extracting deep features from brain MRI scans. These features are then concatenated and used for classification into four classes: **Non-Demented**, **Very Mild Demented**, **Mild Demented**, and **Moderate Demented**.

Due to the dataset imbalance, **SMOTE (Synthetic Minority Over-sampling Technique)** was used to balance the class distribution. The ensemble model achieved **98% accuracy** and reduced false-positive rate by **1.5%** compared to single CNN models.

---

## CONTENTS

1. Introduction  
2. Objective  
3. Problem Statement  
4. Literature Survey  
5. System Analysis  
6. System Design  
7. Implementation  
8. Results  
9. Testing  
10. Conclusion  
11. Bibliography

---

## CHAPTER 1 – INTRODUCTION

Alzheimer’s Disease (AD) is a neurological disorder that involves the progressive loss of memory and cognitive abilities. Accurate classification of its stages can play a significant role in its treatment.

Machine learning and deep learning algorithms have recently shown great promise in medical image classification. With the availability of brain MRI datasets, it has become feasible to automate the classification of Alzheimer's disease.

In this project, we utilize ensemble learning by combining multiple transfer learning models. We aim to leverage the strengths of multiple architectures to improve the overall performance.

---

## CHAPTER 2 – OBJECTIVE

- To classify Alzheimer’s disease into four stages using MRI images.
- To use ensemble transfer learning models for feature extraction.
- To use SMOTE for handling class imbalance.
- To design a classifier based on concatenated deep features from multiple CNNs.
- To achieve high accuracy, precision, and recall.
- To reduce false positives and improve robustness.

---

## CHAPTER 3 – PROBLEM STATEMENT

Alzheimer's Disease classification is often approached as a binary classification problem. However, early detection of its stages is crucial for treatment planning. 

Challenges:
- Imbalanced dataset
- Subtle variations in MRI images across stages
- Overfitting on small sample sizes

The goal is to build a robust classification system that accurately identifies all four stages of AD.

---

## CHAPTER 4 – LITERATURE SURVEY

Several deep learning models have been applied in the past for AD classification. Pre-trained models like VGG16, ResNet, and DenseNet have shown promising results.

Studies have shown:
- Transfer learning improves convergence on small datasets.
- Ensemble learning boosts performance by combining models.
- SMOTE effectively handles class imbalance in medical datasets.

---

## CHAPTER 5 – SYSTEM ANALYSIS

### 5.1 Feasibility Study
- **Technical**: The project can be implemented using Python and TensorFlow with standard hardware.
- **Operational**: The system is easy to use and automates a complex task.
- **Economic**: No additional cost since open-source tools and publicly available datasets are used.

### 5.2 Requirements
- **Hardware**: Minimum 8GB RAM, NVIDIA GPU (recommended)
- **Software**: Python, TensorFlow, Keras, NumPy, Matplotlib, imblearn

---

## 🔧 CHAPTER 6 – SYSTEM DESIGN

### Methodology of the Proposed Method

The methodology of the proposed Alzheimer’s stage classification system follows a structured pipeline combining data preprocessing, sampling, transfer learning, and ensemble classification.

 AD Dataset (MRI Images) ]  

        ↓  
        
[ Preprocessing-(Reshape & Rescale]

        ↓  
        
[ Sampling with SMOTE ]

        ↓  
[ Transfer Learning ]

        ↓  
        
[ AD Classification with (ResNet50, InceptionV3, Xception, Ensemble of all)]

        ↓  
        
[ OUTPUT --> NC  (Non-Demented), EMCI (Very Mild Demented), LMCI (Mild Demented), (Moderate Demented) ]



**Fig 5.1**: Methodology of Proposed Method

This architecture ensures that raw MRI scans are properly normalized and augmented before class imbalance is addressed using SMOTE. The refined data is then passed through multiple transfer learning models to extract deep features, which are used in an ensemble classifier for precise stage prediction.


---

## CHAPTER 7 – IMPLEMENTATION

- **Data Preprocessing**: Resize to 227x227, normalize to [0,1]
- **SMOTE**: Balanced dataset to 3,200 images per class
- **Model**: Feature extractors (InceptionV3, Xception, ResNet50)
- **Classifier**: Concatenated features passed to Dense(10, ReLU) → Dropout(0.3) → Dense(4, Softmax)
- **Training**: 25 epochs, batch size 64
- **Evaluation**: Accuracy, confusion matrix, 10-fold cross-validation

---

## CHAPTER 8 – RESULTS

| Model        | Accuracy |
|--------------|----------|
| InceptionV3  | 94.8%    |
| Xception     | 94.3%    |
| ResNet50     | 94.1%    |
| Ensemble     | 98.0%    |

- Ensemble approach improved generalization.
- False positives reduced by 1.5%.

---

## CHAPTER 9 – TESTING

### 9.1 Unit Testing
- Verified preprocessing, model inputs and outputs

### 9.2 Integration Testing
- From image loading to class prediction

### 9.3 System Testing
- Overall performance and robustness

### 9.4 Error Handling
- Invalid images and corrupt files handled gracefully

---

## CHAPTER 10 – CONCLUSION

The proposed ensemble transfer learning model effectively classifies Alzheimer’s disease into four stages. By using SMOTE and feature concatenation, we enhanced performance while reducing false positives.

This system can assist healthcare professionals in early and accurate diagnosis.

---

## CHAPTER 11 – BIBLIOGRAPHY

1. Sarraf S, Tofighi G. Deep learning-based pipeline to recognize Alzheimer’s disease using fMRI data.
2. Wen J, Thibeau-Sutre E, Diaz-Melo M, et al. Convolutional neural networks for classification of Alzheimer’s disease.
3. Ali F, Rahim A, et al. Handling class imbalance with SMOTE in healthcare datasets.
4. Gupta A, Ayhan M, Maida A. Deep learning models for structural MRI-based diagnosis of Alzheimer’s disease.

---
