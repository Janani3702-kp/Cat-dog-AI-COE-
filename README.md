CNN-Based Dog and Cat Image Classification
A Convolutional Neural Network (CNN) built with TensorFlow and Keras to classify images as cats or dogs. The notebook uses the cats_vs_dogs dataset from TensorFlow Datasets, preprocesses images, trains a CNN with three convolutional layers, evaluates performance, and visualizes predictions.

Project Overview
The goal of this project is to demonstrate how a CNN can learn visual features from images and perform binary image classification.

Objectives
- Load the Cats vs Dogs image dataset using TensorFlow Datasets.
- Resize images to a consistent size and normalize pixel values.
- Build a CNN with three convolutional layers.
- Train the model to distinguish cats from dogs.
- Evaluate the model using validation loss and accuracy.
- Plot training and validation accuracy/loss.
- Display sample images with predicted and actual labels.

Technologies Used
- Python
- TensorFlow
- Keras
- TensorFlow Datasets (tensorflow-datasets)
- Matplotlib
- importlib_resources

Dataset
The notebook loads the cats_vs_dogs dataset from TensorFlow Datasets:
tfds.load(
    "cats_vs_dogs",
    split=["train[:80%]", "train[80%:]"],
    as_supervised=True,
    with_info=True
)
- Dataset: Cats vs Dogs
- Split: 80% training and 20% validation
- Image size: 128 × 128 pixels
- Color channels: 3 (RGB)
- Batch size: 32
- Labels: Cat and Dog

TensorFlow Datasets downloads the dataset the first time the notebook runs, so an internet connection and enough disk space are required.
CNN Architecture
Layer	Configuration
Input	128 × 128 × 3 RGB image
Convolution 1	32 filters, 3 × 3 kernel, ReLU
Max Pooling 1	2 × 2
Convolution 2	64 filters, 3 × 3 kernel, ReLU
Max Pooling 2	2 × 2
Convolution 3	128 filters, 3 × 3 kernel, ReLU
Max Pooling 3	2 × 2
Flatten	Converts feature maps to a vector
Dense	128 neurons, ReLU
Dropout	0.5
Output	1 neuron, Sigmoid


Training Configuration
- Optimizer: Adam
- Loss function: Binary cross-entropy
- Metric: Accuracy
- Epochs: 10
- Batch size: 32
- Image normalization: Pixel values scaled to the range 0–1

Workflow
1. Install and import the required packages.
2. Load the Cats vs Dogs dataset.
3. Resize each image to 128 × 128 and normalize its pixel values.
4. Shuffle and batch the training data.
5. Build the three-convolutional-layer CNN.
6. Compile the model with Adam and binary cross-entropy.
7. Train for 10 epochs and monitor validation performance.
8. Evaluate the model on the validation dataset.
9. Plot training/validation accuracy and loss.
10. Show sample predictions beside their actual labels.

Installation
Install the dependencies in a Python environment or notebook:
pip install tensorflow tensorflow-datasets matplotlib importlib_resources

How to Run
1. Download or clone this project.
2. Open Untitled23 (2).ipynb in Google Colab, Jupyter Notebook, or JupyterLab.
3. Ensure the runtime has internet access so TensorFlow Datasets can download the dataset.
4. Run the notebook cells from top to bottom.
5. Review the model summary, validation metrics, plots, and sample predictions.
Tip: In Google Colab, select a GPU runtime if available to speed up CNN training.

Evaluation and Output
The notebook displays:
- Model architecture and parameter counts
- Validation loss
- Validation accuracy
- Training and validation accuracy curves
- Training and validation loss curves
- Five sample images with predicted and actual classes

The final accuracy depends on the training run, software environment, and dataset processing. Refer to the metrics produced by your own notebook execution; no fixed accuracy is guaranteed.
Repository Structure
project-folder/
├── README.md
└── Untitled23 (2).ipynb
You may rename the notebook to a simpler filename such as dog_cat_cnn.ipynb and update the filename above to match.

Learning Outcomes
- Understand the basic CNN image-classification pipeline.
- Learn the roles of convolution, max pooling, flattening, dense layers, and dropout.
- Prepare image data with resizing and normalization.
- Train and evaluate a binary classifier using TensorFlow/Keras.
- Interpret accuracy and loss curves.
- Inspect individual predictions and compare them with ground-truth labels.

Future Improvements
- Add data augmentation such as random flips and rotations.
- Use early stopping and model checkpoints.
- Compare results with transfer learning models such as MobileNetV2.
- Add a confusion matrix, precision, recall, and F1-score.
- Save the trained model and provide a function to predict a new uploaded image.
