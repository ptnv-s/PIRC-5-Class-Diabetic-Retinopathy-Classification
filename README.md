# PIRC-5-Class-Diabetic-Retinopathy-Classification

This project aims at acheiving well-calibrated reliable model predictions for 5 Class PIRC Diabetic Retinopathy Classification using the APTOS 2019 Blindness Detection Dataset. The Dataset includes 19,00 input samples of retinal imagery available for training using fundus photography. We utilise 90% of the photos (3,302 images) as a train set and the remaining 10% (360 images) as a secondary validation set. These images are sub-divided into five classes rated on a scale of 0 to 4 depending on the severity of the Diabetic Retinopathy condition. 

class 0 - No DR

class 1 - Mild

class 2 - Moderate

class 3 - Severe

class 4 - Proliferative DR

Two steps of training are applied to the end-to-end model architecture. Four distinct baseline models are trained in the initial stage to classify the disease. We employ Test-Time-Augmentation, a method for improving picture classification performance, in the second step. The pre-trained models received these augmented pictures as input, and they subsequently generated individual classification outputs. 

We employed four models for ensembling. Every model utilised was of ResNet-50 architecture, with the final linear layer of the network using a sigmoid activation function. During training and evaluation each RGB input picture is normalised and enlarged to a pixel size of (512,512). We use stochastic gradient descent optimization with 0.0001 learning rate. We also apply the weighted Cross Entropy Loss to account for the substantial class imbalance in the datasets. 


The DR grading performance is evaluated using Cohen’s quadratic weighted Kappa (κ) to measure the inter-rater agreement between raters in ordinal multi-class problems. This metric penalises rating inconsistencies, which are quadratically correlated with the gap between the prediction and the actual data.
