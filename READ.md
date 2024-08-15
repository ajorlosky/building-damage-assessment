# Building Damage Classification

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

