# Skin Disease Classifier
### Overview
Skin diseases are prevalent globally, affecting millions each year. Early and precise detection is crucial for effective treatment and patient management. In this project, we develop an automated system using a deep learning model that can detect and classify different types of skin lesions accurately.

### Dataset and Pre-processing
In this project, we use the HAMS 10000 dataset (sourced directly from Harvard website). The dataset contains of ~10000 dermatoscopic images from the University of Queensland and the Vienna General Hospital. It features a variety of lesions including melanoma, basal cell carcinoma, and others, richly annotated with expert-reviewed diagnoses and metadata such as lesion type, localization, patient age, and sex. There are some missing values in the metadata, and we just delete those records because we have plenty of data.


Since, there is a heavy class imbalance in lesions as shown in the figure below:

![Screenshot 2024-05-01 at 12 47 51 PM](https://github.com/rahul-purswani/skin-disease-classifier/assets/70603471/4cd9cead-7478-44d2-b2d6-f8cef6ec3ecc)

The training set originally contains of 7511 records and the testing set contains of 2504 records. After augmentation, the The training set contains of 26149 records and the testing set contains of 2504 records.

### CNN Model

### Transfer Learning

| Model Architecture | Training Accuracy | Testing Accuracy | Training Loss |
|----------|----------|----------|----------|
| ResNet18 | Row1Col2 | Row1Col3 | Row1Col4 |
| ResNet50 | Row2Col2 | Row2Col3 | Row2Col4 |
| Efficientnet_b1 | Row3Col2 | Row3Col3 | Row3Col4 |
| Mobilenet_v3_small | Row3Col2 | Row3Col3 | Row3Col4 |
| ViT_base_patch16_244 | Row3Col2 | Row3Col3 | Row3Col4 |
| Efficientnet_B1 | Row3Col2 | Row3Col3 | Row3Col4 |

### References
