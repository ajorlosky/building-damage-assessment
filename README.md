# Building Damage Classification

Various natural disasters frequently occur every year. These disasters often tear through
civilization whether that be busy cities or rural towns. In order to provide the most effective aid
post-disaster, a damage assessment is mandatory. Understanding the magnitude of the damage is
an important step to see how much aid is needed and which areas need the most attention.
Traditionally, in order to get these assessments, people are sent onsite, manually going around
and checking each building. This method is rather crude as it puts people at risk of lingering
damages (i.e. damaged power lines) in order to gather information. Furthermore, the act of
checking each building one by one is very time consuming and delays the time for the
subsequent aid. Ultimately, being able to scan an area and quickly classify the extent of damage
in specific areas can enable communities to better respond to natural disasters in a timely
manner. Our design takes in satellite images along with the segmented building locations and
classifies the damage level that those buildings sustained during the disaster. The goal of our
model would be for disaster relief organizations to have the ability to use our model, and
hopefully provide valuable insight into where the damage is concentrated.
A potential workflow may include relief workers feeding the data from an overhead
camera into a localization model in order to locate all the buildings in each image. Then, the
images with located buildings could be used as an input in our model in order to assess the
damage level of the buildings.

Our code utilizes machine learning techniques in order to perform damage level
classification on those buildings, placing buildings into categories based on the level of damage
they accrued. We assess the precision of each model using accuracy and F1 scores. In the
xView2 AI Challenge [1], an open challenge to see who’s model could identify buildings and
rate the amount of damage the best, IBM announced that the best submission achieved an F1
score of 66% for damage classification. We attempted to get similar results as we built our
models and performed various experiments throughout the semester.
The final product of our project would be a software model which can classify the
damage levels of a building. For our development we used Google Colab as our programming
environment as it allows for access to GPU resources for training the model. If our model was to
transition into a fully deployed application, then it would be beneficial to have dedicated
hardware, specifically GPUs so that the training of the model can be done quickly and efficiently.

### Google Colab Project Code
This project is broken down into a variety of Google Colab scripts meant to perform building damage assessment of satellite images from the XView2 Dataset (see Report references). For more information on each component, see the linked titles or the individual scripts in the Code folder. 

## 1. [SVM Classification](https://colab.research.google.com/drive/1Xv0T5Q3IolgD50Do03KvmscLDTOxDXDO?usp=drive_link)

The goal of this file is to use a Support Vector Machine (SVM) to classify images. To properly run this code:
- Run all the cells before the “Gather Image” cells.
- Pick one of the “Gather Images” cells based on the test you want to try.
- Run one of the create train and test split cells.
- Finally, run the Part 1 and 2 code to train the SVM and test the SVM model.

## 2. [Siamese Network](https://colab.research.google.com/drive/1-LfSyWRwwR74Iw2eDfb-moA8RomLzftj?usp=drive_link)

This file aims to run a Siamese model over the dataset to achieve higher accuracy. The file can be executed with the Google Colab “Run All” function. The Siamese model:
- Gathers images based on a disaster name.
- Trains on these building images.
- Outputs a binary classification indicating whether the building had no damage or some level of damage.

## 3. [Preprocessing](https://colab.research.google.com/drive/1gacB6GPYRWoaggmZRLPQQw99yDcClkMY?usp=drive_link)

This file covers the interaction with the dataset and preprocessing actions. Run the cells in order:
- The “Image Directory” cell takes around 10 hours to run. It can be skipped since the dataset is already cleaned.
- Later cells produce visualizations of the dataset in the form of histograms.

## 4. [KNN](https://colab.research.google.com/drive/1xo27PUgMxtvt11PTs7V-OVwtv-UUtTSg?usp=drive_link)

The purpose of this file is to try the classical method of K-Nearest-Neighbors (KNN) classification on our dataset. To run properly:
- First, run all of the Part 0 code.
- Then, run the first two cells in Part 1 to gather the images as necessary.
- Choose either the 3rd or 4th cell to run; one will create the testing split with all categories even, while the other will not consider the damage levels in testing set creation.
- Then run Part 2 to execute the KNN model.

## 5. [CNN Edge Detection](https://colab.research.google.com/drive/1ldETNEfj6jPWpCt7wk0poVrHQwdoTBQw?usp=drive_link)

This file’s goal is to utilize a Convolutional Neural Network (CNN) as well as edge detection to classify our data. The CNN aims to:
- Take in an image of the edges of a building.
- Determine the damage level of the building.

To run, this file can be executed using the Google Colab “Run All” functionality. The code will:
- Grab the images of the specified disaster.
- Split the data based on an even distribution of the damage classifications.
- Train the CNN on the edge-detected images.

## 6. [Crop Buildings](https://colab.research.google.com/drive/1d6oOyVwrvMLlTqEEASa8ZFbPT9lotU0d?usp=drive_link)

This file focuses on processing the different buildings in the images. Since our models aim to classify the damage level of individual buildings, this file shows:
- How to crop out buildings before passing them into our models as data.
- The initial exploration and how our cropping functions work.

This file can be run using the Google Colab “Run All” functionality.

## 7. [Building Classification CNN](https://colab.research.google.com/drive/1goyj3vN_VYUGtJsJccUAATfvGSar9tVb?usp=drive_link)

This file runs our data on a CNN model. The goal is to use the post-disaster image of the building to determine how damaged it got. To run:
- Run the non-numbered cells in Part 0.
- Choose one of the gathering cells based on the test you want to run.
- Pick the train/test split you want to use.
- Run Part 1, Part 2, and Part 3 to see how the data performed in the CNN.
- Part 5 is the basis for the demo shown in class.

## 8. [Demo](https://colab.research.google.com/drive/1MhsgUo9HMc6Ts0ji_zjtLybBsQlDg3oK?usp=sharing)

This file runs an interactive demo allowing a user to select a specific disaster type and model for training and testing on building damage assessment. This demo represents a potential product for a user of our application to:
- Classify damage of all buildings in a satellite image using any of our methods: CNN, Edge Detection CNN, Siamese Neural Network, SVM, or KNN.
- KNN has shown the best performance, but all methods are promising for different use cases.

