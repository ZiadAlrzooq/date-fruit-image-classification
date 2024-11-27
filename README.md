# Date Fruit Classification

This project automates the classification of nine varieties of date fruits commonly found in Saudi Arabia using a Convolutional Neural Network (CNN) based on the EfficientNetV2-L architecture.

---

## Dataset
The dataset was sourced from [Kaggle](https://www.kaggle.com/datasets/wadhasnalhamdan/date-fruit-image-dataset-in-controlled-environment/data) and manually split into two folders for training and testing:
- **Training Images:** 1,156
- **Test Images:** 502
- **Classes:** 9 varieties of dates (Ajwa, Galaxy, Medjool, Meneifi, NabtatAli, Rutab, Shaishe, Sokari, Sugaey)
  
---

## Showcase of Classes
Below are sample images representing each of the nine date fruit classes included in the dataset:

1. **Ajwa**
   ![Ajwa002](https://github.com/user-attachments/assets/6282dd11-4e23-49b0-ba71-d4a271e59bb4)
 
2. **Galaxy**
   ![Galaxy001](https://github.com/user-attachments/assets/9ae4a8f7-048c-4742-90b7-dd981fc5eafb)
   
4. **Medjool**
   ![Mejdool001](https://github.com/user-attachments/assets/efc0057a-247c-4b46-bae6-1eed2fb4a0ea)

6. **Meneifi**
   ![Meneifi001](https://github.com/user-attachments/assets/b737141f-817c-4ea6-937d-df1f7b79fd4d)

7. **NabtatAli**
   ![NabtatAli002](https://github.com/user-attachments/assets/48b1970f-37ea-4895-ae35-01920c1720df)

8. **Rutab**
   ![Rutab001](https://github.com/user-attachments/assets/acbb8b71-c498-4210-a3bb-6d759f2a8859)

9. **Shaishe**
    ![Shaishe002](https://github.com/user-attachments/assets/30f13563-876e-4f03-850e-15f8e016f631)

10. **Sokari**
   ![Sokari001](https://github.com/user-attachments/assets/d198f959-d125-4721-b8e0-568a3edb6c9c)

11. **Sugaey**
   ![Sugaey002](https://github.com/user-attachments/assets/2eb3eb0b-1424-4f08-9f3a-55150e3ec395)



---

## Challenges
1. **Intra-Class Variation:** Differences within the same type of date based on ripeness.
2. **Inter-Class Similarity:** Visual similarities between different types (e.g., Medjool and Meneifi).

---

## Model Architecture
- **Base Model:** EfficientNetV2-L
- **Additional Layers:**
  - Three dense layers with 1024, 512, and 256 neurons.
  - Final dense layer with 9 neurons for classification.
  - Batch normalization and dropout layers to reduce overfitting.

---

## Training Details
- **Data Augmentation:**
  - Rotation, width/height shifts, zoom, shear, and horizontal flips.
- **Optimizer:** AdamW with an initial learning rate of 0.001.
- **Callbacks:**
  - EarlyStopping (patience: 10)
  - ReduceLROnPlateau (patience: 3, factor: 0.5)
- **Hyperparameters:**
  - Epochs: 100
  - Batch Size: 8
  - Loss Function: Categorical Crossentropy

---

## Results
- **Best Epoch:** 23 (stopped via EarlyStopping).
- **Accuracy:** Achieved 99% accuracy on the testing dataset.
- **Metrics:** High training and validation accuracy were observed, indicating excellent model performance.
- **Evaluation:** A detailed classification report and confusion matrix demonstrate the model's strong generalizability across the nine date fruit classes.

