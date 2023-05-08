# P300-classifier-evaluation

*This work was done for the VIRTUAL BR41N.IO HACKATHON Spring School 2023.*

## Purpose

The following project aimed to conduct an evaluation of different machine learning (ML) and deep learning (DL) classifiers for P300 signals in a target vs non-target paradigm. 

P300 signals are brainwave responses measured using electroencephalography (EEG). They occur around 300 milliseconds after a stimulus is presented to a person, and are associated with cognitive processes like attention, memory, and decision-making. They have vast applications in brain-computer interfaces, as they allow for a computer to interpret the selection of the user through an artifical inteligence (AI) classifier.

We worked with a dataset of two subject, which consists of 4 registers each:

* 2 low accuracy signals
* 2 high accuracy signals

The data aquisition was done with a 256 Hz sample rate. 3 conditions indicated by trigger data:

* Distractor (-1)
* Nontarget (1)
* Target (2)

## Pre-processing

MNE library is used to filter and segment data. Normalization is done with scikit-learn library.

* Converting units from microvolts to volts
* Remove offset through substracting the mean
* High pass filter of 1 Hz
* ICA Filter
* Segmentation
* Normalization

## Processing

Scikit-learn library is used to apply machine learning algorithms, and TensorFlow library is used to apply deep learning algorithms. The following classifiers are implemented:

* Linear Discriminant Analysis (LDA)
* Decission Forrest
* Multi-layer perceptron (MLP)
* Convolutional neural network (CNN)

All classifiers are evaluated through accuracy. LDA and decission forrests are also evaluated with confusion matrix, while MLP and CNN are also evaluated with loss.
