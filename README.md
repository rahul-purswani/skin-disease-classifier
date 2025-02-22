# Skin Disease Classifier
### Overview
Skin diseases are prevalent globally, affecting millions each year. Early and precise detection is crucial for effective treatment and patient management. In this project, we develop an automated system using a deep learning model that can detect and classify different types of skin lesions accurately.

### Dataset and Pre-processing
In this project, we use the HAMS 10000 dataset (sourced directly from Harvard website). The dataset contains of ~10000 dermatoscopic images from the University of Queensland and the Vienna General Hospital. It features a variety of lesions including melanoma, basal cell carcinoma, and others, richly annotated with expert-reviewed diagnoses and metadata such as lesion type, localization, patient age, and sex. 

The input for our models is the images of the lesions and the output is lesion_type. In pre-processing, there are some missing values in the metadata, and we just delete those records because we have plenty of data. We also resize all the images (as per the model requirements), and perform random transformations (like vertical/horizontal flip, rotation, etc). Lastly, all the lesion_types are encoded from strings to vectors (using one-hot encoding).

The training set originally contains 7511 records and the testing set contains 2504 records. However, there is a heavy class imbalance in lesions. To address this problem, we do some random undersampling for nv and some over sampling for the rest of the lesion types on the training set. This way of augmentation works because we are also applying random transformations to the images before feeding them to the model. After augmentation, the training set contains 26149 records and the testing set contains 2504 records.

For more details on data analysis, please refer to the notebook data_analysis.ipynb. For information on data augmentation techniques, please refer to the notebook training.ipynb.

### Training Models
We trained two versions of custom CNN models along with various transfer learning models. The results for each model are summarized below. Notably, smaller models yielded significantly better performance compared to larger ones, likely due to the complexity of the dataset. For detailed insights into the training process and results, please refer to the training.ipynb notebook.

| Model Architecture | Training Accuracy | Testing Accuracy | Training Loss |
|----------|----------|----------|----------|
| Custom_CNN | 94.20% | 63.50% | 0.165 |
| ResNet18 | 94.91% | 80.83% | 0.140 |
| ResNet50 | 93.73% | 80% | 0.175 |
| Efficientnet_b1 | 98.54% | 89.70% | 0.042 |
| Mobilenet_v3_small | 97.91% | 81.35% | 0.061 |
| ViT_base_patch16_244 | 83.16% | 63.78% | 0.432 |

### References
- Tschandl, P., Rosendahl, C., Akay, B. N. (2019). "The HAM10000 dataset, a large collection of multi-source dermatoscopic images of common pigmented skin lesions." Scientific Data, 6, Article number: 194.
