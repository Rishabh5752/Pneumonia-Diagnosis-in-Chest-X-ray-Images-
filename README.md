# Pneumonia-Diagnosis-in-Chest-X-ray-Images
#Dataset
Description: The dataset is organized into 3 folders (train, test, val) and contains subfolders for each image category (Pneumonia/Normal). There are 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal).

Chest X-ray images (anterior-posterior) were selected from retrospective cohorts of pediatric patients of one to five years old from Guangzhou Women and Children’s Medical Center, Guangzhou. All chest X-ray imaging was performed as part of patients’ routine clinical care.

For the analysis of chest x-ray images, all chest radiographs were initially screened for quality control by removing all low quality or unreadable scans. The diagnoses for the images were then graded by two expert physicians before being cleared for training the AI system. In order to account for any grading errors, the evaluation set was also checked by a third expert.

#Models
CNN 
The CNN consisted of the following layers:

Conv2D layer: Applies 16 filters of size 3x3 to the input images with a ReLU activation function.
BatchNormalization layer: Normalizes the activations of the previous layer.
MaxPooling2D layer: Performs max pooling with a pool size of 2x2, reducing the spatial dimensions by half.
Conv2D layer: Applies 32 filters of size 3x3 with a ReLU activation function.
MaxPooling2D layer: Performs max pooling with a pool size of 2x2.
Conv2D layer: Applies 64 filters of size 3x3 with a ReLU activation function.
MaxPooling2D layer: Performs max pooling with a pool size of 2x2.
Flatten layer: Flattens the output from the previous layer into a 1D vector.
Dense layer: Consists of 512 neurons with a ReLU activation function.
Dense layer: Consists of a single neuron with a sigmoid activation function, representing the output class probabilities.

Additionally, early stopping was used in the model training process to prevent overfitting. The EarlyStopping callback was applied, monitoring the validation loss and stopping the training if the validation loss did not improve for 5 consecutive epochs. This technique helps to avoid overfitting by stopping the training process when the model's performance on the validation data stops improving, thus preventing excessive training that may lead to overfitting.

Inception V3
I utilized the Inception V3 architecture to develop a deep learning model for scanning X-ray images of patients with pneumonia. The Inception V3 model is known for its effectiveness in image classification tasks. By leveraging its convolutional layers and advanced features, the model can analyze X-ray images and identify patterns associated with pneumonia.

To prevent overfitting and optimize the model's performance, I employed early stopping. This technique stops the training process if the validation loss does not improve for a specified number of epochs, helping to prevent excessive training and potential overfitting. By combining the power of Inception V3 with early stopping, I aimed to create a robust and accurate deep learning model for pneumonia detection in X-ray images.
