# Face-Classification-and-Verification-Using-Convolutional-Neural-Networks

Given an image of a person's face, the task of classifying the ID of the face is known as **face classification**.
Whereas the problem of determining whether two face images are of the same person is known as **face
verification** and this has several important applications.

## Datset 

The data contains face images of size 32 by 32. For classification, we used human face images. 
For verification, given two images, we need to calculate the similarity score
for those images using the embeddings generated by our classification network.

## Face Classification
An input to your system is a face image and you have to predict the ID of the face. The true face image
ID will be present in the training data and so the network will be doing an N-way classication to get the
prediction.

## Face Verification

An input to your system is a trial, that is, a pair of face images that may or may not belong to the same
person. Given a trial, your goal is to output a numeric score that quanties how similar the faces of the two
images appear to be. On some scale, a higher score will indicate higher condence that the faces in the two
images are of the same person.

## Architecture

In this work , we used MobileNetV2 architecture which consists of Depthwise Seperable Convolutions, 
Linear Bottlenecks and Inverted residual blocks. 

# Evaluation of Verification Task
Intuitively, facial features vary extensively across people. Out main task is to train a CNN model to extract
and represent such important features from a person. These extracted features will be represented in a
fixed-length vector of features, known as a **face embedding**. Given two face embeddings,cosine similarity to
evaluate how close the faces are.

## System Evaluation

##System Evaluation
Given similarity scores for many trials, some threshold score is needed to actually accept or reject pairs as same-person pairs
(i.e., when the similarity score is above the threshold) or different-person pairs (i.e., when the score is
below the threshold), respectively. For any given threshold, there are four conditions on the results: some
percentage of the different-person pairs will be accepted (known as the false positive rate), some percentage
of the same-person pairs will be rejected (known as the false rejection rate), some percentage of the different-
person pairs will be rejected (known as the true negative rate), and some percentage of the same-person pairs
will be accepted (known as the true positive rate).

The Receiver Operating Characteristic (ROC) curve is created by plotting the True Positive Rate (TPR)
against the False Positive Rate (FPR) at various threshold settings 1. The Area Under the Curve (AUC) for
the ROC curve is equal to the probability that a classifier will rank a randomly chosen similar pair (images
of same people) higher than a randomly chosen dissimilar one (images from two different people) (assuming
'similar' ranks higher than 'dissimilar' in terms of similarity scores).


## Results
For the face classification task, the model achieved **72%** classification accuracy


For the face verification task, the model achieved **94.27 AUC**