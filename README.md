Download Link: https://assignmentchef.com/product/solved-a1-cv-basic-image-classification-a01651395
<br>
0.1 # Day and Night Image ClassifierThe day/night image dataset consists of 200 RGB color images in two categories: day and night. There are equal numbers of each example: 100 day images and 100 night images.We’d like to build a classifier that can accurately label these images as day or night, and that relies on finding distinguishing features between the two types of images!Note: All images come from the AMOS dataset (Archive of Many Outdoor Scenes).0.1.1 Import resourcesBefore you get started on the project code, import the libraries and resources that you’ll need.

0.2 Training and Testing DataThe 200 day/night images are separated into training and testing datasets.• 60% of these images are training images, for you to use as you create a classifier.• 40% are test images, which will be used to test the accuracy of your classifier.First, we set some variables to keep track of some where our images are stored:image_dir_training: the directory where our training image data is stored image_dir_test: the directory where our test image data is stored[2]: # Image data directories image_dir_training = “day_night_images/training/” image_dir_test = “day_night_images/test/”0.3 Load the datasetsThese first few lines of code will load the training day/night images and store all of them in a variable, IMAGE_LIST. This list contains the images and their associated label (“day” or “night”).For example, the first image-label pair in IMAGE_LIST can be accessed by index: IMAGE_LIST[0][:].[3]: # Using the load_dataset function in helpers.py# Load training dataIMAGE_LIST = helpers.load_dataset(image_dir_training)0.4 Visualize sample day and night images

[4]: Text(0.5, 1.0, ‘Shape: (700, 1280, 3)
Label: night’)

0.5 Construct a STANDARDIZED_LIST of input images and output labels.This function takes in a list of image-label pairs and outputs a standardized list of resized images and numerical labels.[5]: # Standardize all training images## TODO: Code the needed functions in the helpers file in order to return a␣ ,→standardized list.STANDARDIZED_LIST = helpers.standardize(IMAGE_LIST)0.6 Visualize the standardized dataDisplay a standardized image from STANDARDIZED_LIST.

Label [1 = day, 0 = night]: 1

1 Feature ExtractionCreate a feature that represents the brightness in an image. We’ll be extracting the average brightness using HSV colorspace. Specifically, we’ll use the V channel (a measure of brightness), add up the pixel values in the V channel, then divide that sum by the area of the image to get the average Value of the image.

1.0.1 Find the average brigtness using the V channelThis function takes in a standardized RGB image and returns a feature (a single value) that represent the average level of brightness in the image. We’ll use this value to classify the image as day or night.

Avg brightness: 119.6223[8]: &lt;matplotlib.image.AxesImage at 0x139703550&gt;

2 Classification and Visualizing ErrorIn this section, we’ll turn our average brightness feature into a classifier that takes in a standardized image and returns a predicted_label for that image. This estimate_label function should return a value: 0 or 1 (night or day, respectively).

2.0.1 Build a complete classifierComplete this code so that it returns an estimated class label given an input RGB image.

2.1 Testing the classifierHere is where we test your classification algorithm using our test set of data that we set aside at the beginning of the notebook!Since we are using a pretty simple brightess feature, we may not expect this classifier to be 100% accurate. We’ll aim for around 75-85% accuracy usin this one feature.2.1.1 Test datasetBelow, we load in the test dataset, standardize it using the standardize function you defined above, and then shuffle it; this ensures that order will not play a role in testing accuracy.

2.2 Determine the AccuracyCompare the output of your classification algorithm (a.k.a. your “model”) with the true labels and determine the accuracy.This code stores all the misclassified images, their predicted labels, and their true labels, in a list

Accuracy: 0.95Number of misclassified images = 12 out of 240

### Visualize the misclassified imagesVisualize some of the images you classified wrong (in the MISCLASSIFIED list) and note any qualities that make them difficult to classify.[13]: # Visualize misclassified example(s)## TODO: Display an image in the `MISCLASSIFIED` list## TODO: Print out its predicted label – to see what the image *was*␣ ,→incorrectly classified as5# Plot 3 images f, plots = plt.subplots(3, 1, figsize=(50,25)) for i in range(3):

[ ]: