# Leaf Disease Detection 🌿

## Project Overview
This project focuses on developing a deep learning model to automatically classify plant leaves as healthy or infected with diseases. Early and accurate detection of plant diseases is crucial for proactive agricultural management, helping to ensure healthier crops and increased yields. This notebook demonstrates the entire process from data loading and preprocessing to model training, evaluation, and prediction.

## Dataset
The project utilizes the **Plant Disease Recognition Dataset** from Kaggle. This dataset contains images of plant leaves categorized into different classes:
-   **Healthy**: Images of healthy plant leaves.
-   **Powdery**: Images of leaves infected with Powdery Mildew.
-   **Rust**: Images of leaves infected with Rust.

The dataset is structured into `Train`, `Test`, and `Validation` directories, with subdirectories for each class.

## Model Architecture
A Convolutional Neural Network (CNN) is employed for image classification. The model architecture is a sequential model comprising:
-   **Input Layer**: Expects images of size (225, 225, 3).
-   **Convolutional Layers (Conv2D)**: Two layers with 32 and 64 filters respectively, using a (3,3) kernel size and 'relu' activation.
-   **Max Pooling Layers (MaxPooling2D)**: Two layers with a (2,2) pool size, following each convolutional layer to reduce spatial dimensions.
-   **Flatten Layer**: Converts the 2D feature maps into a 1D vector.
-   **Dense Layers**: Two fully connected layers. The first has 64 units with 'relu' activation, and the output layer has 3 units (corresponding to the three classes) with 'softmax' activation for multi-class classification.

## Training and Evaluation

### Data Augmentation
To improve model robustness and generalize better, `ImageDataGenerator` from Keras was used for data augmentation on the training set, including:
-   Rescaling pixel values to [0, 1].
-   Shear range (0.2).
-   Zoom range (0.2).
-   Horizontal flip.

### Training Parameters
-   **Optimizer**: Adam
-   **Loss Function**: Categorical Crossentropy
-   **Metrics**: Accuracy
-   **Epochs**: 5
-   **Batch Size**: 32

### Results
After 5 epochs, the model achieved the following performance:
-   **Training Accuracy**: Approximately 89.06%
-   **Validation Accuracy**: Approximately 88.33%
-   **Validation Loss**: Approximately 0.5053

The model demonstrated strong learning capabilities, with accuracy steadily increasing over epochs and a reasonable validation performance.

### Visualizations
-   **Accuracy Plot**: A plot showing training and validation accuracy over epochs indicates the model's learning progression and helps identify potential overfitting or underfitting.
-   **Sample Predictions**: The notebook includes a visualization of random test images with their true labels, predicted labels, and confidence scores, providing a qualitative assessment of the model's performance.

## Usage and Prediction
The notebook includes functions to:
-   Preprocess individual images for prediction.
-   Make predictions using the trained model.
-   Display the predicted class and its confidence.
-   Analyze top-k predictions with their probabilities for a deeper insight into the model's confidence across different classes.

## Conclusion
This project successfully demonstrates the application of deep learning for automated plant disease detection. The trained CNN model can accurately distinguish between healthy leaves and those affected by Powdery Mildew or Rust. This technology has significant potential to revolutionize agricultural practices by enabling early disease detection, leading to timely interventions, reduced crop losses, and more sustainable farming.
