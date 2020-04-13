<p align="center"><img src="img/eyes.jpg" title="Look At Me!"></a></p>  



# look\_at\_me  

Face detection application utilizing OpenCV.


## Context

This application is useful in analyzing ohotos or even video streams for security systems.  Rather than have a human sift through hours of video to see if a person has entered an unauthorized area, process the data through this application. 

## Table of Contents

- [Context](#Context)
- [Content](#Content)
- [Data Preparation](#Data-Preparation)
- [Analysis](#Analysis)
- [Model Evaluation](#Model-Evaluation)
- [Illustrations](#Illustrations)
- [Deployment](#Deployment)
- [Data Sources](#Data-Sources)
- [Next steps](#Next-steps)
- [Citations](#Citations)

## Content

My dataset is a collection by Tufts University for researching emotion detection for facial recognition technology.  Tufts Face Database is the latest, most comprehensive, large-scale (over 10,000 images, 74 females + 38 males, from more than 15 countries with an age range between 4 to 70 years old) face dataset that contains 6 image modalities: visible, near-infrared, thermal, computerized sketch, a recorded video, and 3D images.  I will be specifically using the TDRGBE and TDIRE image datasets, split for training and testing.

TDRGBE: The images were captured using a NIKON D3100 camera. Each participant was asked to pose with a neutral expression, a smile, eyes closed, exaggerated shocked expression, and finally wearing sunglasses.

TDIRE: Images were captured using a FLIR Vue Pro camera with participants posing as in the TDRGBE dataset.  

## Data-Preparation

There are basically three stages for my project, each of which will utilize the OpenCV library: 1) convert the image to grayscale, 2) search for a face, and 3) draw a box around the face.  I will train a cascade classifier (from OpenCV) and use the Viola & Jones method to search for and draw a rectangle around the face.  

In order to protect the data, I will implement EncryptedPickle to protect the model and data while in use.  The database content and metadata will be encrypted with the SQLCipher extension.

## Modeling

This will be a supervised learning model as the data in my dataset is tagged.  I will choose a statistical approach to modelling and therefore fit a PCA model initially.  I will add a Feed Forward Neural Network, to increase model accuracy. Then I will test a Convolutional Neural Network to increase the model efficiency.  

## Analysis


## Model-Evaluation

- Cascade Classifier
- Accuracy: %
- Recall: %
- The most significant features include: .  

I will initially split the data from the Cohn-Kanade dataset into train and test portions.  After the model is trained, I will generate classification reports to test the accuracy while tuning the model.  After the model is trained, I will refit the data to the full Cohn-Kanade dataset and test against the unseen data in the Tufts Face Database.  If possible, I’d like to test against both the TDRGBE and the matching infrared dataset TDIRE.


## Illustrations 

![Place Holder](img/lucy.jpeg)  

## Deployment  

The model will be deployed as a Flask app that users can upload a previously taken photo or by activating a web cam to send their picture.  The app will then use the model to predict the emotion of the person.  As the model is used by others, their data can be saved, tagged, and then used as future training data.


## Data-Sources

[![Tufts Face Database][3]][4]

[3]: img/tufts_university.png 
[4]: http://tdface.ece.tufts.edu "Tufts Face Database: Request permission to use this dataset!!!"  


## Next-steps  
 

## Citations

Any publication using this database must reference to this

- Website: http://tdface.ece.tufts.edu/, (Check note)

- Paper: Panetta, Karen, Qianwen Wan, Sos Agaian, Srijith Rajeev, Shreyas Kamath, Rahul Rajendran, Shishir Rao et al. "A comprehensive database for benchmarking imaging systems." IEEE Transactions on Pattern Analysis and Machine Intelligence (2018).

For any enquires regarding the Tufts Face Database, contact: panettavisonsensinglab@gmail.com

