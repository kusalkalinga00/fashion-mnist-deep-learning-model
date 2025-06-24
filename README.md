# Fashion MNIST Image Classification

This project demonstrates building and training a simple neural network to classify images from the Fashion MNIST dataset.

## Dataset

The Fashion MNIST dataset is a dataset of 70,000 grayscale images of 10 fashion categories. The dataset is split into 60,000 training images and 10,000 testing images. Each image is 28x28 pixels.

The 10 classes are:
- T-shirt/top
- Trouser
- Pullover
- Dress
- Coat
- Sandal
- Shirt
- Sneaker
- Bag
- Ankle boot

## Project Steps

1.  **Load Data**: The Fashion MNIST dataset is loaded using `fetch_openml` from `sklearn.datasets`.
2.  **Explore Data**: The shape of the data and target variables are inspected. Sample images for each class are displayed to visualize the dataset.
3.  **Preprocess Data**: The target variable `y` is converted to integer type. The pixel values of the images in `x` are scaled by dividing by 255.0 to normalize them between 0 and 1.
4.  **Split Data**: The data is split into training and testing sets using `train_test_split` with a test size of 20%.
5.  **Build Model**: A sequential neural network model is built using TensorFlow/Keras. The model consists of:
    - A `Flatten` layer to flatten the 28x28 images into a 784-element vector.
    - Two `Dense` layers with ReLU activation for hidden layers (128 and 64 units respectively).
    - A final `Dense` layer with softmax activation for the output layer (10 units, one for each class).
6.  **Define Callback**: A custom Keras callback `myCallback` is defined to stop training if the validation accuracy drops more than 1% below the training accuracy.
7.  **Compile and Train Model**: The model is compiled with the Adam optimizer, sparse categorical crossentropy loss, and accuracy as the metric. The model is then trained on the training data for 10 epochs with the test data used for validation, and the custom callback is included.
8.  **Visualize Training History**: The training and validation accuracy over epochs are plotted to visualize the model's performance during training.
9.  **Save Model**: The trained model and the list of class names are saved using `pickle`.
10. **Load Model**: The saved model is loaded using `pickle`.
11. **Evaluate Model**: The loaded model is evaluated on the test set to determine its loss and accuracy.
12. **Visualize Predictions**: A few random images from the test set are selected, and their true labels and the model's predicted labels are displayed.

## Requirements

-   `openml`
-   `scikit-learn`
-   `matplotlib`
-   `pandas`
-   `numpy`
-   `tensorflow`

You can install the required libraries using pip:
