# Diabetic Retinopathy Diagnosis Project

## MOTIVATION

Diabetic retinopathy (DR) is one of the leading causes of vision loss. The World Health Organization reports that more than 300 million people worldwide have diabetes (Wong et al. 2016). In 2019, the global prevalence of DR among individuals with diabetes was at more than 25% (Thomas et al. 2019). The prevalence has been rising rapidly in developing countries.

Early detection and treatment are crucial steps towards preventing DR. The screening procedure requires a trained clinical expert to examine the fundus photographs of the patient's retina. This creates delays in diagnosis and treatment. This is especially relevant for developing countries, which often lack qualified medical staff to perform the diagnosis. Automated detection of DR can speed up the efficiency and coverage of the screening programs.
![Bildschirmfoto 2023-11-04 um 02 11 56](https://github.com/hrishikesh829370/Dibetic_Retinopathy_Diagnosis/assets/131910887/885e756e-e150-4b6e-a599-94ea7fc766d2)

## Datset

The data for this project is sourced from Kaggle and consists of 3,662 labeled retina images of clinical patients and a test set with 1,928 images with unknown labels. The images are labeled by a clinical expert. The integer labels indicate the severity of DR on a scale from 0 to 4, where 0 indicates no disease and 5 is the proliferative stage of DR.

![Bildschirmfoto 2023-11-04 um 02 13 00](https://github.com/hrishikesh829370/Dibetic_Retinopathy_Diagnosis/assets/131910887/de22e7da-a1fd-4a42-8b4d-b1051ff2dfc9)

## Project Overview

Diabetic retinopathy (DR) is a leading cause of vision loss globally, and early detection is crucial to prevent its progression. This project aims to develop a model for automated DR diagnosis using fundus photographs.

## Project Structure

The project comprises several key components:

- `config.py`: Configuration settings for training, including device, learning rate, batch size, and more.

- `dataset.py`: Defines the custom dataset class for loading and preprocessing data.

- `preprocessing_image.py`: Handles the preprocessing of images, removing unnecessary borders, and resizing.

- `training.py`: Contains the training pipeline for the DR diagnosis model, using the EfficientNet architecture.

- `training_blend.py`: The left and right eye informations are blended, which infact resulted in better result.

- `utils.py`: Utility functions for model evaluation, saving and loading checkpoints, and making predictions.

## Project Stages

### Baseline Model
- Base line model uses a simple EfficientNet architecture 
- **Validation Score**: 0.55

### Preprocessing Images
- Low validation score suggested necessity of image preprocessing
- Removed black parts from images.
- **Validation Score**: 0.6 (a 0.05 improvement)
  ![Bildschirmfoto 2023-11-04 um 02 09 56](https://github.com/hrishikesh829370/Dibetic_Retinopathy_Diagnosis/assets/131910887/d3234471-c5be-4d8b-950a-f73756721bd3)

### Loss and Metric
- Considering to change the metric used.
- Initially used cross-entropy as the metric.
- Improved the loss function by switching to Mean Squared Error (MSE).
- **Validation Score**: 0.65 (a 0.05 improvement)

### Data Loader
- Attempted to create a balanced data loader, but it didn't work as expected.

### Heavy Data Augmentation
- Introduced heavy data augmentation.
- **Validation Score**: -0.02 (no improvement)

### Blending
- Blended information from the left and right eye.
- **Validation Score**: 0.65 (no change)

### Increase Image Resolution
- Increased image resolution from 300x300.
  - **Validation Score**: 0.736
- Further increased image resolution to 728x728.
  - **Validation Score**: 0.818

## Next Steps

The project has made significant progress in improving the model's validation score. Future steps may involve:

- Further data augmentation techniques.
- Exploring advanced loss functions.
- Fine-tuning the model architecture.

## Contributions and Collaboration

Contributions and collaboration are welcome to enhance the project and advance automated DR diagnosis.

## Get Involved

If you're interested in contributing or collaborating on this project, please feel free to reach out.

Let's work together to improve diabetic retinopathy diagnosis and make a difference!
