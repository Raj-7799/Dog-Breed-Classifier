# Dog Breed Classifier

[//]: # (Image References)

[image1]: ./images/sample_dog_output.png "Sample Output"
[image2]: ./images/vgg16_model.png "VGG-16 Model Keras Layers"
[image3]: ./images/vgg16_model_draw.png "VGG16 Model Figure"


## Project Overview

The project focuses on building a pipeline to process real-world, user-supplied images. Given an image of a dog, the algorithm identifies the canine's breed.

The algorithm implementation is done using CNN models for classification. 

## Project Setup

### Steps

1. Download the [dog dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/dogImages.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/dogImages`. 
2. Download the [human dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/lfw.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/lfw`.  If you are using a Windows machine, you are encouraged to use [7zip](http://www.7-zip.org/) to extract the folder. 
3. Donwload the [VGG-16 bottleneck features](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/DogVGG16Data.npz) for the dog dataset.  Place it in the repo, at location `path/to/dog-project/bottleneck_features`.
4. Obtain the necessary Python packages, and switch Keras backend to Tensorflow.  
	
	For __Mac/OSX__:
	```
		conda env create -f requirements/aind-dog-mac.yml
		source activate aind-dog
		KERAS_BACKEND=tensorflow python -c "from keras import backend"
	```

	For __Linux__:
	```
		conda env create -f requirements/aind-dog-linux.yml
		source activate aind-dog
		KERAS_BACKEND=tensorflow python -c "from keras import backend"
	```

	For __Windows__:
	```
		conda env create -f requirements/aind-dog-windows.yml
		activate aind-dog
		set KERAS_BACKEND=tensorflow
		python -c "from keras import backend"
	```
6. Open the notebook and follow the instructions.
	
	```
		jupyter notebook dog_app.ipynb
	```

## Results
1. Using a custom CNN architecutre with 5 sets of Convolutional layers : trainning accuracy 27.8%, testing accuracy 26.9%
2. Transfer learning using ResNet50 : trainning accuracy 99.8%, testing accuracy 84.2%


## Detection and recognition at play

### Sample 1 : Irish Water Spaniel
### The algorithm detects that the image contains a dog and the CNN correctly recognizes the dog's breed.

[Irish Water Spaniel]: ./images/Correct_Matches.png "VGG16 Model Figure"

### Sample 2 : Labroader Retriever
### The algorithm detects that the image contains a dog and the CNN correctly recognizes the dog's breed.

[Labroader Retriever]: ./images/Correct_Matches_2.png "VGG16 Model Figure"


### Sample 3 : Human Subject
### The algorithm detects that the image contains a human and the CNN tries to find a dog's breed resembling the human.

[Human Subject]: ./images/Human_example_1.png "VGG16 Model Figure"


### Sample 4 : Human Subject
### The algorithm detects that the image contains a human and the CNN tries to find a dog's breed resembling the human.

[Human Subject 2]: ./images/Human_example_2.png "VGG16 Model Figure"


### Sample 5 : Picture of cat resembling dog
### The detection algorithm thinks that the picture contains a dog. Furthermore, the CNN finds a dog breed resembling the cat.

[Incorrect Sample]: ./images/Algorithm_Incorrect.png "VGG16 Model Figure"

### Sample 6 : Picture of dog outside of dataset
### The algorithm detects that the image contains a dog but the CNN is not able to find it's corresponding breed as it belongs outside the dataset.

[Incorrect Sample]: ./images/Algorithm_Miss.png "VGG16 Model Figure"
