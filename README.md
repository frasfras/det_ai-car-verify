# damage-car-verify

check Car damage with  Determined.ai

Project Objective

Verify car damage images with  determined.ai|
Build an automated and effective system that verifies customer photo uploads.
 Collect Car damage dataset to train classifier on the Determined.ai platform This dataset would be used to train a use a pre-trained CNN to extract features from the images and then train a classifier on those features.
 
Data Sample
Make your own copy of this <a href='https://docs.google.com/spreadsheets/d/1_AI5s5mU1L5a4oQKEguKv7zlXKHBgeD3OTjonpwmLxk/edit#gid=0'>spreadsheet</a>  with insurance claims that we’ve made. The spreadsheet includes information on each claim. Most importantly, it contains a link to a photo on local folder for each claim. 
You can also create your own spreadsheet that includes a photo for each claim in local folder. This photo must have a local dataset so the determined ai classification model can use it.

url	-Type of damage
bumper_dent.png -	bumper_dent

url	Type of damage
bumper_dent.png 	bumper_dent

![bumper dent](https://user-images.githubusercontent.com/65541080/232556800-f9acbe49-6bc7-4da2-ae6a-ce402e8df02d.png)

Model Architecture

Our model architecture use a pre-trained CNN to extract features from the images and then train a classifier on those features. load the pre-trained VGG16 model (excluding the top layer) from Keras and use it to extract features from each image in the dataset. We then concatenate these features into a numpy array, and the labels are stored in another numpy array. After splitting the data into training and testing sets, we define and train a simple classifier using Keras, which takes the extracted features as input and outputs a binary classification for the type of damage. Finally, we evaluate the accuracy of the classifier on the testing set.

How to Run the Training Job

pip Install the Determined.ai in google colab. Clone this repository .Prepare your training data. This includes downloading the CSV file  , downloading the images from the folder repo, and preprocessing the images as needed (e.g. resizing, normalization). <a href='https://docs.google.com/spreadsheets/d/1_AI5s5mU1L5a4oQKEguKv7zlXKHBgeD3OTjonpwmLxk/edit#gid=0'> create your own copy of this spreadsheet</a> that includes a name of photo for each claim in local folder. This photo must have a local dataset so the determined ai classification model can use it.

You will use that photo in a determined classification model.
 pip install --user virtualenv. 
 Set up a Determined AI cluster. You can follow the instructions on their website to set up a cluster on your preferred infrastructure.

Create a keras model definition. This defines the neural network architecture and training logic. You can define your model using the keras framework and include the necessary layers for your image classification task.

Create a Determined AI experiment. This is where you define the hyperparameters, resources, and other settings for your training run. You can use the Determined AI web UI or command-line interface to create the experiment and specify the PyTorch model definition.

Train the model. Once the experiment is created, you can start the training process on the Determined AI cluster.

Best Metrics Screenshot



Evaluation Metrics

We then load the pre-trained VGG16 model (excluding the top layer) from Keras and use it to extract features from each image in the dataset. We then concatenate these features into a numpy array, and the labels are stored in another numpy array. After splitting the data into training and testing sets, we define and train a simple classifier using Keras, which takes the extracted features as input and outputs a binary classification for the type of damage. Finally, we evaluate the accuracy of the classifier on the testing set.

Evaluation Results
To test the model, you can use the predict method of the trained classifier to predict the class labels for a new set of images.
After training  models , we were able to predict to 0.3333333333333333 accuracy
