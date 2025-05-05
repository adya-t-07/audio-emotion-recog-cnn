# audio-emotion-recog-cnn
Classifies audio samples from the RAVDESS dataset into 8 emotions using a CNN model
A google drive folder containing all the data is uploaded to the code

A class called AudioData is created to perform all necessary actions for the data to become inputted to the cnn
-this includes
    1)Extracting the emotion from the file name
    2)Using librosa to load the audio files and set parameters to ensure that all the files have equal length 
    3)Creating spectograms and normalizing the data 
    4)Returning tensors and labels to be passed to the model
    
A class called CNN carries out all the blocks of a regular ConvNet
-one block includes a convolution layer, an activation(ReLU) layer and a pooling layer
-after this we have 2 fully connected layers that map on to 8 neurons, showing the likelihood of the 8 emotions

Random samples are chosen from the dataset to be a part of the training dataset or testing dataset
I have not done a regular training-testing split as it was too much computational load to process the whole dataset 
An object of the CNN class is created and the optimizer and criterion are set up to use in the training loop 
Here we choose the learning rate of backpropagation and what loss function to use

In the training loop the training data goes through 10 epochs, and we evaluate the loss function after each epoch 

To evaluate the model's performance we run the test data through the model to get the prediction
The predictions and true values are compared using the accuracy metric and by creating a confusion matrix
