# Automatic Speaker Recognition using Transfer Learning Approach of DL Models

This project is based on a dataset based on Librivox audiobooks which trains two deep learning models : CNN and ANN ; and compares their results after testing it on data collected either from Youtube or collected live.

# Testing Demo
To test the pretrained models, run Transfer_Learning.ipynb.
## CNN
Run the model on pretrained weights model.h5 and test data containiing in folder tfdata1 in png format.
## ANN
Run the model on pretrained weights ann_weights80.h5 and test data containiing in folder ann_data as spectrograms of csv format.

# Preparing Dataset
Run Creating_Datasets.ipynb for downloading Librivox audiobooks.(You can also run DataProcessing.ipynb prior to this to get the files in zip format)
This will create two datasets, one in the form of tree of directories containing spectrograms images with their corresponding speaker label.(Used in CNN training)
Second one in the form of csv format containing extracted spectral features of a audio segment for the corresponding speaker audio label.(Used in ANN Model)

# Training CNN Model
Run Training_CNN.ipynb to train the CNN network and store the weights of the model.

# Training ANN Model
Run Training_ANN.ipynb to train the ANN network and store the weights of the model.

# Run Transfer_Learning .ipynb to test the models and plot the precision-recall curves.

