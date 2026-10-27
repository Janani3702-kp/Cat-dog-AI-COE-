# CNN-Based Dog and Cat Image Classification

## Project Overview

This project implements a Convolutional Neural Network (CNN) using Python, TensorFlow, and Keras to classify images into two categories: cats and dogs.

The CNN automatically learns visual features such as edges, shapes, textures, and patterns from images to distinguish between the two animal categories.

## Objectives

- Load the Cats vs Dogs image dataset.
- Preprocess and resize images.
- Normalize image pixel values.
- Build a CNN with three convolutional layers.
- Train the model to classify cats and dogs.
- Evaluate model performance using validation metrics.
- Visualize training accuracy and loss.
- Display sample predictions with actual labels.

## Technologies Used

- Python
- TensorFlow
- Keras
- TensorFlow Datasets
- Matplotlib
- `importlib_resources`

## Dataset

The project uses the Cats vs Dogs dataset available through TensorFlow Datasets.

The notebook loads the dataset and divides the available data into training and validation subsets.

**Dataset Configuration**

- Dataset: Cats vs Dogs
- Training Split: 80%
- Validation Split: 20%
- Image Size: 128 × 128 pixels
- Image Channels: 3 (RGB)
- Batch Size: 32
- Classification Type: Binary Classification

The dataset is downloaded automatically when the notebook loads it for the first time. An internet connection and sufficient storage are required.

## Model Architecture

1. **Input Layer:** Accepts RGB images of size 128 × 128 × 3.
2. **Convolutional Layer 1:** Uses 32 filters with a 3 × 3 kernel and ReLU activation.
3. **Max Pooling Layer 1:** Reduces the spatial dimensions of the feature maps.
4. **Convolutional Layer 2:** Uses 64 filters with a 3 × 3 kernel and ReLU activation.
5. **Max Pooling Layer 2:** Reduces the feature-map dimensions.
6. **Convolutional Layer 3:** Uses 128 filters with a 3 × 3 kernel and ReLU activation.
7. **Max Pooling Layer 3:** Further reduces the spatial dimensions.
8. **Flatten Layer:** Converts feature maps into a one-dimensional vector.
9. **Dense Layer:** Contains 128 neurons with ReLU activation.
10. **Dropout Layer:** Uses a dropout rate of 0.5 to help reduce overfitting.
11. **Output Layer:** Uses one neuron with sigmoid activation to predict the probability of the positive class.

## Training Configuration

- Optimizer: Adam
- Loss Function: Binary Cross-Entropy
- Evaluation Metric: Accuracy
- Number of Epochs: 10
- Batch Size: 32
- Image Dimensions: 128 × 128 × 3
- Pixel Normalization: Values scaled to the range 0–1

## Project Workflow

1. Import the required libraries.
2. Load the Cats vs Dogs dataset using TensorFlow Datasets.
3. Resize the images to 128 × 128 pixels.
4. Normalize the image pixel values.
5. Divide the dataset into training and validation subsets.
6. Shuffle and batch the training data.
7. Build the CNN with three convolutional layers.
8. Compile the model using Adam and binary cross-entropy.
9. Train the model for the specified number of epochs.
10. Evaluate the model on the validation dataset.
11. Plot training and validation accuracy.
12. Plot training and validation loss.
13. Display sample images with their predicted and actual classes.

## Installation

Install the required dependencies:

```bash
pip install tensorflow tensorflow-datasets matplotlib importlib_resources
```

## How to Run

1. Open the notebook in Google Colab or Jupyter Notebook.
2. Ensure that internet access is available for downloading the dataset.
3. Run the notebook cells from top to bottom.
4. Review the dataset preprocessing steps.
5. Observe the CNN model summary.
6. Monitor training and validation accuracy.
7. Examine the accuracy and loss graphs.
8. Review the sample classification predictions.

**Tip:** If available, use a GPU runtime in Google Colab to speed up model training.

## Output

The notebook produces the following outputs:

- Dataset loading and preprocessing results
- CNN architecture summary
- Training progress over the specified epochs
- Training and validation accuracy graph
- Training and validation loss graph
- Validation loss and accuracy
- Sample images with predicted and actual labels

The final accuracy depends on the training process, dataset preprocessing, and runtime environment.

## Limitations

- The model performs only binary classification between cats and dogs.
- Training can require significant time and memory.
- Model performance depends on image quality and dataset representation.
- Training for a small number of epochs may limit classification performance.
- The model may not generalize well to images that differ significantly from the training data.

## Future Enhancements

- Apply data augmentation using image flips, rotations, and zooming.
- Add early stopping and model checkpointing.
- Use transfer learning with MobileNetV2 or another pretrained CNN.
- Evaluate precision, recall, F1-score, and a confusion matrix.
- Save the trained model for future use.
- Build a web interface that allows users to upload images and receive predictions.
